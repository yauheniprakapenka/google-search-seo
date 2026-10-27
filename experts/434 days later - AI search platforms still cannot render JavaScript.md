> Source: https://www.gsqi.com/marketing-blog/can-ai-search-platforms-render-javascript/
> Автор: Glenn Gabe (G-Squared Interactive)
> Опубликовано: 19 октября 2026 года
> Локальная адаптация на русский язык: 21 октября 2026 года

# Прошло 434 дня — по-прежнему ли AI-поисковые платформы вроде ChatGPT и Claude не могут рендерить JavaScript в октябре 2026 года?

![Тестирование AI-поиска и контента на JavaScript в октябре 2026 года.](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-sm.jpg)

В августе 2025 года я опубликовал пост о том, что AI-поисковые платформы вроде ChatGPT, Claude и других [не рендерят JavaScript](https://www.gsqi.com/marketing-blog/ai-search-javascript-rendering/). Я протестировал ряд сайтов, использовавших JS для отрисовки контента, и результаты были неутешительными… совсем неутешительными.

ChatGPT, Claude и Perplexity явно упирались в барьеры при попытке прочитать контент. Когда я просил каждого чат-бота прочитать содержимое страницы, они буквально рассказывали мне о проблемах в своих ответах, в том числе конкретно о том, как рендеринг на JavaScript мешает им видеть контент.

Например:

![Пример ответа о проблемах с рендерингом JS](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-1.jpg)

### А как насчёт Gemini и Copilot?

Во время тестов в прошлом году Gemini и Copilot справлялись, что вполне логично. Они опираются на мощные поисковые системы Google и Bing, и обе могут видеть контент, отрисованный через JavaScript (в большинстве случаев). Эту информацию я тоже привёл в своём посте.

Вот что говорится о рендеринге JavaScript в руководстве Google по оптимизации для генеративных AI-функций Google Search:

*«**If you're using JavaScript, be sure to follow JavaScript SEO best practices**. Google is able to process content within JavaScript as long as it isn't blocked.»* («Если вы используете JavaScript, обязательно следуйте лучшим практикам JavaScript SEO. Google может обрабатывать контент внутри JavaScript, если он не заблокирован»).

![Скриншот документации Google о JavaScript](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-google-doc.jpg)

В конце прошлого поста я дал советы владельцам сайтов: быть очень осторожными при использовании JavaScript для контента, как тестировать свой контент и как донести результаты до команды разработчиков. Если коротко: если вы хотите, чтобы AI-поисковые платформы видели ваш контент, **не** полагайтесь на рендеринг на JS.

### 434 дня спустя: тестируем AI-поисковые платформы снова!

Но мой пост был опубликован больше года назад — точнее, **434 дня** назад. Как выглядит ситуация сейчас? Эволюционировали ли AI-поисковые платформы и получили ли они возможность рендерить контент на JavaScript? Я разбирался.

Чтобы проверить текущее состояние контента, отрисовываемого через JavaScript, я протестировал несколько сайтов, использовавших JavaScript в разной степени для публикации контента. Некоторые использовали его для всего содержимого страницы, другие — для больших частей основного контента, при этом шапка и подвал были в статическом HTML.

**Я тестировал каждый сайт в:**

- ChatGPT
- Claude
- Perplexity
- Gemini
- Copilot

Я использовал тот же подход, что и в прошлом году: просил каждую AI-платформу прочитать контент на странице и привести первый и последний абзацы. Результаты ниже.

### Тест 1: основной контент полностью рендерится через JavaScript.

**ChatGPT: провал**

Когда я попросил ChatGPT прочитать контент и вернуть первый и последний абзацы, он явно не смог этого сделать. И сам об этом сказал. Вот его ответ:

*«I opened the {url}, but the page extraction returned only navigation and footer elements, not the main body text. I can't verify the actual first and last paragraphs of the page. Its main content may be dynamically rendered.»* («Я открыл {url}, но извлечение страницы вернуло только элементы навигации и подвала, а не основной текст. Я не могу проверить фактические первый и последний абзацы страницы. Возможно, её основной контент рендерится динамически».)

![ChatGPT не видит основной контент](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-one-chatgpt.jpg)

**Claude: провал**

У Claude тоже были серьёзные проблемы. Он по сути увидел только навигацию и подвал — и ничего больше.

*«Only partly. The page fetched fine (200, HTML), but what came back was just the site chrome: the header (phone number, heading, login link), the nav menus, social links, and the footer. None of the main body content about products was in the response. That pattern usually means a Next.js page whose main content renders client-side, so a fetcher that doesn't execute JavaScript only sees the shell.»* («Частично. Страница загрузилась нормально (200, HTML), но вернулась только «обвязка» сайта: шапка (номер телефона, заголовок, ссылка на вход), меню навигации, ссылки на соцсети и подвал. Ни одного основного текста о продуктах в ответе не было. Такой паттерн обычно означает страницу Next.js, чей основной контент рендерится на клиенте, поэтому fetcher, не исполняющий JavaScript, видит только оболочку».)

![Claude видит только оболочку страницы](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-one-claude.jpg)

**Perplexity: провал**

Perplexity столкнулась с теми же проблемами на этом сайте.

*«Partially—I can retrieve text from the URL, but the extraction is dominated by the cookie-consent content and only includes a small portion of the page content. I can't reliably identify the last paragraph of the full page.»* («Частично — я могу получить текст по URL, но извлечение в основном состоит из текста cookie-согласия и включает лишь небольшую часть контента страницы. Я не могу надёжно определить последний абзац полной страницы».)

![Perplexity видит только cookie-баннер и часть контента](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-one-perplexity.jpg)

**Gemini: успех!**

Как я объяснял ранее, Gemini опирается на поисковые системы Google, поэтому может видеть контент, отрисованный через JavaScript.

*«Yes, I can read the page. Here are the first and last substantive paragraphs from the content…»* («Да, я могу прочитать страницу. Вот первый и последний содержательные абзацы из контента…»)

![Gemini читает контент](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-one-gemini.jpg)

**Copilot: успех!**

Как и Gemini, Copilot видит контент, отрисованный через JavaScript, поскольку опирается на поисковые системы Bing.

*«Yes — I can read the page you shared. Here are the first and last paragraphs from the content retrieved…»* («Да — я могу прочитать страницу, которой вы поделились. Вот первый и последний абзацы из полученного контента…»)

![Copilot читает контент](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-one-copilot.jpg)

### Тест 2: шапка и подвал присутствуют, но основной контент полностью рендерится через JavaScript.

**ChatGPT: провал**

Нет, он вообще не смог увидеть основной контент.

«I can access the page, but I cannot retrieve all of its main content.» («Я могу открыть страницу, но не могу получить весь её основной контент») и «…information isn't appearing in the extracted HTML» («…информация не появляется в извлечённом HTML»).

![ChatGPT снова не видит основной контент](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-two-chatgpt.jpg)

**Claude: провал (и обратите внимание на часть про «plain HTML fetch»)**

Claude увидел только заголовок страницы, подвал и юридический шаблонный текст. Он также объяснил, что основной контент рендерится через JS, а обычная HTML-выгрузка (plain HTML fetch) его не подхватывает.

*«Partly. The page loads, but none of the page's actual content came through. What I got was the page title, the tab labels, the footer navigation, and the legal boilerplate. There was no description, objective, etc. That strongly suggests the main body is rendered client-side with JavaScript, which a plain HTML fetch doesn't run.»* («Частично. Страница загружается, но ни один реальный контент страницы не прошёл. Я получил заголовок страницы, подписи вкладок, навигацию подвала и юридический шаблонный текст. Ни описания, ни целей и т.д. Это явно указывает, что основной контент рендерится на клиенте через JavaScript, который обычная HTML-выгрузка не исполняет».)

![Claude видит только заголовок и юридический текст](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-two-claude-b.jpg)

**Perplexity: провал**

Perplexity могла видеть только оболочку страницы и юридический дисклеймер. Она даже сама объяснила, что основной контент рендерится динамически.

*«Yes, I can read the page, but the extracted content is mostly the page shell and legal/disclaimer text—not the main descriptive copy. It appears the content sections are rendered dynamically, so they weren't included in the readable text.»* («Да, я могу прочитать страницу, но извлечённый контент — это в основном оболочка страницы и юридический/дисклеймерный текст, а не основной описательный текст. Похоже, секции контента рендерятся динамически, поэтому они не попали в читаемый текст».)

![Perplexity видит только оболочку страницы](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-two-perplexity.jpg)

**Gemini: успех!**

Как я объяснял ранее, Gemini мог видеть основной контент, поскольку опирается на поисковые системы Google.

*«Yes, the page is accessible. Here are the first and last paragraphs from the content…»* («Да, страница доступна. Вот первый и последний абзацы из контента…»)

![Gemini снова читает контент](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-two-gemini.jpg)

**Copilot: успех!**

Как и Gemini, Copilot мог видеть основной контент, поскольку опирается на поисковые системы Bing.

*«Yes, I can read that page. The first paragraph of the description appears to be…»* («Да, я могу прочитать эту страницу. Первый абзац описания, похоже…»)

![Copilot снова читает контент](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-two-copilot.jpg)

### Тест 3: параллакс-сайт с головокружительным эффектом для AI-поиска (и для людей).

Следующий пример я протестировал как настоящий JS-тест… это был параллакс-сайт. Знаете, сайт, который даёт головокружительный эффект при прокрутке страницы, когда контент анимируется и меняется. Я не поклонник такого стиля с точки зрения UX, и, как вы увидите, с точки зрения AI-поиска он может создавать большие проблемы.

**ChatGPT: большой провал.**

ChatGPT просто объяснил, что вообще не может видеть содержимое страницы. Он увидел только заголовок страницы, а затем текст о том, что контент не может загрузиться (по сути, ошибку загрузки). Затем объяснил, что сайт зависит от рендеринга JavaScript, который его «читалка» страниц не смогла успешно загрузить.

*«I attempted to read the page, but I couldn't access the actual page content. Here's what I found: Visible text: "THE CONTENT DID NOT LOAD". Error message: "This page could not be drawn. The connection may have dropped, or this browser could not start its graphics. Reload to try again. The site appears to depend on browser-based graphics or JavaScript rendering that my page reader cannot successfully load.»* («Я попытался прочитать страницу, но не смог получить доступ к её фактическому контенту. Вот что я нашёл: Видимый текст: «КОНТЕНТ НЕ ЗАГРУЗИЛСЯ». Сообщение об ошибке: «Эту страницу не удалось отрисовать. Возможно, соединение прервалось, или этот браузер не смог запустить свою графику. Перезагрузите и попробуйте снова». Похоже, сайт зависит от браузерной графики или рендеринга JavaScript, которые моя читалка страниц не может успешно загрузить».)

![ChatGPT видит только ошибку загрузки](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-three-chatgpt.jpg)

**Claude: большой провал.**

Claude вообще не смог увидеть содержимое страницы. Он объяснил, что страница основана на JavaScript, и он не может прочитать ни один из её материалов. Он также предложил вариант загрузить страницу во встроенном браузере, подождать рендеринга и вернуться с результатами… Это было интересно.

*«What comes back without a browser is a shell for a JavaScript/WebGL experience, not a page with real paragraphs. What I can see is the metadata. The visible text is just fragments: a "loading" indicator, the site name, a progress readout, and a fallback error block. That error block says the roll did not load, the page couldn't be drawn, and the connection may have dropped or the browser couldn't start its graphics, with a reload prompt. This is the classic client-side rendering problem: a crawler that doesn't execute JS, or an AI fetcher like the one I used, gets almost nothing beyond the meta tags.»* («Без браузера возвращается оболочка для JavaScript/WebGL-экспериенса, а не страница с настоящими абзацами. Я вижу только метаданные. Видимый текст — это просто фрагменты: индикатор «загрузки», название сайта, показания прогресса и резервный блок ошибки. Этот блок ошибки говорит, что ролл не загрузился, страницу не удалось отрисовать, соединение могло прерваться или браузер не смог запустить графику, с предложением перезагрузить. Это классическая проблема клиентского рендеринга: краулер, не исполняющий JS, или AI-fetcher вроде того, что использовал я, не получает почти ничего, кроме мета-тегов».)

![Claude видит только оболочку WebGL](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-three-claude.jpg)

**Perplexity: провал.**

Perplexity также не смогла прочитать содержимое страницы. Уточню: она думает, что читает содержимое, но это то самое сообщение об ошибке, о котором я писал выше для других AI-платформ.

*«Yes, I can read the page, but it's a highly interactive WebGL/canvas experience rather than a conventional text page. The extracted page content contains essentially one visible block of text, not multiple normal paragraphs. The first (and effectively only) paragraph was, "THE PAGE DID NOT LOAD. This page could not be drawn. The connection may have dropped, or this browser could not start its graphics. Reload to try again.»* («Да, я могу прочитать страницу, но это высокоинтерактивный WebGL/canvas-экспириенс, а не обычная текстовая страница. Извлечённый контент содержит по сути один видимый блок текста, а не несколько нормальных абзацев. Первый (и фактически единственный) абзац был: «СТРАНИЦА НЕ ЗАГРУЗИЛАСЬ. Эту страницу не удалось отрисовать. Возможно, соединение прервалось, или этот браузер не смог запустить свою графику. Перезагрузите и попробуйте снова»».)

![Perplexity читает только сообщение об ошибке](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-three-perplexity.jpg)

**Gemini: успех!**

Как и ожидалось, Gemini смог прочитать содержимое страницы. Он подхватил различные секции контента, которые пользователь видит при прокрутке. А также подхватил сообщение об ошибке, которое было в коде.

*«Yes, I can access the page. It's an interactive, WebGL-driven 3D showcase site for a conceptual product rather than a traditional text-heavy article, so it contains very little paragraph body text. Here is the first paragraph… Note: The page also includes an initial fallback error state for WebGL rendering: "This page could not be drawn. The connection may have dropped, or this browser could not start its graphics. Reload to try again.»* («Да, я могу открыть страницу. Это интерактивный 3D-шоукейс-сайт на WebGL для концептуального продукта, а не традиционная текстовая статья, поэтому в нём очень мало абзацев с основным текстом. Вот первый абзац… Примечание: страница также содержит начальное резервное состояние ошибки для WebGL-рендеринга: «Эту страницу не удалось отрисовать. Возможно, соединение прервалось, или этот браузер не смог запустить свою графику. Перезагрузите и попробуйте снова»».)

![Gemini читает секции параллакс-сайта](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-three-gemini.jpg)

**Copilot: провал.**

Это было интересно. Copilot **НЕ** смог увидеть контент, хотя опирается на поисковые системы Bing. Он увидел только сообщение об ошибке. Также он спросил, не хочу ли я, чтобы он использовал более глубокий подход к извлечению текста.

*«I can access a limited text rendering of the page, but the site appears to rely heavily on graphics/animation and did not fully load in the browser used by my web tool.*

*From the content I could retrieve: "THE PAGE DID NOT LOAD. This page could not be drawn. The connection may have dropped, or this browser could not start its graphics. Reload to try again. Because the page is graphics-driven, I may not be seeing the full underlying content. If you'd like, I can try a deeper retrieval approach and extract more of the site's text.»* («Я могу получить ограниченную текстовую версию страницы, но сайт, похоже, сильно зависит от графики/анимации и не полностью загрузился в браузере, который использует мой веб-инструмент. Из контента, который я смог получить: «СТРАНИЦА НЕ ЗАГРУЗИЛАСЬ. Эту страницу не удалось отрисовать. Возможно, соединение прервалось, или этот браузер не смог запустить свою графику. Перезагрузите и попробуйте снова». Поскольку страница управляется графикой, я могу видеть не весь основной контент. Если хотите, я могу попробовать более глубокий подход к извлечению и вытащить больше текста сайта».)

![Copilot видит только ошибку](https://www.gsqi.com/marketing-blog/wp-content/uploads/sites/3/2026/10/ai-search-javascript-2026-case-three-copilot.jpg)

### Итог: контент на JavaScript всё ещё большая проблема для AI-поиска. Будьте осторожны.

Итак, спустя больше года AI-поисковые платформы по-прежнему не могут рендерить контент на JavaScript. Поэтому я бы по-прежнему был очень осторожен с тем, как вы используете контент на JavaScript на своём сайте. Этот контент будет невидим для AI-поисковых платформ вроде ChatGPT, Claude, Perplexity и других. А для некоторых протестированных страниц даже Gemini и Copilot не смогли увидеть контент (хотя они опираются на поисковые системы Google и Bing).

Я продолжу следить за ситуацией и проведу дополнительные тесты в будущем, чтобы увидеть, как продвигается рендеринг JavaScript. Надеюсь, AI-поисковые платформы эволюционируют в этом плане sooner than later. Но до тех пор — будьте осторожны с контентом, требующим рендеринга на JavaScript.

GG
