# Course list (`Course`) structured data

> Source: https://developers.google.com/search/docs/appearance/structured-data/course
> Last updated: 2025-12-10 UTC

With course list structured data, you can provide more information about your courses so that prospective students find your courses through Google Search. You can provide details including the course name, who's offering it, and a short description.

## Feature availability

The course list rich result is available in English in all regions where Google Search is available.

## How to add structured data

Structured data is a standardized format for providing information about a page and classifying the page content. Here's an overview of how to build, test, and release structured data.

1. Add the required properties. Based on the format you're using, learn where to insert structured data on the page.
2. Follow the guidelines.
3. Validate your code using the Rich Results Test.
4. Deploy a few pages and use the URL Inspection tool to test.
5. Submit a sitemap to keep Google informed of future changes.

## Examples

### Single course details page

Here's an example of a single course details page. This page must be paired with a summary page that contains the `ItemList` markup.

```html
<html>
  <head>
    <title>Introduction to Computer Science and Programming</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Course",
      "name": "Introduction to Computer Science and Programming",
      "description": "Introductory CS course laying out the basics.",
      "provider": {
        "@type": "Organization",
        "name": "University of Technology - Eureka",
        "sameAs": "https://www.example.com"
      }
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

### Single, all-in-one page

Here's an example of a single, all-in-one page. This page setup includes both the list markup and the details for each course on the same page.

```html
<html>
  <head>
    <title>Computer Science Courses</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "ItemList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "position": 1,
          "item": {
            "@type": "Course",
            "url":"https://www.example.com/courses#intro-to-cs",
            "name": "Introduction to Computer Science and Programming",
            "description": "This is an introductory CS course laying out the basics.",
            "provider": {
              "@type": "Organization",
              "name": "University of Technology - Example",
              "sameAs": "https://www.example.com"
            }
          }
        },
        {
          "@type": "ListItem",
          "position": 2,
          "item": {
            "@type": "Course",
            "url":"https://www.example.com/courses#intermediate-cs",
            "name": "Intermediate Computer Science and Programming",
            "description": "This is a CS course that builds on the basics learned in the Introduction course.",
            "provider": {
              "@type": "Organization",
              "name": "University of Technology - Example",
              "sameAs": "https://www.example.com"
            }
          }
        },
        {
          "@type": "ListItem",
          "position": 3,
          "item": {
            "@type": "Course",
            "url":"https://www.example.com/courses#advanced-cs",
            "name": "Advanced Computer Science and Programming",
            "description": "This CS course covers advanced programming principles.",
            "provider": {
              "@type": "Organization",
              "name": "University of Technology - Eureka",
              "sameAs": "https://www.example.com"
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

You must follow these guidelines to be eligible to appear in a course list.

- Content guidelines
- Technical guidelines
- Carousel guidelines
- Search Essentials
- General structured data guidelines

### Content guidelines

- Only use `Course` markup for educational content that fits the following definition of a course: A series or unit of curriculum that contains lectures, lessons, or modules in a particular subject and/or topic.
- A course must have an explicit educational outcome of knowledge and/or skill in a particular subject and/or topic, and be led by one or more instructors with a roster of students.
- A general public event such as "Astronomy Day" is not a course, and a single 2-minute "How to make a Sandwich Video" is not a course.

### Technical guidelines

- You must mark up at least three courses. The courses can be on separate detail pages, or in an all-in-one page.
- You must add Carousel markup to either a summary page or an all-in-one page.
- Each course must have valid `name` and `provider` properties. For example, the following naming practices are not valid:
  - Promotional phrases: "Best school in the world"
  - Prices in course titles: "Learn ukulele - only $30!"
  - Using something other than a course for a title
  - Discounts or purchase opportunities

## Structured data type definitions

### `Course`

Use the following properties to mark up at least three courses. The full definition of `Course` is available at schema.org/Course.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `description` | `Text` | A description of the course. Display limit of 60 characters. |
| `name` | `Text` | The title of the course. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `provider` | `Organization` | The organization that publishes the source content of the course. For example, UC Berkeley. |

### `ItemList`

In addition to `Course` properties, add the following properties to specify the list. The full definition of `ItemList` is available at schema.org/ItemList.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `itemListElement` | `ListItem` | Annotation for a single item page. |
| `ListItem.position` | `Integer` | Ordinal position of the item page in the list. |
| `ListItem.url` | `URL` | The canonical URL of the item page. Every item must have a unique URL. |
