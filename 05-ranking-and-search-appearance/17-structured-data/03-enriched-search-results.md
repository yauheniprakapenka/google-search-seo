# Enriched Search Results

> Source: https://developers.google.com/search/docs/appearance/enriched-search-results
> Last updated: 2025-12-10 UTC

In addition to standard rich results, Google Search supports a more interactive and enhanced class of rich result called *enriched search results*. Enriched search results often include an immersive experience or other advanced interaction feature.

Enriched search enables the user to search across the various properties of a structured data item; for example, a user might search for chicken soup recipes under 200 calories, or recipes that take less than 1 hour of preparation time.

## Implementing enriched search

Enriched search is a subset of rich results, and is implemented using structured data. Some rich result types are only available as enriched search types (for example, recipes, jobs, and events); other rich result types can be extended to be an enriched search type with the addition of a few properties.

You must follow:

- The [Structured data quality guidelines](./02-sd-policies.md)
- The Search Essentials
- The enriched search quality guidelines below

## Enriched search types

The following search types support an enriched search experience:

- [Job Posting](./features/job-posting.md)
- [Recipe](./features/recipe.md)
- [Event](./features/event.md)

## Enriched search quality guidelines

- **Required properties:** Each enriched search type defines a required set of properties. Items missing the required properties are ineligible.
- **Completeness:** The more additional (recommended) properties you provide, the higher quality the item is to users. Completeness is one of the most important ranking signals.
- **Relevance:** Your marked up data must be relevant to the enriched search you are participating in.
- **Leaf content:** Enriched search is only available for leaf pages, not for listing pages. A leaf page describes the detailed properties of an item. A listing page is a category page that links to multiple leaf pages.
- **Content policies:** Individual enriched search has additional content-type-specific policies.
