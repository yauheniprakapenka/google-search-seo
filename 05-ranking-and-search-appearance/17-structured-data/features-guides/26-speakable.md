# Speakable (`Article`, `WebPage`) structured data (BETA)

> Source: <https://developers.google.com/search/docs/appearance/structured-data/speakable>

> Last updated: 2025-12-10 UTC

This feature is in beta and subject to change.

The `speakable` [schema.org](https://schema.org/) property identifies sections within an article or webpage that are best suited for audio playback using text-to-speech (TTS). Adding markup allows search engines and other applications to identify content to read aloud on Google Assistant-enabled devices using TTS. Web pages with `speakable` structured data can use the Google Assistant to distribute the content through new channels and reach a wider base of users.

The Google Assistant uses `speakable` structured data to answer topical news queries on smart speaker devices. When users ask for news about a specific topic, the Google Assistant returns up to three articles from around the web and supports audio playback using TTS for sections in the article with `speakable` structured data. When the Google Assistant reads aloud a `speakable` section, it attributes the source and sends the full article URL to the user's mobile device through the Google Assistant app.

## Example

The following is an example of `speakable` structured data using JSON-LD code and the xPath `content-locator` value:

```html
<html>
  <head>
    <title>Speakable markup example</title>
    <meta name="description" content="This page is all about the quick brown fox" />
    <script type="application/ld+json">
    {
     "@context": "https://schema.org/",
     "@type": "WebPage",
     "name": "Quick Brown Fox",
     "speakable":
     {
      "@type": "SpeakableSpecification",
      "xPath": [
        "/html/head/title",
        "/html/head/meta[@name='description']/@content"
        ]
      },
     "url": "https://www.example.com/quick-brown-fox"
     }
    </script>
  </head>
  <body>
  </body>
</html>
```

## Country and language availability

The `speakable` property works for users in the U.S. that have Google Home devices set to English, and publishers that publish content in English. We hope to launch in other countries and languages as soon as sufficient number of publishers have implemented `speakable`.

## Getting started

For your news content to be eligible as answers to topical news queries, follow these steps:

1. Make sure that you follow [our guidelines](#guidelines).
2. Add [`speakable` structured data](#structured-data-type-definitions) to your web page.

## Guidelines

- [Technical guidelines](#technical-guidelines)
- [Content guidelines](#content-guidelines)
- [Search Essentials](/search/docs/essentials)
- [Structured data general guidelines](/search/docs/appearance/structured-data/sd-policies)

### Technical guidelines

- Don't add `speakable` structured data to content that may sound confusing in voice-only and voice-forward situations, like datelines, photo captions, or source attributions.
- Rather than highlighting an entire article with `speakable` structured data, focus on key points. This allows listeners to get an idea of the story and not have the TTS readout cut off important details.

### Content guidelines

- Content indicated by `speakable` structured data must have concise headlines and/or summaries that provide users with comprehensible and useful information.
- If you include the top of the story in `speakable` structured data, we suggest that you rewrite the top of the story to break up information into individual sentences so that it reads more clearly for TTS.
- For optimal audio user experiences, we recommend around 20-30 seconds of content per section of `speakable` structured data, or roughly two to three sentences.

## Structured data type definitions

[Speakable](https://pending.schema.org/speakable) is used by the [`Article`](https://pending.schema.org/Article) or [`Webpage`](https://pending.schema.org/WebPage) object. The full definition of `speakable` is available at [schema.org/speakable](https://schema.org/speakable). You must include the required properties for your content to be eligible for this feature.

Use one of the following properties:

**Required properties (use either `cssSelector` or `xPath`):**

| Property | Type | Description |
|----------|------|-------------|
| `cssSelector` | `Text` | Addresses content in the annotated pages (such as class attribute). Use either `cssSelector` or `xPath`; don't use both. |
| `xPath` | `Text` | Addresses content using xPaths. Use either `cssSelector` or `xPath`; don't use both. |

Example with `cssSelector`:

```json
"speakable":
  {
  "@type": "SpeakableSpecification",
  "cssSelector": [
    ".headline",
    ".summary"
  ]
}
```

Example with `xPath`:

```json
"speakable":
  {
  "@type": "SpeakableSpecification",
  "xPath": [
    "/html/head/title",
    "/html/head/meta[@name='description']/@content"
  ]
}
```
