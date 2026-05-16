# FAQ (`FAQPage`, `Question`, `Answer`) structured data

> Source: https://developers.google.com/search/docs/appearance/structured-data/faqpage
> Last updated: 2026-05-08 UTC

**Upcoming deprecation:** As of May 7, 2026, FAQ rich results are no longer appearing in Google Search. We will be dropping the FAQ search appearance, rich result report, and support in the Rich results test in June 2026.

If your government-focused or health-focused site has a list of questions and answers, you can use `FAQPage` structured data to help people find that information on Google. Properly marked up FAQ pages may be eligible to have a rich result on Search and an Action on the Google Assistant.

**Does your site allow users to submit answers to a single question?** Use `QAPage` structured data instead.

## Feature availability

FAQ rich results are only available for well-known, authoritative websites that are government-focused or health-focused. The feature is available on desktop and mobile devices in all countries and languages where Google Search is available.

## How to add structured data

1. Add the required properties.
2. Follow the guidelines.
3. Validate your code using the Rich Results Test.
4. Deploy and test with URL Inspection tool.
5. Submit a sitemap.

## Examples

### JSON-LD

```html
<html>
  <head>
    <title>Finding an apprenticeship - Frequently Asked Questions(FAQ)</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "FAQPage",
      "mainEntity": [{
        "@type": "Question",
        "name": "How to find an apprenticeship?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "<p>We provide an official service to search through available apprenticeships. To get started, create an account here, specify the desired region, and your preferences. You will be able to search through all officially registered open apprenticeships.</p>"
        }
      }, {
        "@type": "Question",
        "name": "Whom to contact?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "You can contact the apprenticeship office through our official phone hotline above, or with the web-form below. We generally respond to written requests within 7-10 days."
        }
      }]
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

### Microdata

```html
<html itemscope itemtype="https://schema.org/FAQPage">
<head></head>
<body>
  <h1>Frequently Asked Questions(FAQ)</h1>
  <div itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
    <h2 itemprop="name">How to find an apprenticeship?</h2>
    <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
      <div itemprop="text">
        We provide an official service to search through available apprenticeships.
      </div>
    </div>
  </div>
  <div itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
    <h2 itemprop="name">Whom to contact?</h2>
    <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
      <div itemprop="text">
        You can contact the apprenticeship office through our official phone hotline above.
      </div>
    </div>
  </div>
</body>
</html>
```

## Guidelines

- General structured data guidelines
- Search Essentials
- Content guidelines

### Content guidelines

- Your site must be a health or government site. It must also be well-known and authoritative.
- Only use `FAQPage` if your page contains FAQs where there's a single answer to each question. If your page has a single question and users can submit alternative answers, use `QAPage` instead.
- Don't use `FAQPage` for advertising purposes.
- Make sure each `Question` includes the entire text of the question and each `Answer` includes the entire text of the answer.
- Question and answer content may not be displayed if it contains obscene, profane, sexually explicit, graphically violent, or hateful content.
- All `FAQ` content must be visible to the user on the source page.
- If you have FAQ content that is repetitive on your site, mark up only one instance of that FAQ for your entire site.

## Structured data type definitions

### `FAQPage`

The full definition of FAQPage is provided on schema.org. The `FAQPage` type indicates that the page is an FAQ with answered questions. There must be one `FAQPage` type definition per page.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `mainEntity` | `Question` | An array of `Question` elements which contain the list of answered questions. You must specify at least one valid `Question` item. |

### `Question`

The `Question` type defines a single answered question within the FAQ. Every `Question` instance must be contained within the `mainEntity` property array of the `schema.org/FAQPage`.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `acceptedAnswer` | `Answer` | The answer to the question. There must be one answer per question. |
| `name` | `Text` | The full text of the question. For example, "How long does it take to process a refund?". |

### `Answer`

The `Answer` type defines the `acceptedAnswer` to each of the `Question` on this page.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `text` | `Text` | The full answer to the question. May contain HTML content such as links and lists. Supported HTML tags: `<h1>` through `<h6>`, `<br>`, `<ol>`, `<ul>`, `<li>`, `<a>`, `<p>`, `<div>`, `<b>`, `<strong>`, `<i>`, and `<em>`. |
