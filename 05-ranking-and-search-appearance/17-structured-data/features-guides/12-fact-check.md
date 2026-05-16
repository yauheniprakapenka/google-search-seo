# Fact check (`ClaimReview`) structured data

> Source: https://developers.google.com/search/docs/appearance/structured-data/factcheck
> Last updated: 2025-12-10 UTC

We're phasing out support for `ClaimReview` markup in Google Search. However, this markup remains supported by the Factcheck Explorer Tool.

If you have a web page that reviews a claim made by others, you can include `ClaimReview` structured data on your web page. `ClaimReview` structured data can enable a summarized version of your fact check to display in Google Search results when your page appears in search results for that claim.

This guide describes the details on how to implement `ClaimReview` structured data. If you don't want to add structured data manually, you can check out the Fact Check Markup Tool.

## How to add structured data

1. Add the required properties.
2. Follow the guidelines.
3. Validate your code using the Rich Results Test.
4. Deploy and test with URL Inspection tool.
5. Submit a sitemap.

## Example

Here's an example of structured data on a page that hosts a fact check:

```html
<html>
  <head>
    <title>The world is flat</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "ClaimReview",
      "url": "https://example.com/news/science/worldisflat.html",
      "claimReviewed": "The world is flat",
      "itemReviewed": {
        "@type": "Claim",
        "author": {
          "@type": "Organization",
          "name": "Square World Society",
          "sameAs": "https://example.flatworlders.com/we-know-that-the-world-is-flat"
        },
        "datePublished": "2024-06-20",
        "appearance": {
          "@type": "OpinionNewsArticle",
          "url": "https://example.com/news/a122121",
          "headline": "Square Earth - Flat earthers for the Internet age",
          "datePublished": "2024-06-22",
          "author": {
            "@type": "Person",
            "name": "T. Tellar"
          },
          "image": "https://example.com/photos/1x1/photo.jpg",
          "publisher": {
            "@type": "Organization",
            "name": "Skeptical News",
            "logo": {
              "@type": "ImageObject",
              "url": "https://example.com/logo.jpg"
            }
          }
        }
      },
      "author": {
        "@type": "Organization",
        "name": "Example.com science watch"
      },
      "reviewRating": {
        "@type": "Rating",
        "ratingValue": 1,
        "bestRating": 5,
        "worstRating": 1,
        "alternateName": "False"
      }
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

## Eligibility guidelines

Google doesn't guarantee that fact checks will be shown in search results, even if your page is marked up correctly. The Google algorithm programmatically determines eligibility depending on many variables, including the following guidelines:

- Your site must have several pages marked with `ClaimReview` structured data.
- You must follow all the structured data guidelines and Search Essentials.
- There must not be any mismatch between the structured data and page content.
- You must meet the standards for accountability, transparency, readability, and site misrepresentation.
- You must have a corrections policy or mechanism for users to report errors.
- Websites for political entities aren't eligible.
- Readers must easily identify claims and checks in the article body.
- You must clearly attribute the specific claim to a distinct origin.
- Your analysis must be traceable and transparent about sources and methods.

### Technical guidelines

- To be eligible for the single fact check rich result, a page must only have one `ClaimReview` element.
- The page hosting the `ClaimReview` element must have at least a brief summary of the fact check.
- A specific `ClaimReview` must only be on one page on your site.
- If your website aggregates fact-check articles, ensure all articles match the criteria.

## Structured data type definitions

### `ClaimReview`

The full definition is available at schema.org/ClaimReview.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `claimReviewed` | `Text` | A short summary of the claim being evaluated. Try to keep this less than 75 characters. Don't include the rating here; use `reviewRating` instead. |
| `reviewRating` | `Rating` | The assessment of the claim. Supports both numeric and textual assessment. |
| `url` | `URL` | Link to the page hosting the full article. Domain must be same as or subdomain of the hosting page. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `author` | `Organization` or `Person` | The publisher of the fact check article. Must include `name` and optionally `url`. |
| `itemReviewed` | `Claim` | An object describing the claim being made. |

### `Claim`

The full definition is available at schema.org/Claim.

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `appearance` | `URL` or `CreativeWork` | A link to, or inline description of, a `CreativeWork` in which this claim appears. |
| `author` | `Organization` or `Person` | The author of the claim (not the fact check). Include `name` (required) and `sameAs` (recommended). |
| `datePublished` | `DateTime` or `Date` | The date when the claim was made or entered public discourse. |
| `firstAppearance` | `URL` or `CreativeWork` | A link to, or inline description of, a `CreativeWork` in which this specific claim first appears. |

### `Rating`

The full definition is available at schema.org/Rating.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `alternateName` | `Text` | The truthfulness rating as a human-readable short word or phrase. Example: "True" or "Mostly true". |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `bestRating` | `Number` | For numeric ratings, the best value possible. Must be greater than `worstRating`. |
| `ratingValue` | `Number` | A numeric rating in the range `worstRating` to `bestRating`. |
| `worstRating` | `Number` | For numeric ratings, the worst value possible. Must be less than `bestRating`. Minimum value of 1. |
