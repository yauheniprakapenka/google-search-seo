# Article (`Article`, `NewsArticle`, `BlogPosting`) structured data

> Source: https://developers.google.com/search/docs/appearance/structured-data/article
> Last updated: 2025-12-10 UTC

Adding `Article` structured data to your news, blog, and sports article pages can help Google understand more about the web page and show better title text, images, and date information for the article in search results on Google Search and other properties (for example, Google News and the Google Assistant). While there's no markup requirement to be eligible for Google News features like Top stories, you can add `Article` to more explicitly tell Google what your content is about (for example, that it's a news article, who the author is, or what the title of the article is).

## Example

Here's an example of a page with `Article` structured data.

### JSON-LD

```html
<html>
  <head>
    <title>Title of a News Article</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "NewsArticle",
      "headline": "Title of a News Article",
      "image": [
        "https://example.com/photos/1x1/photo.jpg",
        "https://example.com/photos/4x3/photo.jpg",
        "https://example.com/photos/16x9/photo.jpg"
       ],
      "datePublished": "2024-01-05T08:00:00+08:00",
      "dateModified": "2024-02-05T09:20:00+08:00",
      "author": [{
          "@type": "Person",
          "name": "Jane Doe",
          "url": "https://example.com/profile/janedoe123"
        },{
          "@type": "Person",
          "name": "John Doe",
          "url": "https://example.com/profile/johndoe123"
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
<html>
  <head>
    <title>Title of a News Article</title>
  </head>
  <body>
    <div itemscope itemtype="https://schema.org/NewsArticle">
      <div itemprop="headline">Title of News Article</div>
      <meta itemprop="image" content="https://example.com/photos/1x1/photo.jpg" />
      <meta itemprop="image" content="https://example.com/photos/4x3/photo.jpg" />
      <img itemprop="image" src="https://example.com/photos/16x9/photo.jpg" />
      <div>
        <span itemprop="datePublished" content="2024-01-05T08:00:00+08:00">
          January 5, 2024 at 8:00am
        </span>
        (last modified
        <span itemprop="dateModified" content="2024-02-05T09:20:00+08:00">
          February 5, 2024 at 9:20am
        </span>
        )
      </div>
      <div>
        by
        <span itemprop="author" itemscope itemtype="https://schema.org/Person">
          <a itemprop="url" href="https://example.com/profile/janedoe123">
            <span itemprop="name">Jane Doe</span>
          </a>
        </span>
        and
        <span itemprop="author" itemscope itemtype="https://schema.org/Person">
          <a itemprop="url" href="https://example.com/profile/johndoe123">
            <span itemprop="name">John Doe</span>
          </a>
        </span>
      </div>
    </div>
  </body>
</html>
```

## How to add structured data

Structured data is a standardized format for providing information about a page and classifying the page content. If you're new to structured data, you can learn more about how structured data works.

Here's an overview of how to build, test, and release structured data.

1. Add as many recommended properties that apply to your web page. There are no required properties; instead, add the properties that apply to your content. Based on the format you're using, learn where to insert structured data on the page.
2. Follow the guidelines.
3. Validate your code using the Rich Results Test and fix any critical errors. Consider also fixing any non-critical issues that may be flagged in the tool.
4. Deploy a few pages that include your structured data and use the URL Inspection tool to test how Google sees the page.
5. To keep Google informed of future changes, we recommend that you submit a sitemap.

## Guidelines

You must follow these guidelines to enable structured data to be eligible for inclusion in Google Search results.

- Search Essentials
- General structured data guidelines
- Technical guidelines

### Technical guidelines

- For multi-part articles, make sure that the `rel=canonical` points at either each individual page or a "view-all" page (and not to page 1 of a multi-part series).
- If you offer subscription-based access to your website content, or if users must register for access, consider adding structured data for subscription and paywalled content.

## Structured data type definitions

To help Google better understand your page, include as many recommended properties that apply to your web page. There are no required properties; instead, add the properties that apply to your content.

### `Article` objects

Article objects must be based on one of the following schema.org types: `Article`, `NewsArticle`, `BlogPosting`.

The Google-supported properties are the following:

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `author` | `Person` or `Organization` | The author of the article. To help Google best understand authors across various features, we recommend following the author markup best practices. |
| `author.name` | `Text` | The name of the author. |
| `author.url` | `URL` | A link to a web page that uniquely identifies the author of the article. For example, the author's social media page, an "about me" page, or a bio page. |
| `dateModified` | `DateTime` | The date and time the article was most recently modified, in ISO 8601 format. |
| `datePublished` | `DateTime` | The date and time the article was first published, in ISO 8601 format. |
| `headline` | `Text` | The title of the article. Consider using a concise title, as long titles may be truncated on some devices. |
| `image` | Repeated `ImageObject` or `URL` | The URL to an image that is representative of the article. Use images that are relevant to the article, rather than logos or captions. Additional image guidelines: URLs must be crawlable and indexable; images must represent the marked up content; must be in a supported format; recommend multiple high-resolution images (minimum 50K pixels) with 16x9, 4x3, and 1x1 aspect ratios. |

Example of image property:

```json
"image": [
  "https://example.com/photos/1x1/photo.jpg",
  "https://example.com/photos/4x3/photo.jpg",
  "https://example.com/photos/16x9/photo.jpg"
]
```

## Author markup best practices

To help Google best understand and represent the author of the content, we recommend following these best practices when specifying authors in markup:

### Include all authors in the markup

Make sure that all the authors that are presented as authors on the web page are also included in markup.

### Specifying multiple authors

When specifying multiple authors, list each author in their own `author` field:

```json
"author": [
  {"name": "Willow Lane"},
  {"name": "Regula Felix"}
]
```

Don't merge multiple authors in the same `author` field:

```json
"author": {
  "name": "Willow Lane, Regula Felix"
}
```

### Use additional fields

To help Google better understand who the author is, we strongly recommend using the `type` and `url` (or `sameAs`) properties:

```json
"author": [
  {
    "@type": "Person",
    "name": "Willow Lane",
    "url": "https://www.example.com/staff/willow_lane"
  }
]
```

### Only specify the author's name in the `author.name` property

In the `author.name` property, only specify the name of the author. Don't add the name of the publisher, job title, honorific prefix/suffix, or introductory words.

```json
"author": [
  {
    "@type": "Person",
    "name": "Echidna Jones",
    "honorificPrefix": "Dr",
    "jobTitle": "Editor in Chief"
  }
],
"publisher": [
  {
    "@type": "Organization",
    "name": "Bugs Daily"
  }
]
```

### Use the appropriate `Type`

Use the `Person` type for people, and the `Organization` type for organizations. Don't use the `Thing` type.

Here's an example that applies the author markup best practices:

```json
"author": [
  {
    "@type": "Person",
    "name": "Willow Lane",
    "jobTitle": "Journalist",
    "url": "https://www.example.com/staff/willow-lane"
  },
  {
    "@type": "Person",
    "name": "Echidna Jones",
    "jobTitle": "Editor in Chief",
    "url": "https://www.example.com/staff/echidna-jones"
  }
],
"publisher": {
  "@type": "Organization",
  "name": "The Daily Bug",
  "url": "https://www.example.com"
}
```
