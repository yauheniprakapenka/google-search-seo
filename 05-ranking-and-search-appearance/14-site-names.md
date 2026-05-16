# Provide a site name to Google Search

> Source: https://developers.google.com/search/docs/appearance/site-names
> Last updated: 2025-12-10 UTC

When Google lists a page in search results, it shows the name of the site the page comes from. This is called the site name. Note that the site name is different from the per-page title links (title links are specific to each web page, whereas the site name is for the entire site).

## Feature availability

Site names are available in all languages where Google Search is available, on both mobile and desktop. Site names can appear for domain-level and subdomain-level sites.

## How site names in Google Search are created

Google's generation of site names on the Google Search results page is completely automated and takes into account content from a site's home page and references to it that appear on the web. The goal of the site name in Google Search is to best represent and describe the source of each result.

To indicate your site name preference, add `WebSite` structured data to your home page. Our site name system will also consider content in `og:site_name`, `<title>`, heading elements, and other text on a home page. However, `WebSite` structured data is most important, if you want to specify a preference.

## Choosing your site name

- **Choose a unique name** that accurately reflects the identity of your site and isn't misleading for users.
- **Use a concise, commonly-recognized name** for your site.
- **Avoid using a generic name**.
- **Use your site name consistently across your home page**.
- **Provide an alternative name** using the `alternateName` property.

## How to add a site name with structured data

### Technical guidelines

- **Only one name per site:** Currently, Google Search only supports one site name per site, where a *site* is defined by the domain or subdomain. Google Search does not support site names at the subdirectory level.
  - **Supported**: `https://example.com` (domain-level home page)
  - **Supported**: `https://www.example.com` (also domain-level)
  - **Supported**: `https://m.example.com` (also domain-level)
  - **Supported**: `https://news.example.com` (subdomain-level)
  - **Not supported**: `https://example.com/news` (subdirectory-level)
- **Structured data must be on the home page of a site:** The `WebSite` structured data must be on the home page of the site.
- **The home page must be crawlable by Google.**
- **For sites with duplicate home pages:** make sure that you're using the same structured data on all page duplicates.
- **If you already have `WebSite` structured data on your site**, make sure that you nest the site name properties in the same node.

### Add required site name properties

Required properties:
- `name` (Text) — The name of the website.
- `url` (URL) — The URL of the home page of the site.

JSON-LD example:
```json
{
  "@context" : "https://schema.org",
  "@type" : "WebSite",
  "name" : "Example",
  "url" : "https://example.com/"
}
```

### Add an alternative site name

Recommended property:
- `alternateName` (Text) — The alternate name of the website (for example, an acronym or shorter name).

Example with alternate names:
```json
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "name": "Burnt Toast",
  "alternateName": ["BT", "B-T", "Burnt Toast Shop"],
  "url": "https://www.example.com/"
}
```

## What to do if your preferred site name isn't selected

1. Verify the site name in `WebSite` structured data, check for errors, confirm it follows guidelines, and check other sources on your home page.
2. Make sure redirects are working and Googlebot can access the redirect target.
3. If you have multiple versions of your site, make sure you're using the same site name consistently.
4. Allow time for Google to recrawl and process updates (several days to several weeks).

If still not working:
1. Try providing an alternative name using `alternateName`.
2. Provide your domain or subdomain name as a backup option (in all lowercase).
3. As a last resort, provide your domain/subdomain name as the preferred name.
