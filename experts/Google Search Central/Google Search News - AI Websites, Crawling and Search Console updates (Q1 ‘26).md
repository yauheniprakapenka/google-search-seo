# AI Websites, Crawling and Search Console updates (Q1 ‘26)

Краткий разбор выпуска Google Search News с John Mueller (Google Switzerland): обновления Search Console, замечания про vibe-coded сайты, новая документация по краулингу и короткие новости Search.

---

## Search Console

С прошлого выпуска в GSC выкатилось несколько заметных фич.

### Branded vs non-branded

Появилось разделение запросов на **branded** и **non-branded** — где пользователь явно искал ваш бренд/бизнес.

- В **Search Console Insights** есть сравнение этих типов запросов.
- В **Performance** — больше деталей.
- Сплит строится **AI-ом по нескольким сигналам**, это не regex.
- Доступно для top-level сайтов с достаточным трафиком.

### AI-конфигуратор Performance

AI-powered tool помогает быстрее настроить Performance report под повседневные решения — особенно если отчёт ещё непривычен.

### Weekly / monthly агрегации

В отчёте добавили недельные и месячные агрегации. Дневной «шум» часто мешает увидеть тренд или проблему; более крупные окна упрощают чтение.

### Social profiles в Insights (ограниченный роллаут)

Для небольшого набора сайтов в Insights можно добавить search-данные по социальным профилям компании. Фича экспериментальная; если видите — жмите thumbs up / thumbs down рядом с отчётом.

### Напоминание

Query groups и custom annotations всё ещё стоит попробовать, если ещё не трогали. У команды GSC в пайплайне ещё обновления.

---

## Vibe-coded websites (сайты, собранные в основном AI)

Это обычные сайты: для поиска они в целом нормальны. Но Mueller отмечает несколько практических пунктов.

| Проверка | Зачем |
| --- | --- |
| Контент реально добавляет ценность вебу | Легко «нагенерить» сайт; сложно сделать так, чтобы людям было зачем на него приходить |
| SEO Starter Guide | Базовый контекст, как работает Search |
| `rel=canonical` с полным URL (включая домен) | На многостраничных AI-сайтах часто ломается |
| JS-фреймворки (React, Next.js) | Проверьте, что Google реально видит контент; смотрите JavaScript SEO docs/videos |
| Добавить сайт в Search Console | Видеть проблемы и performance |

В целом vibe-coded сайты, которые Mueller видел, часто имеют нормальные titles и structured data — это плюс. Создавать можно и через Gemini, и через более узкие инструменты вроде Antigravity / AI Studio.

Массово «захватывать популярный веб» такие сайты пока не обязаны. Но для работы с небольшими клиентами имеет смысл набить руку.

---

## Crawling: новый хаб документации

Google сделал отдельный сайт/раздел с общей информацией про crawling (включая перенесённый search-контент).

Что добавили:

- документацию по краулерам **Read Along**, **NotebookLM**, **Pinpoint**, **Google Agent**  
  (Google Agent — краулер для AI-агентов на инфраструктуре Google; им тоже можно пользоваться);
- high-level гайд «что стоит знать про web crawling Google» — удобная ссылка на типовые вопросы;
- обновление про **fetch limits для Googlebot**: лимит **2 MB** на uncompressed initial HTML (есть нюансы). Большинству сайтов не критично; если в HTML огромные меню — стоит перепроверить. Есть blog post и подкаст с деталями.

---

## Короткие обновления Search

| Тема | Суть |
| --- | --- |
| Алгоритмы | Были Discover core update, spam update и обычный core update — штатная работа над качеством выдачи |
| Google Shopping / UCP | Поддержка **Universal Commerce Protocol** — общий язык для агентов, которые взаимодействуют с сайтом и бизнесом. Ещё рано; не всем e-commerce нужно срочно прыгать |
| Google Trends | Новая Explore page + AI-помощь в подборе терминов для сравнения |
| Ивенты | Search Central Live уже были в Brazil и Argentina; дальше — Toronto, Shanghai, Sydney |

---

## Подборка из SEO-сообщества

| Автор | Материал |
| --- | --- |
| MJ Cachones | Полный гайд по e-commerce SEO |
| Dawn Anderson | Demystifying generative information retrieval — разбор путаницы из соцсетей |
| Lily Ray | SEO и AI: рефлексия и отсев распространённых misconceptions |
| Amy DiRinka | Роль informational-контента в эпоху LLM — снова про ценность, а не «магический трюк» |

---

## Бонус: robots.txt с Doom

Bant Wonch сделал валидный `robots.txt`, внутри которого лежит копия классического Doom. Делать так не обязательно — но можно. Напоминание: `robots.txt` в целом простой файл.

---

## Кратко

1. GSC: branded/non-branded, AI-хелпер для Performance, weekly/monthly, эксперимент с social в Insights.
2. Vibe-coded сайты для Search обычно ок, если есть ценность, корректный canonical и проверяемый рендер для JS.
3. Новый crawling-хаб + доки по новым краулерам + лимит 2 MB на initial HTML.
4. UCP для e-commerce — смотреть, но не паниковать; Trends Explore обновили; впереди серия Search Central Live.
