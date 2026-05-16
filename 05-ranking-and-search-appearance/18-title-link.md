# Influencing your title links in search results

> Source: https://developers.google.com/search/docs/appearance/title-link
> Last updated: 2025-12-10 UTC

A *title link* is the title of a search result on Google Search and other properties (for example, Google News) that links to the web page. Google uses a number of different sources to automatically determine the title link, but you can indicate your preferences by following our best practices.

## Best practices for influencing title links

- Make sure **every page on your site has a title specified in the `<title>` element**.
- Write **descriptive and concise** text for your `<title>` elements. Avoid vague descriptors like "Home" for your home page, or "Profile" for a specific person's profile. Also avoid unnecessarily long or verbose text.
- Avoid **keyword stuffing**.
- Avoid **repeated or boilerplate text in `<title>` elements**. It's important to have distinct text that describes the content of the page in the `<title>` element for each page on your site.
- **Brand your titles** concisely. The `<title>` element on your site's home page is a reasonable place to include some additional information about your site. But displaying that text on every page will look repetitive. Consider including just your site name at the beginning or end of each `<title>` element, separated from the rest of the text with a delimiter such as a hyphen, colon, or pipe.
- **Make it clear which text is the main title** for the page. Google looks at various sources when creating title links, and it can be confusing if multiple headings carry the same visual weight and prominence.
- **Be careful about disallowing search engines** from crawling your pages. Using robots.txt can stop Google from crawling your pages, but it may not always prevent them from being indexed.
- **Use the same language and writing system** as the primary content on your pages.
- **Avoid including flight price information in `<title>` elements.**

## How title links in Google Search are created

Google Search uses the following sources to automatically determine title links:

- Content in `<title>` elements
- Main visual title shown on the page
- Heading elements, such as `<h1>` elements
- Content in `og:title` meta tags
- Other content that's large and prominent through the use of style treatments
- Other text contained in the page
- Anchor text on the page
- Text within links that point to the page
- `WebSite` structured data

## Common issues and how Google manages them

- **Half-empty `<title>` elements**: Google uses information from header elements or other prominent text.
- **Obsolete `<title>` elements**: Google detects inconsistencies and uses the correct date from the visible title.
- **Inaccurate `<title>` elements**: Google may modify the title link to better help users.
- **Micro-boilerplate text**: Google can detect distinguishing information in prominent text and insert it.
- **No clear main title**: If there are multiple prominent headings, Google may use the first one.
- **Mismatch of writing system or language**: Google may generate a title link that better matches the primary content.
- **Duplication of the site name**: Google may omit the site name from the title link if it's repetitive with the site name already shown in the search result.
