# AGENTS.md

## О проекте

Это офлайн-архив официальной документации Google по SEO (поисковой оптимизации для Google Search), скопированной с `developers.google.com/search/docs`. Архив содержит только справочные материалы на английском языке, исполняемого кода нет.

Назначение проекта — служить источником требований и рекомендаций для аудита веб-страниц на соответствие правилам Google Search.

Каждый `.md`-файл содержит заголовок с исходным URL (`> Source: ...`) и дату последнего обновления (`> Last updated: ...`).

## Структура папок

```
google-search-seo/
├── 01-introduction.md                          # Введение: что такое SEO, ссылки на базовые ресурсы
├── 02-search-essentials/                       # Обязательные требования Google Search
│   ├── 01-google-search-essentials.md          #   Общий обзор essentials
│   ├── 02-technical-requirements.md            #   Технические требования (HTTP 200, Googlebot не заблокирован, индексируемый контент)
│   └── 03-spam-policies.md                     #   Политики против спама (cloaking, doorway, скрытый текст,-link spam и др.)
├── 03-seo-fundamentals/                        # Базовые принципы SEO
│   ├── 01-seo-starter-guide.md                 #   SEO Starter Guide — полный гайд для начинающих
│   ├── 02-how-google-search-works.md           #   Как работает поиск Google
│   ├── 03-creating-helpful-content.md          #   Создание полезного контента (E-E-A-T)
│   ├── 04-generative-ai-fundamentals/          #   SEO и генеративный ИИ
│   ├── 05-maintaining-your-site-seo.md         #   Поддержание SEO сайта
│   ├── 06-developers-guide-to-search.md        #   Гайд для разработчиков
│   └── 07-do-you-need-an-seo.md                #   Нужен ли вам SEO-специалист
├── 04-crawling-and-indexing/                   # Кроулинг и индексация
│   ├── 01-overview.md                          #   Обзор
│   ├── 02-file-types-google-can-index.md       #   Типы файлов, которые Google может индексировать
│   ├── 03-url-structure.md                     #   Структура URL
│   ├── 04-links.md                             #   Ссылки и перелинковка
│   ├── 05-sitemaps/                            #   Sitemap: создание, отправка, расширения (image, news, video)
│   ├── 06-crawler-management/                  #   Управление краулером, список Googlebot'ов
│   ├── 07-robots.txt/                          #   robots.txt: синтаксис и интерпретация Google
│   ├── 08-canonicalization/                    #   Канонизация URL: указание, исправление проблем
│   ├── 09-mobile-sites-mobile-first-indexing.md #  Мобильная индексация (mobile-first)
│   ├── 10-amp/                                 #   AMP: гайдлайны, валидация, удаление
│   ├── 11-javascript/                          #   JavaScript SEO: основы, ленивая загрузка, динамический рендеринг
│   ├── 12-page-and-content-metadata/           #   Мета-теги, robots meta, rel-атрибуты
│   ├── 13-removals/                            #   Удаление контента из выдачи
│   └── 14-site-moves-and-changes/              #   Переезды сайта, редиректы, A/B тестирование
├── 05-ranking-and-search-appearance/           # Ранжирование и внешний вид в поиске
│   ├── 01-overview.md                          #   Обзор
│   ├── 02-ai-features.md                       #   AI-фичи в поиске
│   ├── 03-byline-dates.md                      #   Даты (byline dates) в сниппетах
│   ├── 04-favicons.md                          #   Favicon в выдаче
│   ├── 05-featured-snippets.md                 #   Избранные сниппеты
│   ├── 06-flexible-sampling.md                 #   Flexible Sampling (paywall-контент)
│   ├── 07-google-discover.md                   #   Google Discover
│   ├── 08-images.md                            #   Оптимизация изображений
│   ├── 09-local-features/                      #   Локальные функции (Business details, Top places)
│   ├── 10-page-experience/                     #   Page Experience: Core Web Vitals, интерстициалы
│   ├── 11-preferred-sources.md                 #   Предпочитаемые источники
│   ├── 12-ranking-systems/                     #   Системы ранжирования (Core updates, Reviews system)
│   ├── 13-ranking-updates/                     #   Обновления ранжирования
│   ├── 14-site-names.md                        #   Названия сайтов в выдаче
│   ├── 15-sitelinks.md                         #   Сителинки
│   ├── 16-snippet.md                           #   Сниппеты (meta description)
│   ├── 17-structured-data/                     #   Структурированные данные (JSON-LD)
│   │   ├── 01-understand-how-structured-data-works.md
│   │   ├── 02-structured-data-general-guidelines.md
│   │   ├── 03-enriched-search-results.md
│   │   ├── 04-generate-structured-data-with-javascript.md
│   │   └── features-guides/                    #     Гайды по конкретным типам (Article, Product, FAQ, Recipe и т.д.)
│   ├── 18-title-link.md                        #   Title link в выдаче
│   ├── 19-translated-features/                 #   Переводы и мультиязычность
│   ├── 20-video.md                             #   Видео в поиске
│   ├── 21-visual-elements-gallery.md           #   Галерея визуальных элементов выдачи
│   ├── 22-web-stories/                         #   Web Stories
│   └── 23-early-adopters-program/              #   Early adopters: package tracking, carousels
├── 06-monitoring-and-debugging/                # Мониторинг и отладка
│   ├── 01-debugging-drops-in-search-traffic.md #   Отладка падения трафика
│   ├── 02-monitor-with-search-console/         #   Search Console: начало, bubble chart, аналитика
│   ├── 03-debug-with-search-operators/         #   Операторы поиска для отладки
│   ├── 04-preventing-and-monitoring-abuse/     #   Защита от злоупотреблений: malware, спам, social engineering
│   └── 05-Get-started-with-Google-Trends.md    #   Google Trends
└── 07-site-specific-guides/                    # Руководства для конкретных типов сайтов
    ├── 01-ecommerce/                           #   E-commerce: обзор, структурированные данные, URL, структура сайта
    ├── 02-International-and-multilingual/      #   Международные и мультиязычные сайты: hreflang, locale
    └── 03-explicit-content/                    #   Контент для взрослых: гайдлайны, обжалование флага
```

