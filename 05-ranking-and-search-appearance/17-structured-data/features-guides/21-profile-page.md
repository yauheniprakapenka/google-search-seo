# Profile page (`ProfilePage`) structured data

> Source: <https://developers.google.com/search/docs/appearance/structured-data/profile-page>

> Last updated: 2025-12-10 UTC

`ProfilePage` markup is designed for any site where creators (either people or organizations) share first-hand perspectives. Adding this markup helps Google Search understand the creators that post in an online community, and show better content from that community in search results, including the [Discussions and Forums](https://blog.google/products/search/google-search-discussions-forums-news/) feature.

## How to add structured data

1. Add the [required properties](#structured-data-type-definitions). Based on the format you're using, learn where to [insert structured data on the page](/search/docs/appearance/structured-data/intro-structured-data#format-placement).
2. Follow the [guidelines](#guidelines).
3. Validate your code using the [Rich Results Test](https://search.google.com/test/rich-results).
4. Deploy a few pages and use the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289) to test.
5. To keep Google informed of future changes, [submit a sitemap](/search/docs/crawling-indexing/sitemaps/build-sitemap).

## Examples

### JSON-LD

```html
<html>
  <head>
    <title>Angelo Huff on Cool Forum Platform</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "ProfilePage",
      "dateCreated": "2024-12-23T12:34:00-05:00",
      "dateModified": "2024-12-26T14:53:00-05:00",
      "mainEntity": {
        "@type": "Person",
        "name": "Angelo Huff",
        "alternateName": "ahuff23",
        "identifier": "123475623",
        "interactionStatistic": [{
          "@type": "InteractionCounter",
          "interactionType": "https://schema.org/FollowAction",
          "userInteractionCount": 1
        },{
          "@type": "InteractionCounter",
          "interactionType": "https://schema.org/LikeAction",
          "userInteractionCount": 5
        }],
        "agentInteractionStatistic": {
          "@type": "InteractionCounter",
          "interactionType": "https://schema.org/WriteAction",
          "userInteractionCount": 2346
        },
        "description": "Defender of Truth",
        "image": "https://example.com/avatars/ahuff23.jpg",
        "sameAs": [
          "https://www.example.com/real-angelo",
          "https://example.com/profile/therealangelohuff"
        ]
      }
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
    <title>Angelo Huff on Cool Forum Platform</title>
  </head>
  <body itemtype="https://schema.org/ProfilePage" itemscope>
    <meta itemprop="dateCreated" content="2024-12-23T12:34:00-05:00" />
    <meta itemprop="dateModified" content="2024-12-26T14:53:00-05:00" />
    <div itemprop="mainEntity" itemtype="https://schema.org/Person" itemscope>
      <div><span itemprop="alternateName" id="handle">ahuff23</span> (<span itemprop="name" id="real-name">Angelo Huff</span>)</div>
      <meta itemprop="identifier" content="123475623" />
      <div itemprop="description">Defender of Truth</div>
      <img itemprop="image" src="https://example.com/avatars/ahuff23.jpg" />
      <div>Links: <a itemprop="sameAs" href="https://www.therealangelohuff.com">Home Page</a><br>
                  <a itemprop="sameAs" href="https://example.com/profile/therealangelohuff">Other Social Media Site</a></div>
    </div>
  </body>
</html>
```

## Guidelines

- [General structured data guidelines](/search/docs/appearance/structured-data/sd-policies)
- [Search Essentials](/search/docs/essentials)
- [Content Guidelines](#content-guidelines)
- [Technical Guidelines](#technical-guidelines)

### Content guidelines

The primary focus of the page must be a single person or organization that is affiliated with the overall website.

**Valid use cases:**
- A user profile page on a forum or social media site
- An author page on a news site
- An "About Me" page on a blog site
- An employee page on a company website

**Invalid use cases:**
- The main home page of a store
- An organization review site (the organization isn't associated with the website)

### Technical guidelines

If the profile page also includes the creator's recent activity, you can include markup using URLs on those objects to reference the page with the full content and markup.

```json
{
  "@context": "https://schema.org",
  "@type": "ProfilePage",
  "mainEntity": {
    "@id": "#main-author",
    "@type": "Person",
    "name": "Marlo Smith"
  },
  "hasPart": [{
    "@type": "Article",
    "headline": "Things to see in NJ",
    "url": "https://example.com/things-to-see-nj",
    "datePublished": "2014-02-23T18:34:00Z",
    "author": { "@id": "#main-author" }
  }]
}
```

## Structured data type definitions

### `ProfilePage`

The full definition of `ProfilePage` is available at [schema.org/ProfilePage](https://schema.org/ProfilePage).

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `mainEntity` | `Person` or `Organization` | The person or organization that this profile page is about. Use the correct type if available; otherwise default to `Person`. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `dateCreated` | `DateTime` | The date and time the profile was created, in ISO 8601. |
| `dateModified` | `DateTime` | The date and time the profile was modified, in ISO 8601. |

### `Person` or `Organization`

Both [schema.org/Person](https://schema.org/Person) and [schema.org/Organization](https://schema.org/Organization) share common properties.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `name` | `Text` | The primary way the person or organization is identified. If `name` isn't available, `alternateName` can fulfill this requirement. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `agentInteractionStatistic` | `InteractionCounter` | Statistics about the entity's own behavior. Recognized `interactionTypes`: `FollowAction`, `LikeAction`, `WriteAction`, `ShareAction`. |
| `alternateName` | `Text` | An alternate public identifier (e.g., social media handle). |
| `description` | `Text` | The user's byline or applicable credential. |
| `identifier` | `Text` | Any unique identifier used within your site. |
| `image` | `URL` or `ImageObject` | The URL of a profile image. Don't include default/placeholder images. |
| `interactionStatistic` | `InteractionCounter` | Statistics applied to the entity. Recognized `interactionTypes`: `FollowAction`, `LikeAction`, `BefriendAction`. |
| `sameAs` | `URL` | URLs to other external profiles or home pages. |
