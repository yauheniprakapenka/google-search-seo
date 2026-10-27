> Source: https://bsky.app/profile/johnmu.com/post/3myaxnekqbc2x
> Автор: John Mueller (@johnmu.com, Bluesky)
> Опубликовано: 19 октября 2026 года
> Локальная адаптация на русский язык: 21 октября 2026 года

# John Mueller: URL с закодированными и незакодированными зарезервированными символами — это НЕ эквивалентные URL

## Контекст треда

Тред начался 14 октября 2026 года, когда John Mueller поделился видео Google Search Central «[What can you actually put in a URL 🐔?](https://www.youtube.com/watch?v=Mfvw43BbHy0)» («Что на самом деле можно поместить в URL»):

> «Can you use emoji domain names as usernames here on Bluesky? Hmm…» («Можно ли использовать эмодзи в доменных именах как имена пользователей на Bluesky? Хм…»)

18 октября 2026 года [Vanessa Fox](https://bsky.app/profile/vanessafox.bsky.social) задала вопрос в комментариях к видео и продублировала его в треде:

> «I posted this question in the YT video comments: For URLs with characters that can be encoded (brackets, plus signs, spaces), does Google treat the encoded version as a distinct URL? (example.com/category?filter[]=123 vs. example.com/category?filter%5B%5D=123 used in links vs. canonical values).»
>
> («Я задала этот вопрос в комментариях к YouTube-видео: для URL с символами, которые могут быть закодированы (квадратные скобки, знаки плюс, пробелы), — считает ли Google закодированную версию отдельным URL? (example.com/category?filter[]=123 vs. example.com/category?filter%5B%5D=123 — используемые в ссылках против значений canonical»).»

## Пост John Mueller (сохраняемый)

19 октября 2026 года John Mueller ответил:

> «Well, TIL. I would have assumed they're equivalent, but they're NOT. This was a fun side-track. "?filter[]=123" ≠ "?filter%5B%5D=123" because in RFC 3986, Section 2.2 the characters brackets ([, ]) and plus signs (+) are defined as part of the reserved set.»
>
> («Что ж, TIL [today I learned — сегодня я узнал]. Я бы предположил, что они эквивалентны, но это НЕ так. Это было интересное ответвление. "?filter[]=123" ≠ "?filter%5B%5D=123", потому что в RFC 3986, раздел 2.2, символы квадратных скобок ([, ]) и знаки плюс (+) определены как часть зарезервированного набора».)

И в ответе дополнил цитатой из RFC 3986:

> «"URIs that differ in the replacement of a reserved character with its corresponding percent-encoded octet are not equivalent. Percent-encoding a reserved character, or decoding a percent-encoded octet that corresponds to a reserved character, will change how the URI is interpreted by …"»
>
> («URI, различающиеся заменой зарезервированного символа на соответствующий процентно-закодированный октет, не эквивалентны. Процентное кодирование зарезервированного символа или декодирование процентно-закодированного октета, соответствующего зарезервированному символу, изменит то, как URI интерпретируется…»)

## Суть для практики

- `?filter[]=123` и `?filter%5B%5D=123` — **разные** URL с точки зрения интерпретации по RFC 3986.
- Квадратные скобки `[`, `]` и знак `+` входят в зарезервированный набор символов (RFC 3986, Section 2.2). Их кодирование/раскодирование меняет интерпретацию URI.
- Практический вывод: при генерации ссылок и canonical-значений нужно последовательно использовать одну и ту же форму записи URL — расхождение между формой в ссылках и формой в canonical может указывать на разные URL.