## Алгоритм работы агента при аудите страницы

Когда пользователь даёт ссылку на страницу, агент должен выполнить следующие шаги:

### Шаг 1. Открыть страницу и изучить содержимое

- Получить HTML-код страницы по ссылке
- Проанализировать:
  - HTTP-статус ответа
  - `<title>` и `<meta name="description">`
  - Заголовки (`<h1>`–`<h6>`)
  - Канонический URL (`<link rel="canonical">`)
  - Мета-теги robots (`<meta name="robots">`)
  - Структурированные данные (JSON-LD, microdata, RDFa)
  - Атрибуты `alt` у изображений
  - Наличие `robots.txt` и `sitemap.xml` (по корневым URL)
  - Языковые атрибуты (`hreflang`)
  - Использование JavaScript для рендеринга контента
  - Мобильную адаптивность (viewport meta)
  - Open Graph и другие社交-мета-теги

### Шаг 2. Найти релевантные разделы в офлайн-архиве

На основе типа страницы и её содержимого определить, какие разделы документации применимы:

| Что анализируется | Где искать в архиве |
|---|---|
| Техническая доступность (HTTP-статус, блокировки) | `02-search-essentials/02-technical-requirements.md` |
| Спам-политики (cloaking, скрытый текст, doorway-страницы) | `02-search-essentials/03-spam-policies.md` |
| Базовые SEO-практики (заголовки, мета-описания, навигация) | `03-seo-fundamentals/01-seo-starter-guide.md` |
| Качество контента (E-E-A-T, helpful content) | `03-seo-fundamentals/03-creating-helpful-content.md` |
| URL-структура | `04-crawling-and-indexing/03-url-structure.md` |
| Sitemap | `04-crawling-and-indexing/05-sitemaps/` |
| Robots.txt | `04-crawling-and-indexing/07-robots.txt/` |
| Канонизация URL | `04-crawling-and-indexing/08-canonicalization/` |
| Мобильная индексация | `04-crawling-and-indexing/09-mobile-sites-mobile-first-indexing.md` |
| JavaScript SEO | `04-crawling-and-indexing/11-javascript/` |
| Мета-теги и метаданные | `04-crawling-and-indexing/12-page-and-content-metadata/` |
| Редиректы | `04-crawling-and-indexing/14-site-moves-and-changes/01-redirects-and-google-search.md` |
| Title link в выдаче | `05-ranking-and-search-appearance/18-title-link.md` |
| Сниппеты (meta description) | `05-ranking-and-search-appearance/16-snippet.md` |
| Структурированные данные | `05-ranking-and-search-appearance/17-structured-data/` |
| Изображения | `05-ranking-and-search-appearance/08-images.md` |
| Видео | `05-ranking-and-search-appearance/20-video.md` |
| Page Experience / Core Web Vitals | `05-ranking-and-search-appearance/10-page-experience/` |
| Favicon | `05-ranking-and-search-appearance/04-favicons.md` |
| hreflang / мультиязычность | `07-site-specific-guides/02-International-and-multilingual/` |
| E-commerce (если страница товарная) | `07-site-specific-guides/01-ecommerce/` |
| Контент для взрослых | `07-site-specific-guides/03-explicit-content/` |

