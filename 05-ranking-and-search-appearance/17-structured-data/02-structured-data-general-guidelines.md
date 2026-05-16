# General Structured Data Guidelines

> Source: https://developers.google.com/search/docs/appearance/structured-data/sd-policies
> Last updated: 2026-01-06 UTC

To be eligible for rich result appearance in Google Search results, structured data shouldn't violate the Content policies for Google Search (which include spam policies). In addition, this page details the general guidelines that apply to all structured data.

If your page contains a structured data issue, it can result in a manual action. A structured data manual action means that a page loses eligibility for appearance as a rich result; it doesn't affect how the page ranks in Google web search. To check if you have a manual action, open the [Manual Actions report in Search Console](https://search.google.com/search-console/manual-actions).

**Important: Google does not guarantee that your structured data will show up in search results**, even if your page is marked up correctly. Here are some common reasons why:

- Using structured data *enables* a feature to be present, it does not *guarantee* that it will be present.
- The structured data is not representative of the main content of the page, or is potentially misleading.
- The structured data is incorrect in a way that the Rich Results Test was not able to catch.
- The content referred to by the structured data is hidden from the user.
- The page doesn't meet the guidelines for structured data.

## Technical guidelines

You can test compliance with technical guidelines using the [Rich Results Test](https://search.google.com/test/rich-results) and the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289).

### Format

In order to be eligible for rich results, mark up your site's pages using one of three supported formats:

- **JSON-LD** (recommended)
- **Microdata**
- **RDFa**

### Access

Don't block your structured data pages to Googlebot using robots.txt, `noindex`, or any other access control methods.

## Quality guidelines

These quality guidelines are not easily testable using an automated tool. Violating a quality guideline can prevent syntactically correct structured data from being displayed as a rich result.

### Content

- Follow the [spam policies for Google web search](https://developers.google.com/search/docs/essentials/spam-policies).
- Provide up-to-date information. We won't show a rich result for time-sensitive content that is no longer relevant.
- Provide original content that you or your users have generated.
- **Don't** mark up content that is not visible to readers of the page.
- **Don't** mark up irrelevant or misleading content, such as fake reviews or content unrelated to the focus of a page.
- **Don't** use structured data to deceive or mislead users.
- Content in structured data must also follow the additional content guidelines or policies, as documented in the specific feature guide.

### Relevance

Your structured data must be a true representation of the page content. Examples of irrelevant data:

- A sports live streaming site labeling broadcasts as local events.
- A woodworking site labeling instructions as recipes.

### Completeness

- Specify all **required properties** listed in the documentation for your specific rich result type. Items that are missing required properties are not eligible for rich results.
- The more **recommended properties** that you provide, the higher quality the result is to users. Rich result ranking takes extra information into consideration.

### Location

- Put the structured data on the page that it describes, unless specified otherwise by the documentation.
- If you have duplicate pages for the same content, we recommend placing the same structured data on all page duplicates, not just on the canonical page.

### Specificity

- Try to use the most specific applicable type and property names defined by schema.org for your markup.
- Follow all additional guidelines given in the documentation for your specific rich result type.

### Images

- When specifying an image as a structured data property, make sure that the image is relevant to the page that it's on.
- All image URLs specified in structured data must be crawlable and indexable.

### Multiple items on a page

Multiple items on a page means that there is more than one kind of thing on a page. For example, a page could contain a recipe, a video, and breadcrumb information. All of this user-visible information can be marked up with structured data.

Google Search understands multiple items on a page, whether you **nest** the items or specify each item **individually**:

#### Nesting

When there is one main item, and additional items are grouped under the main item. This is particularly helpful when grouping related items (for example, a recipe with a video and reviews).

```html
<html>
  <head>
    <title>How To Make Banana Bread</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org/",
      "@type": "Recipe",
      "name": "Banana Bread Recipe",
      "description": "The best banana bread recipe you'll ever find!",
      "aggregateRating": {
        "@type": "AggregateRating",
        "ratingValue": 4.7,
        "ratingCount": 123
      },
      "video": {
        "@type": "VideoObject",
        "name": "How To Make Banana Bread",
        "description": "This is how you make banana bread, in 5 easy steps.",
        "contentUrl": "https://www.example.com/video123.mp4"
       }
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

#### Individual items

When each item is a separate block on the same page.

```html
<html>
  <head>
    <title>How To Make Banana Bread</title>
    <script type="application/ld+json">
    [{
      "@context": "https://schema.org/",
      "@type": "Recipe",
      "name": "Banana Bread Recipe",
      "description": "The best banana bread recipe you'll ever find!"
    },
    {
      "@context": "https://schema.org",
      "@type": "BreadcrumbList",
      "itemListElement": [{
        "@type": "ListItem",
        "position": 1,
        "name": "Recipes",
        "item": "https://example.com/recipes"
      },{
        "@type": "ListItem",
        "position": 2,
        "name": "Bread recipes",
        "item": "https://example.com/recipes/bread-recipes"
      },{
        "@type": "ListItem",
        "position": 3,
        "name": "How To Make Banana Bread"
      }]
    }]
    </script>
  </head>
  <body>
  </body>
</html>
```

#### Additional tips

- Include the main type of structured data that reflects the main focus of the page. For example, if a page is mainly about a recipe, include Recipe structured data in addition to Video and Review structured data.
- If there are items that are more helpful when they are linked together (for example, a recipe and a video), use `@id` in both items to specify that the video is about the recipe.
- Make sure all structured data items are complete. If you include multiple reviews, include all of the reviews that are visible to people on the page.
