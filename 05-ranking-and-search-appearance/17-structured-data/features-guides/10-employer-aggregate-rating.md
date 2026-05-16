# Employer aggregate rating (`EmployerAggregateRating`) structured data

> Source: https://developers.google.com/search/docs/appearance/structured-data/employer-rating
> Last updated: 2025-12-10 UTC

If your site publishes user-generated ratings about hiring organizations, add `EmployerAggregateRating` structured data to your site. `EmployerAggregateRating` is an evaluation of a hiring organization compiled from many users. Adding `EmployerAggregateRating` can provide job seekers with ratings about a hiring organization to help them choose a job.

## Example

Here's an example for `EmployerAggregateRating` using JSON-LD code.

```html
<html>
  <head>
    <title>World's Best Coffee Shop</title>
    <script type="application/ld+json">
    {
      "@context" : "https://schema.org/",
      "@type": "EmployerAggregateRating",
      "itemReviewed": {
        "@type": "Organization",
        "name" : "World's Best Coffee Shop",
        "sameAs" : "https://example.com"
      },
      "ratingValue": 91,
      "bestRating": 100,
      "worstRating": 1,
      "ratingCount" : "10561"
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

## How to add structured data

1. Add the required properties.
2. Follow the guidelines.
3. Validate your code using the Rich Results Test.
4. Deploy and test with URL Inspection tool.
5. Submit a sitemap.

## Guidelines

You must follow these guidelines to be eligible to appear in the Google job search experience.

- Technical guidelines
- Content guidelines
- Enriched search quality guidelines
- Search Essentials
- General structured data guidelines

### Technical guidelines

- Make sure that the ratings are available to users from the page where you add `EmployerAggregateRating` structured data.
- Provide rating information about a specific hiring organization, not about a category or a list of items.
- By default, Google assumes a 5-point scale (5=best, 1=worst), but you can use any other scale by specifying `bestRating` and `worstRating`.

### Content guidelines

- Users must be able to post their own ratings on your site and your site must host those user ratings.
- The number of ratings must reflect actual ratings that users provide.
- The aggregate score must be accurately derived from the provided ratings.

## Structured data type definitions

### `EmployerAggregateRating`

The full definition is available at schema.org/EmployerAggregateRating.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `itemReviewed` | `Organization` | The organization that is being rated. Must point to a schema.org/Organization. |
| `ratingCount` | `Number` | The total number of ratings of the organization on your site. At least one of `ratingCount` or `reviewCount` is required. |
| `ratingValue` | `Number` or `Text` | A numerical quality rating for the item, either a number, fraction, or percentage. Default scale is 5-point (1-5). |
| `reviewCount` | `Number` | Specifies the number of people who provided a review with or without an accompanying rating. At least one of `ratingCount` or `reviewCount` is required. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `bestRating` | `Number` | The highest value allowed in this rating system. If omitted, 5 is assumed. |
| `worstRating` | `Number` | The lowest value allowed in this rating system. If omitted, 1 is assumed. |

Example:

```json
{
  "@context" : "https://schema.org/",
  "@type": "EmployerAggregateRating",
  "itemReviewed": {
    "@type": "Organization",
    "name" : "World's Best Coffee Shop",
    "sameAs" : "https://www.worlds-best-coffee-shop.example.com"
  }
}
```
