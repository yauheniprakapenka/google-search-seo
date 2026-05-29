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

## Информационные заметки (не требуют действий)

| # | Элемент | Что найдено на странице | Пояснение | Источник |
|---|---|---|---|---|
| 1 | ... | ... | ... | `путь/к/файлу.md` |

---

*Аудит проведён на основе офлайн-архива документации Google Search. Все требования ссылаются на конкретные файлы архива.*
```

- **Соответствует требованиям** — пункты, где страница полностью отвечает требованиям Google
- **Нарушения** — конкретные несоответствия обязательным требованиям или политикам
- **Рекомендации** — советы по улучшению (best practices), не являющиеся строго обязательными, но способные улучшить видимость в поиске
- **Информационные заметки** — элементы, наличие или отсутствие которых не является ошибкой, но упоминаются для полноты картины. Сюда относятся: устаревшие типы структурированных данных, игнорируемые мета-теги, несовпадения между источниками title link и прочие случаи, когда Google прямо указывает, что элемент не влияет на ранжирование

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

7. **Информационные заметки (не требуют действий).** Ряд элементов не является ни нарушением, ни рекомендацией, но должен быть упомянут в отдельной таблице «Информационные заметки (не требуют действий)» для полноты картины. Все такие случаи перечислены ниже. При обнаружении на странице эти элементы вносятся **только** в таблицу информационных заметок, **не** в «Нарушения» и **не** в «Рекомендации»:
   - **FAQPage** — с 7 мая 2026 года Google прекратил показ FAQ rich results. Формулировка: «FAQPage-разметка не требуется: с 07.05.2026 Google прекратил показ FAQ rich results. Наличие FAQ-контента на странице полезно для пользователей и AI Overviews, но добавлять FAQPage schema не нужно.»
   - **`<meta name="keywords">`** — Google полностью игнорирует этот тег. Формулировка: «Наличие или отсутствие `<meta name="keywords">` не влияет на ранжирование — Google игнорирует этот тег.»
   - **Несовпадение og:title и `<title>`** — Google использует og:title как один из возможных источников title link, но не требует его совпадения с `<title>`. Формулировка: «og:title отличается от `<title>`, но Google не требует их совпадения — это один из нескольких возможных источников title link.»

 9. **Не использовать `aggregateRating` без верифицируемых отзывов.** Если на странице нет видимых, подтверждённых отзывов (например, из Google Business Profile, Яндекс.Карт), свойство `aggregateRating` **не должно** добавляться в структурированные данные. Причина: документация запрещает "fake reviews" и "misleading content" (`05-ranking-and-search-appearance/17-structured-data/02-structured-data-general-guidelines.md`, строки 44–45), нарушение ведёт к manual action — потере права на rich results. Если на странице найден `aggregateRating` без подтверждённых отзывов — вносить в «Нарушения» как нарушение спам-политик.

10. **Стандартный набор схем для страниц ветеринарных клиник.** Для страниц услуг ветеринарной клиники (и аналогичных локальных бизнесов) следует использовать три типа JSON-LD в одном `@graph`:

    **Используемые типы:**
    - **`Organization`** — общая информация о компании: название, логотип, год основания, контакты, `sameAs` (соцсети). Один раз на сайт, можно дублировать на все страницы.
    - **`VeterinaryCare`** (не `LocalBusiness`) — наиболее специфичный тип по документации ("Use the most specific LocalBusiness sub-type possible", `05-ranking-and-search-appearance/17-structured-data/features-guides/16-local-business.md`). Свойства: `name`, `description`, `url`, `telephone`, `address` (массив филиалов), `image`, `priceRange`, `openingHoursSpecification`. Предупреждения валидатора для `priceRange` и `openingHoursSpecification` игнорируются (свойства унаследованы от `LocalBusiness`, Google обрабатывает корректно). `aggregateRating` — **только** при наличии верифицируемых отзывов (см. ограничение #9).
    - **`BreadcrumbList`** — хлебные крошки для понимания структуры сайта. Обязательно для каждой страницы.

    **Не используемые типы и причины:**
    - **`LocalBusiness`** — заменён на `VeterinaryCare`, более специфичный подтип.
    - **`FAQPage`** — прекращён 07.05.2026 (см. ограничение #7).
    - **`Service`** — Google не поддерживает rich results для этого типа.
    - **`MedicalProcedure`** — нет rich results, Google не использует.
    - **`HowTo`** — для пошаговых инструкций, не для услуг.
    - **`Review` / `ReviewSnippet`** — только при наличии реальных отзывов на странице.
    - **`Article` / `NewsArticle`** — для статей, не для услуг.
    - **`Product`** — для товаров с ценой, не для услуг.
    - **`Event`** — для мероприятий, не для постоянных услуг.

11. **Количество ссылок в `sameAs` НЕ является аудируемым критерием.**
    - Google не устанавливает требований или рекомендаций по количеству ссылок в свойстве `sameAs`. Документация лишь описывает назначение свойства — указание URL профилей, представляющих ту же сущность.
    - Больше ссылок в `sameAs` не означает лучше для SEO. Не использовать количественные пороги вида «2 из 5+ профилей — плохо» или «нужно минимум 5 ссылок».
    - Если sameAs присутствует и содержит корректные ссылки — этого достаточно.
    - Расширение sameAs можно упомянуть как **опциональную рекомендацию** (низкий приоритет): дополнительные ссылки на Яндекс.Карты, Google Maps / Business Profile, 2ГИС, YouTube могут помочь AI-моделям с entity resolution, но это не SEO-требование. Добавлять или нет — решает пользователь.
    - Не использовать формулировки «sameAs минимальный», «критический пробел в sameAs», «2 из 5+ платформ» — это выдуманные критерии.

12. **`Person`-схемы для врачей на странице услуги не нужны.** Google не поддерживает rich results для типа `Person`. Разметка врачей на странице услуги не даёт никакого визуального эффекта в выдаче. Это пустая разметка без пользы для SEO. Документация: "Don't create blank or empty pages just to hold structured data" (`05-ranking-and-search-appearance/17-structured-data/01-understand-how-structured-data-works.md`) — тот же принцип: не добавлять разметку, которая ничего не даёт. Не использовать формулировки «отсутствие Person-схем» как проблему или нарушение.

    **Когда `Person` имеет смысл (вложенный тип, не standalone):**
    - **`author` в статьях** (`Article`, `NewsArticle`, `BlogPosting`) — Google показывает автора в rich results. Требуется `author.name`, рекомендуется `author.url` (ссылка на страницу автора). Источник: `05-ranking-and-search-appearance/17-structured-data/features-guides/02-article.md`.
    - **`mainEntity` в `ProfilePage`** — для страниц-профилей людей (форумы, соцсети, сообщества). Помогает Google понимать авторов контента и показывать его в «Discussions and Forums». Источник: `05-ranking-and-search-appearance/17-structured-data/features-guides/21-profile-page.md`.
    - **Вложенное свойство в других типах** — `Review.author`, `Book.author`, `Movie.actor`, `Event.performer`, `ImageObject.creator` — всегда в контексте родительского типа, у которого есть rich results.

    **Для ветклиники `Person` приобретает смысл только при появлении:**
    - Отдельных страниц-профилей врачей (`ProfilePage`, `mainEntity: Person`) — для блога/сообщества;
    - Статей/блог-постов от имени конкретного врача (`Article`, `author: Person`);
    - Отзывов пациентов с указанием врача (`Review`, `author: Person`).

13. **Отсутствие авторства (byline) на странице услуги — не критическая проблема и не нарушение.** Документация: «E-E-A-T itself isn't a specific ranking factor» (`03-seo-fundamentals/01-seo-starter-guide.md:214`), «We strongly encourage adding accurate authorship information, such as bylines to content **where readers might expect it**» (`03-seo-fundamentals/03-creating-helpful-content.md:96`). Ключевая фраза: «where readers might expect it» — на странице услуги ветклиники читатель ожидает информацию об услуге, а не авторскую статью. Это не блог и не медицинская статья. Наличие блока с перечислением врачей клиники (даже всех, не только профильных) — достаточно. Не использовать формулировки «критическая проблема для YMYL-контента» или «нет авторства (E-E-A-T)» как нарушение или проблему высокого приоритета.     Упоминание конкретных врачей, выполняющих данную услугу, — опциональная рекомендация низкого приоритета (UX-улучшение, не SEO-требование).

14. **Даты публикации/обновления (`datePublished`/`dateModified`) на странице услуги не нужны.** Документация по byline dates (`05-ranking-and-search-appearance/03-byline-dates.md`) предназначена для контента типа `Article`, `BlogPosting`, `NewsArticle`, `VideoObject` — публикаций со сроком актуальности. Страница услуги — это постоянно актуальная коммерческая страница, а не публикация. Свойства `datePublished`/`dateModified` релевантны только для подтипов `CreativeWork`, не для `VeterinaryCare`. Не использовать формулировки «нет дат публикации» как проблему или рекомендацию. Ссылки на Perplexity/Google AIO как источник требования не принимаются — это не Google Search, их факторы не относятся к документации проекта.
