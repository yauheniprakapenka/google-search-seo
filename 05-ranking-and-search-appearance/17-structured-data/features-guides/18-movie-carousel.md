# Movie carousel (`Movie`) structured data

> Source: <https://developers.google.com/search/docs/appearance/structured-data/movie>

> Last updated: 2025-12-10 UTC

Mark up your movie lists with structured data so users can explore movies on Google Search in new ways. You can provide details about the movies, such as the title of the movie, director of the movie, and an image of the movie. The movie carousel is only available on mobile devices.

## How to add structured data

1. Add the [required properties](#structured-data-type-definitions). Based on the format you're using, learn where to [insert structured data on the page](/search/docs/appearance/structured-data/intro-structured-data#format-placement).
2. Follow the [guidelines](#guidelines).
3. Validate your code using the [Rich Results Test](https://search.google.com/test/rich-results).
4. Deploy a few pages that include your structured data and use the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289) to test how Google sees the page.
5. To keep Google informed of future changes, we recommend that you [submit a sitemap](/search/docs/crawling-indexing/sitemaps/build-sitemap).

## Examples

### Summary page + multiple full details pages

The summary page has a short description of each item in the list, and each description points to a separate details page that is focused entirely on one item.

```html
<html>
  <head>
    <title>The Best Movies from the Oscars - 2024</title>
    <script type="application/ld+json">
    {
      "@context":"https://schema.org",
      "@type":"ItemList",
      "itemListElement":[
        {
          "@type":"ListItem",
          "position":1,
          "url":"https://example.com/a-star-is-born.html"
        },
        {
          "@type":"ListItem",
          "position":2,
          "url":"https://example.com/bohemian-rhapsody.html"
        },
        {
          "@type":"ListItem",
          "position":3,
          "url":"https://example.com/black-panther.html"
        }
      ]
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

### Single, all-in-one-page list

```html
<html>
  <head>
    <title>The Best Movies from the Oscars - 2024</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "ItemList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "position": 1,
          "item": {
            "@type": "Movie",
            "url": "https://example.com/2024-best-picture-noms#a-star-is-born",
            "name": "A Star Is Born",
            "image": "https://example.com/photos/6x9/photo.jpg",
            "dateCreated": "2024-10-05",
            "director": {
                "@type": "Person",
                "name": "Bradley Cooper"
            },
            "review": {
              "@type": "Review",
              "reviewRating": {
                "@type": "Rating",
                "ratingValue": 5
              },
              "author": {
                "@type": "Person",
                "name": "John D."
              }
            },
            "aggregateRating": {
              "@type": "AggregateRating",
              "ratingValue": 90,
              "bestRating": 100,
              "ratingCount": 19141
            }
          }
        },
        {
          "@type": "ListItem",
          "position": 2,
          "item": {
            "@type": "Movie",
            "name": "Bohemian Rhapsody",
            "url": "https://example.com/2024-best-picture-noms#bohemian-rhapsody",
            "image": "https://example.com/photos/6x9/photo.jpg",
            "dateCreated": "2024-11-02",
            "director": {
                "@type": "Person",
                "name": "Bryan Singer"
            },
            "review": {
              "@type": "Review",
              "reviewRating": {
                "@type": "Rating",
                "ratingValue": 3
              },
              "author": {
                "@type": "Person",
                "name": "Vin S."
              }
            },
            "aggregateRating": {
              "@type": "AggregateRating",
              "ratingValue": 61,
              "bestRating": 100,
              "ratingCount": 21985
            }
          }
        },
        {
          "@type": "ListItem",
          "position": 3,
          "item": {
            "@type": "Movie",
            "name": "Black Panther",
            "url": "https://example.com/2024-best-picture-noms#black-panther",
            "image": "https://example.com/photos/6x9/photo.jpg",
            "dateCreated": "2024-02-16",
            "director": {
                "@type": "Person",
                "name": "Ryan Coogler"
            },
            "review": {
              "@type": "Review",
              "reviewRating": {
                "@type": "Rating",
                "ratingValue": 2
              },
              "author": {
                "@type": "Person",
                "name": "Trevor R."
              }
            },
            "aggregateRating": {
              "@type": "AggregateRating",
              "ratingValue": 96,
              "bestRating": 100,
              "ratingCount": 88211
            }
          }
        }
      ]
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

## Guidelines

- [Carousel guidelines](/search/docs/appearance/structured-data/carousel#guidelines)
- [Search Essentials](/search/docs/essentials)
- [General structured data guidelines](/search/docs/appearance/structured-data/sd-policies)

## Structured data type definitions

### `Movie`

In addition to the [Carousel properties](/search/docs/appearance/structured-data/carousel), define the following properties in your Carousel object.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `image` | `URL` or `ImageObject` | An image that represents the movie. Must have a high resolution and 6:9 aspect ratio. |
| `name` | `Text` | The name of the movie. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `aggregateRating` | `AggregateRating` | Annotation for the average review score. Follow the [Review snippet guidelines](/search/docs/appearance/structured-data/review-snippet#guidelines). |
| `dateCreated` | `Date` or `DateTime` | The date the movie was released. |
| `director` | `Person` | The director of the movie. |
| `review` | `Review` | A nested `Review` of the movie. Follow the [Review snippet guidelines](/search/docs/appearance/structured-data/review-snippet#guidelines). |
