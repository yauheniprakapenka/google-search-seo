# Structured data for subscription and paywalled content (`CreativeWork`)

> Source: <https://developers.google.com/search/docs/appearance/structured-data/paywalled-content>

> Last updated: 2025-12-10 UTC

This page describes how to use schema.org JSON-LD to indicate paywalled content on your site with [`CreativeWork`](https://schema.org/CreativeWork) properties. This structured data helps Google differentiate paywalled content from the practice of [cloaking](/search/docs/essentials/spam-policies#cloaking), which violates [spam policies](/search/docs/essentials/spam-policies).

## Example

Here's an example of `NewsArticle` structured data with paywalled content.

```html
<html>
  <head>
    <title>Article headline</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "NewsArticle",
      "headline": "Article headline",
      "image": "https://example.org/thumbnail1.jpg",
      "datePublished": "2025-02-05T08:00:00+08:00",
      "dateModified": "2025-02-05T09:20:00+08:00",
      "author": {
        "@type": "Person",
        "name": "John Doe",
        "url": "https://example.com/profile/johndoe123"
      },
      "description": "A most wonderful article",
      "isAccessibleForFree": false,
      "hasPart":
        {
        "@type": "WebPageElement",
        "isAccessibleForFree": false,
        "cssSelector" : ".paywall"
        }
    }
    </script>
  </head>
  <body>
    <div class="non-paywall">
      Non-Paywalled Content
    </div>
    <div class="paywall">
      Paywalled Content
    </div>
  </body>
</html>
```

## Guidelines

- JSON-LD and microdata formats are accepted methods for specifying structured data for paywalled content.
- Don't nest content sections.
- Only use `.class` selectors for the `cssSelector` property.
- If you don't want the content to be accessible to the browser at the time of serving, choose a paywall implementation that doesn't supply the paywalled content to the browser. If you use a client-side JavaScript solution, check our [guidance on using JavaScript to implement paywalled content](/search/docs/crawling-indexing/javascript/fix-search-javascript#paywall).

## Add markup to paywalled content

If you offer any subscription-based access to your website content, follow these steps for all versions of your page (including AMP and non-AMP).

1. Add a class name around each paywalled section of your page:

```html
<body>
<p>This content is outside a paywall and is visible to all.</p>
<div class="paywall">This content is inside a paywall, and requires a subscription or registration.</div>
</body>
```

2. Add [`NewsArticle`](/search/docs/appearance/structured-data/article) structured data.
3. Add the highlighted JSON-LD structured data to your `NewsArticle` structured data:

```json
{
  "@context": "https://schema.org",
  "@type": "NewsArticle",
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://example.org/article"
  },
  "isAccessibleForFree": false,
  "hasPart": {
    "@type": "WebPageElement",
    "isAccessibleForFree": false,
    "cssSelector": ".paywall"
  }
}
```

### Multiple paywalled sections

If you have multiple paywalled sections on a page, add the class names as an array.

```html
<body>
  <div class="section1">This content is inside a paywall.</div>
  <p>This content is outside a paywall and is visible to all.</p>
  <div class="section2">This is another section that's inside a paywall.</div>
</body>
```

```json
{
  "@context": "https://schema.org",
  "@type": "NewsArticle",
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://example.org/article"
  },
  "isAccessibleForFree": false,
  "hasPart": [
    {
      "@type": "WebPageElement",
      "isAccessibleForFree": false,
      "cssSelector": ".section1"
    }, {
      "@type": "WebPageElement",
      "isAccessibleForFree": false,
      "cssSelector": ".section2"
    }
  ]
}
```

### Supported types

This markup is supported for the `[CreativeWork](https://schema.org/CreativeWork)` type or one of the following more specific types:

- `Article`
- `NewsArticle`
- `Blog`
- `Comment`
- `Course`
- `HowTo`
- `Message`
- `Review`
- `WebPage`

Multiple schema.org types can be used:

```json
"@type": ["Article", "LearningResource"]
```

## Structured data type definitions

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `isAccessibleForFree` | `Boolean` | Whether the article is accessible to everyone. Set to `false` to specify that this section is behind a paywall. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `hasPart.cssSelector` | `CssSelectorType` | A CSS selector that references the class name you set in the HTML. |
| `hasPart.@type` | `Text` | Set to `WebPageElement`. |
| `hasPart.isAccessibleForFree` | `Boolean` | Whether this section is behind a paywall. Set to `False` for paywalled sections. |

## AMP considerations

- If you have an AMP page with paywalled content, use [`amp-subscriptions`](https://www.ampproject.org/docs/reference/components/amp-subscriptions) where appropriate.
- Make sure that your authorization endpoint grants access to content to the appropriate bots from Google and others.
- Ensure that your bot access policy is the same for AMP and non-AMP pages.

## Make sure Google can crawl and index your pages

If you want Google to crawl and index your content, including the paywalled sections, make sure [Googlebot](/search/docs/crawling-indexing/verifying-googlebot), and [`Googlebot-News`](/search/docs/crawling-indexing/overview-google-crawlers#googlebot-news) if applicable, can access your page.

## Control what information is shown in search results

To exclude certain sections from appearing in search result snippets, use the [`data-nosnippet` HTML attribute](/search/docs/crawling-indexing/robots-meta-tag#data-nosnippet-attr). You can also limit snippet length using the [`max-snippet` robots `meta` tag](/search/docs/crawling-indexing/robots-meta-tag#max-snippet).
