# Episode 98: Lazy loading demystified

Разбор выпуска *Search Off the Record* с John Mueller и Martin Splitt: что такое lazy loading, почему нельзя вешать `loading="lazy"` на всё подряд, как это бьёт по LCP/SEO и чем custom-библиотеки отличаются от нативного атрибута.

---

## Что это и зачем

**Lazy loading** — грузить ресурс, когда он реально нужен, а не сразу со всей страницей.

Зачем:

- меньше работы «впустую»;
- экономия сети, батареи, CPU;
- браузер не занят картинками/виджетами внизу, пока пользователь до них не доскроллил.

HTTP-waterfall «по 5 запросов» — не то же самое: без lazy браузер всё равно дотянет картинки/видео внизу страницы, даже если пользователь туда никогда не дойдёт.

Выигрывают почти все страницы, особенно длинные. Не только images: iframe, video, блоки с API (stock ticker — меньше платных вызовов), комментарии, куски контента из API.

---

## Эволюция: от JS-библиотек к `loading="lazy"`

| Эра | Как делали |
| --- | --- |
| Раньше | Свои/сторонние JS-библиотеки: детект viewport → подставить URL |
| Сейчас | Нативный `loading="lazy"` на **`<img>`** и **`<iframe>`** |

WordPress (вклад Felix Arntz и др.) по умолчанию использует image lazy loading — обсуждение «потише»: часто достаточно атрибута.

Натив лучше самописного JS для типовых картинок/iframe. Библиотеки не исчезнут: legacy-темы, preview→hi-res swap, lazy для video/API-контента/комментов — натив этого не покрывает.

---

## Главная ошибка: lazy на hero / above-the-fold

Почему браузер **не** ставит lazy на все картинки сам:

У браузера есть **resource scanner**: видит `<img>` в HTML → старается начать загрузку рано (картинки заметны, если «пустые»).

`loading="lazy"` говорит: *не грузи, пока не понадобится*. Если так помечен **hero**:

1. Сначала парсят страницу, грузят non-lazy ресурсы.
2. Потом замечают, что hero тоже нужен.
3. Картинка «всплывает» поздно → хуже UX.
4. Без `width`/`height` — ещё и layout shift.

CMS, которая по умолчанию ставит lazy на **все** images (кейс с их docs CMS) — плохая идея.

| Элемент | Lazy? |
| --- | --- |
| Hero / LCP-кандидат above the fold | **Нет** |
| Картинки ниже fold | Обычно **да** |
| Hero video с autoplay | Lazy обычно **не** нужен |
| Video ниже fold | Часто poster сейчас, video — по приближению к viewport |

---

## Связь с Core Web Vitals и ранжированием

Performance — главный драйвер.

| Сценарий | Эффект |
| --- | --- |
| Нет lazy там, где нужно | Лишняя нагрузка → хуже CWV (часто LCP и общая «тяжесть») |
| Lazy на above-the-fold image | LCP почти наверняка **хуже** (paint позже) |

LCP не всегда картинка: поздний client-side блок текста с медленного API тоже может стать LCP.

Влияние на ranking через CWV — **маленький** фактор в большинстве случаев. Исключения бывают, но не «lazy = ранжирование».

---

## Индексация: натив vs custom

| Реализация | Риск для индекса |
| --- | --- |
| Нативный `loading="lazy"` + нормальный `src` | Обычно ок: URL картинки в `src`, грузится чуть позже |
| Custom (`data-src` → JS кладёт в `src`) | Если JS/библиотека ломается или Googlebot не «дотягивает» — **нет `src` → не подхватят** |

Custom ≠ автоматически проблема, но есть **потенциал** проблемы. Натив для images/iframes снимает большую часть риска.

Зачем всё ещё custom:

1. Старый стек / тема 5 лет назад без `loading`.
2. Low-res preview (data URL / другой URL) → swap на hi-res.
3. Не img/iframe: video, API-блоки, comments, ticker.

---

## Как проверить (SEO + dev)

**Главный способ:** Search Console → URL Inspection → **rendered HTML** (скриншот можно игнорировать).

Ищите:

- у картинок реальные URL в `src` (не только `data-src`);
- lazy-контент (комменты, виджеты) присутствует в rendered HTML.

Практично: скопировать rendered HTML и поискать нужные URL/фрагменты текста.

Дополнительно:

- не ранжируетесь по запросам, текст которых lazy → spot-check, есть ли текст в rendered;
- картинки массово не в Image Search → подозрение на сломанный custom lazy (с нативом реже).

---

## Lazy loading vs infinite scroll

| | Lazy loading | Infinite scroll |
| --- | --- | --- |
| Цель | Отложить **некритичные** куски **той же** страницы | Подгружать **новый** контент, страница «бесконечная» |
| Примеры | Images, comments, ticker | Лента постов/товаров без пагинации |
| Общее | Progressive load по viewport | То же по механике |
| Ловушка infinite | — | Потеря позиции при back; нужен способ выразить место в URL |

---

## Видео, privacy, декоратив

**Video:** тяжёлые → часто poster + load по viewport; крупные — streaming. Hero autoplay — не lazy. Отдельный кейс: грузить внешнее video только после consent (thumbnail + «click to activate») — по духу близко к lazy non-critical.

**Decorative images:** иконки/bullets лучше через CSS, не как смысловой `<img>` в статье про рыб Great Barrier Reef. CSS background ≠ lazy loading (грузится из CSS, не «по необходимости» в смысле атрибута). Для индекса картинок CSS обычно слабее `<img>`. Многомегабайтный «декор» — просто ошибка.

---

## Практический чеклист

1. Above-the-fold / LCP image — **без** `loading="lazy"`.
2. Ниже fold — native `loading="lazy"` на img/iframe, где уместно.
3. Всегда задавайте размеры картинок (width/height или CSS aspect), чтобы не прыгал layout.
4. Custom library → проверка rendered HTML в GSC.
5. `data-src` без попадания в `src` после render = риск для Image Search / индекса.
6. Infinite scroll — отдельно продумайте URL/состояние позиции.
7. Docs: [web.dev](https://web.dev) по lazy loading + Search Central; вопросы — Search Central help community / LinkedIn.

---

## Кратко

Lazy loading — про не грузить лишнее до нужды. Для картинок/iframe натив почти закрыл тему; не вешайте lazy на hero. Ошибки бьют в первую очередь по LCP/UX, во вторую — по индексации при кривом JS (`data-src`). Проверка = rendered HTML в Search Console, а не вера в «разработчик сказал, что всё ок».
