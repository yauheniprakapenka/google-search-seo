# Translated results in Google Search

> Source: https://developers.google.com/search/docs/appearance/translated-results
> Last updated: 2025-12-10 UTC

Google Search strives to make information accessible and useful to all users. To help address content and perspective gaps when a user searches in their local language, sometimes Google may translate the title link and snippet of a search result for results that aren't in the language of the search query. Translated results enable people to view results from other languages in their language, and can help publishers reach a larger audience.

## Feature availability

Currently, Google may translate results into the following languages: Arabic, Bengali, English, French, German, Gujarati, Hindi, Indonesian, Kannada, Korean, Malayalam, Marathi, Persian, Portuguese, Spanish, Tamil, Telugu, Thai, Turkish, Urdu, Vietnamese. It's available on mobile and desktop.

## How translated results work

If the user clicks the translated title link, they're presented with a page that's been machine translated. Users also have an option to view the original search result, and access the entire page in the original language.

Google doesn't host any translated pages. Opening a page through a translated result is no different than opening the original search result through Google Translate or using Chrome in-browser translation. This means that Javascript on the page is usually supported, as well as embedded images and other page features.

## Monitor performance in Search Console

To monitor clicks and impressions for translated results, you can use the Search Appearance filter in the Performance report.

## Opting in or out of translated results

This feature is applicable across all pages and results based on the user's language. You don't need to do anything to opt in.

Translated results are like other translation-related features in Google Search. To opt out of all translation features in Google Search, use the `notranslate` rule, which can be implemented as a `meta` tag or an HTTP header:

```html
<!-- opt out of translation features on all search engines that support this rule -->
<meta name="robots" content="notranslate">

<!-- opt out of translation features on Google -->
<meta name="googlebot" content="notranslate">
```

Alternatively, you can specify the rule as an HTTP response header:

```
X-Robots-Tag: notranslate
```
