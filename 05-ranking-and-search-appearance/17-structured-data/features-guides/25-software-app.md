# Software app (`SoftwareApplication`) structured data

> Source: <https://developers.google.com/search/docs/appearance/structured-data/software-app>

> Last updated: 2025-12-10 UTC

Mark up software application information in the body of a web page to better display your app details in Google Search results.

## How to add structured data

1. Add the [required properties](#structured-data-type-definitions).
2. Follow the [guidelines](#guidelines).
3. Validate your code using the [Rich Results Test](https://search.google.com/test/rich-results).
4. Deploy a few pages and use the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289) to test.
5. To keep Google informed of future changes, [submit a sitemap](/search/docs/crawling-indexing/sitemaps/build-sitemap).

## Examples

### JSON-LD

```html
<html>
  <head>
    <title>Angry Birds</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "SoftwareApplication",
      "name": "Angry Birds",
      "operatingSystem": "ANDROID",
      "applicationCategory": "GameApplication",
      "aggregateRating": {
        "@type": "AggregateRating",
        "ratingValue": 4.6,
        "ratingCount": 8864
      },
      "offers": {
        "@type": "Offer",
        "price": 1.00,
        "priceCurrency": "USD"
      }
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

## Guidelines

- [Search Essentials](/search/docs/essentials)
- [General structured data guidelines](/search/docs/appearance/structured-data/sd-policies)

## Structured data type definitions

### `SoftwareApplication`

The full definition of `SoftwareApplication` is available at [schema.org/SoftwareApplication](https://schema.org/SoftwareApplication).

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `name` | `Text` | The name of the app. |
| `offers.price` | `Offer` | An offer to sell the app. If free, set `offers.price` to `0`. If paid, also include `offers.priceCurrency`. |
| Rating or review | | You must include one of the following: |
| `aggregateRating` | `AggregateRating` | The average review score. Follow the [Review snippet guidelines](/search/docs/appearance/structured-data/review-snippet#guidelines). |
| `review` | `Review` | A single review. Follow the [Review snippet guidelines](/search/docs/appearance/structured-data/review-snippet#guidelines). |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `applicationCategory` | `Text` | The type of app. Must be a supported app type (see below). |
| `operatingSystem` | `Text` | The operating system(s) required (e.g., `Windows 7`, `OSX 10.6`, `Android 1.6`). |

### Supported app types

- `GameApplication`
- `SocialNetworkingApplication`
- `TravelApplication`
- `ShoppingApplication`
- `SportsApplication`
- `LifestyleApplication`
- `BusinessApplication`
- `DesignApplication`
- `DeveloperApplication`
- `DriverApplication`
- `EducationalApplication`
- `HealthApplication`
- `FinanceApplication`
- `SecurityApplication`
- `BrowserApplication`
- `CommunicationApplication`
- `DesktopEnhancementApplication`
- `EntertainmentApplication`
- `MultimediaApplication`
- `HomeApplication`
- `UtilitiesApplication`
- `ReferenceApplication`

### Extended properties for app subtypes

For mobile applications and web applications, Google also supports [`MobileApplication`](https://schema.org/MobileApplication) and [`WebApplication`](https://schema.org/WebApplication).

Google doesn't show a rich result for Software Apps that only have the [`VideoGame`](https://schema.org/VideoGame) type. Co-type `VideoGame` with another type:

```json
{
  "@context": "https://schema.org",
  "@type": ["VideoGame", "MobileApplication"],
  ....
}
```