### Шаг 3. Сверить страницу с требованиями из документации

- Последовательно проверить каждое требование из найденных релевантных разделов
- Сопоставить фактическое состояние страницы с тем, что рекомендует Google
- Классифицировать каждый пункт как: соответствует / нарушено / частично / не применимо

### Шаг 4. Сформировать отчёт

## Формат итогового отчёта

Отчёт должен быть структурирован следующим образом:

```markdown
# SEO-аудит страницы: [URL]

**Дата анализа:** [дата]

---

## Краткое резюме

[1-2 предложения об общем состоянии страницы]

---

## Соответствует требованиям

| # | Проверка | Значение на странице | Источник в документации |
|---|---|---|---|
| 1 | ... | ... | `путь/к/файлу.md` |

## Нарушения

| # | Проблема | Что найдено на странице | Требование из документации | Источник |
|---|---|---|---|---|
| 1 | ... | ... | ... | `путь/к/файлу.md` |

## Рекомендации

| # | Рекомендация | Почему это важно | Источник |
|---|---|---|---|
| 1 | ... | ... | `путь/к/файлу.md` |

---

*Аудит проведён на основе офлайн-архива документации Google Search. Все требования ссылуются на конкретные файлы архива.*
```

- **Соответствует требованиям** — пункты, где страница полностью отвечает требованиям Google
- **Нарушения** — конкретные несоответствия обязательным требованиям или политикам
- **Рекомендации** — советы по улучшению (best practices), не являющиеся строго обязательными, но способные улучшить видимость в поиске

## Разделы документации: за что отвечают

| Раздел | Ответственность |
|---|---|
| `01-introduction` | Общее знакомство с SEO, не содержит аудируемых требований |
| `02-search-essentials` | **Обязательные требования**. Технические требования к индексации и политики против спама. Нарушения здесь ведут к исключению из выдачи |
| `03-seo-fundamentals` | **Базовые практики SEO**. Starter guide, создание полезного контента, E-E-A-T, основы для начинающих |
| `04-crawling-and-indexing` | **Техническое SEO**. Всё, что связано с тем, как Google находит, обходит и индексирует страницы: robots.txt, sitemap, canonical, JS, мобильная индексация, мета-теги |
| `05-ranking-and-search-appearance` | **Ранжирование и представление**. Как страница выглядит и ранжируется в выдаче: сниппеты, структурированные данные, Core Web Vitals, изображения, видео, title-link |
| `06-monitoring-and-debugging` | **Мониторинг**. Инструменты для отслеживания и диагностики проблем (Search Console, операторы поиска). Не содержит требований к странице |
| `07-site-specific-guides` | **Специфические руководства**. Дополнительные требования для e-commerce, международных сайтов и контента для взрослых |

## Важные ограничения

1. **Ссылаться только на файлы из архива.** Все требования и рекомендации должны сопровождаться путём к конкретному `.md`-файлу в проекте. Пример: `02-search-essentials/02-technical-requirements.md`.

2. **Не придумывать требования.** Если в документации архива нет явного указания на требование или рекомендацию — не включать его в отчёт. Агент не должен генерировать правила «из общих соображений».

3. **Цитировать по существу.** При указании нарушения или рекомендации — кратко пересказывать, что именно сказано в документации, а не просто давать ссылку.

4. **Разделять обязательное и рекомендуемое.** Требования из `02-search-essentials` — обязательные (нарушение ведёт к исключению из выдачи). Рекомендации из `03-seo-fundamentals` и `05-ranking-and-search-appearance` — best practices (улучшают видимость, но не ведут к пенализации).

5. **Учитывать тип страницы.** Не все разделы документации применимы ко всем страницам. Например, структурированные данные для рецептов не применимы к лендингу SaaS-продукта. Агент должен определять тип страницы и отбирать только релевантные разделы.

6. **Язык отчёта.** Отчёт формируется на русском языке. Документация в архиве — на английском, цитаты из неё можно приводить на английском оригинале.

7. **Устаревшие структурированные данные.** Некоторые типы структурированных данных были официально прекращены Google. Их **не следует** включать в таблицу «Нарушения» или «Рекомендации». Если на странице присутствует контент, к которому ранее применялся такой тип разметки, следует добавить информационную заметку в раздел «Рекомендации» с пояснением, что разметка больше не требуется (чтобы избежать впечатления, что она была упущена):
   - **FAQPage** — с 7 мая 2026 года Google больше не показывает FAQ rich results в выдаче. Формулировка в отчёте: «FAQPage-разметка не требуется: с 07.05.2026 Google прекратил показ FAQ rich results. Наличие FAQ-контента на странице полезно для пользователей и AI Overviews, но добавлять FAQPage schema не нужно.»
