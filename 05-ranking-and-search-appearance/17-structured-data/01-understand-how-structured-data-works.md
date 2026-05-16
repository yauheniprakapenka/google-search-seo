# Introduction to structured data markup in Google Search

> Source: https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data
> Last updated: 2025-12-10 UTC

Google Search works hard to understand the content of a page. You can help us by providing explicit clues about the meaning of a page to Google by including structured data on the page. Structured data is a standardized format for providing information about a page and classifying the page content; for example, on a recipe page, what are the ingredients, the cooking time and temperature, the calories, and so on.

## Why add structured data to a page?

Adding structured data can enable search results that are more engaging to users and might encourage them to interact more with your website, which are called *rich results*. Here are some case studies of websites that have implemented structured data for their site:

- **Rotten Tomatoes** added structured data to 100,000 unique pages and measured a **25% higher click-through rate** for pages enhanced with structured data.
- **The Food Network** has converted 80% of their pages to enable search features, and has seen a **35% increase in visits**.
- **Rakuten** has found that users spend **1.5x more time** on pages that implemented structured data.
- **Nestlé** has measured pages that show as rich results in search have an **82% higher click through rate** than non-rich result pages.

## How structured data works in Google Search

Google uses structured data that it finds on the web to understand the content of the page, as well as to gather information about the web and the world in general.

Structured data is coded using in-page markup on the page that the information applies to. The structured data on the page describes the content of that page. **Don't create blank or empty pages just to hold structured data**, and don't add structured data about information that is not visible to the user, even if the information is accurate.

The [Rich Results Test](https://search.google.com/test/rich-results) is an easy and useful tool for validating your structured data, and in some cases, previewing a feature in Google Search.

### Example: Recipe structured data (JSON-LD)

```html
<html>
  <head>
    <title>Non-Alcoholic Piña Colada</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org/",
      "@type": "Recipe",
      "name": "Non-Alcoholic Piña Colada",
      "image": [
        "https://example.com/photos/1x1/photo.jpg",
        "https://example.com/photos/4x3/photo.jpg",
        "https://example.com/photos/16x9/photo.jpg"
      ],
      "author": {
        "@type": "Person",
        "name": "Mary Stone"
      },
      "datePublished": "2024-03-10",
      "description": "This non-alcoholic pina colada is everyone's favorite!",
      "recipeCuisine": "American",
      "prepTime": "PT1M",
      "cookTime": "PT2M",
      "totalTime": "PT3M",
      "keywords": "non-alcoholic",
      "recipeYield": "4 servings",
      "recipeCategory": "Drink",
      "nutrition": {
        "@type": "NutritionInformation",
        "calories": "120 calories"
      },
      "aggregateRating": {
        "@type": "AggregateRating",
        "ratingValue": 5,
        "ratingCount": 18
      },
      "recipeIngredient": [
        "400ml of pineapple juice",
        "100ml cream of coconut",
        "ice"
      ],
      "recipeInstructions": [
        {
          "@type": "HowToStep",
          "name": "Blend",
          "text": "Blend 400ml of pineapple juice and 100ml cream of coconut until smooth.",
          "url": "https://example.com/non-alcoholic-pina-colada#step1",
          "image": "https://example.com/photos/non-alcoholic-pina-colada/step1.jpg"
        },
        {
          "@type": "HowToStep",
          "name": "Fill",
          "text": "Fill a glass with ice.",
          "url": "https://example.com/non-alcoholic-pina-colada#step2",
          "image": "https://example.com/photos/non-alcoholic-pina-colada/step2.jpg"
        },
        {
          "@type": "HowToStep",
          "name": "Pour",
          "text": "Pour the pineapple juice and coconut mixture over ice.",
          "url": "https://example.com/non-alcoholic-pina-colada#step3",
          "image": "https://example.com/photos/non-alcoholic-pina-colada/step3.jpg"
        }
      ],
      "video": {
        "@type": "VideoObject",
        "name": "How to Make a Non-Alcoholic Piña Colada",
        "description": "This is how you make a non-alcoholic piña colada.",
        "thumbnailUrl": [
          "https://example.com/photos/1x1/photo.jpg",
          "https://example.com/photos/4x3/photo.jpg",
          "https://example.com/photos/16x9/photo.jpg"
        ],
        "contentUrl": "https://www.example.com/video123.mp4",
        "embedUrl": "https://www.example.com/videoplayer?video=123",
        "uploadDate": "2024-02-05T08:00:00+08:00",
        "duration": "PT1M33S",
        "interactionStatistic": {
          "@type": "InteractionCounter",
          "interactionType": { "@type": "WatchAction" },
          "userInteractionCount": 2347
        },
        "expires": "2024-02-05T08:00:00+08:00"
      }
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

## Structured data vocabulary and format

Most Search structured data uses [schema.org](https://schema.org/) vocabulary, but you should rely on the Google Search Central documentation as definitive for Google Search behavior, rather than the schema.org documentation.

**Data-vocabulary.org markup is no longer eligible for Google rich result features.**

You must include all the **required properties** for an object to be eligible for appearance in Google Search with enhanced display. In general, defining more recommended features can make it more likely that your information can appear in Search results with enhanced display. However, it is more important to supply **fewer but complete and accurate** recommended properties rather than trying to provide every possible recommended property with less complete, badly-formed, or inaccurate data.

### Supported formats

| Format | Description |
|--------|-------------|
| **JSON-LD** (Recommended) | A JavaScript notation embedded in a `<script>` tag in the `<head>` and `<body>` elements of an HTML page. The markup is not interleaved with the user-visible text, which makes nested data items easier to express. Google can read JSON-LD data when it is dynamically injected into the page's contents. |
| **Microdata** | An open-community HTML specification used to nest structured data within HTML content. Uses HTML tag attributes to name the properties. Typically used in the `<body>` element. |
| **RDFa** | An HTML5 extension that supports linked data by introducing HTML tag attributes that correspond to the user-visible content. Commonly used in both `<head>` and `<body>` sections. |

In general, Google recommends using **JSON-LD** for structured data — it's the easiest solution to implement and maintain at scale (less prone to user errors).

## Structured data guidelines

Be sure to follow the [general structured data guidelines](./02-sd-policies.md), as well as any guidelines specific to your structured data type; otherwise your structured data might be ineligible for rich result display in Google Search.

## Get started with structured data

If you're new to structured data, check out [schema.org beginner's guide to structured data](https://schema.org/docs/gs.html). While the guide focuses on Microdata, the basic ideas are relevant for JSON-LD and RDFa.

Explore the [list of structured data features in Google Search](./03-search-gallery.md) and pick a feature to implement.

## Measuring the effect of structured data

1. Take some pages on your site that are not using any structured data, and have several months of data in Search Console.
2. Add structured data or other features to your pages. Confirm that your markup is valid using the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289).
3. Record the performance for a few months in the [Performance report](https://support.google.com/webmasters/answer/7576553#by_search_appearance), and filter by URL to compare performance.
