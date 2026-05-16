# Control your snippets in search results

> Source: https://developers.google.com/search/docs/appearance/snippet
> Last updated: 2026-04-20 UTC

A *snippet* is the description or summary part of search result on Google Search and other properties (for example, Google News). Google primarily uses the content on the page to automatically determine the appropriate snippet. We may also use descriptive information in the meta description element when it describes the page better than other parts of the content.

## How snippets are created

Snippets are automatically created from page content. Snippets are designed to emphasize and preview the page content that best relates to a user's specific search. This means that Google Search might show different snippets for different searches.

Snippets are primarily created from the page content itself. However, Google sometimes uses the meta description HTML element if it might give users a more accurate description of the page than content taken directly from the page.

## How to prevent snippets or adjust snippet length

You can prevent snippets from being created and shown for your site in search results, or let Google know about the maximum lengths that you want your snippets to be. To prevent Google from displaying a snippet for your page in search results, use the `nosnippet` meta tag. To specify the maximum length for your snippets, use the `max-snippet:[number]` meta tag. You can also prevent certain parts of the page from being shown in a snippet by using the `data-nosnippet` attribute.

## Best practices for creating quality meta descriptions

Google will sometimes use the `<meta name="description">` tag from a page to generate a snippet in search results, if we think it gives users a more accurate description than would be possible purely from the on-page content.

### Create unique descriptions for each page on your site

Identical or similar descriptions on every page of a site aren't helpful when individual pages appear in search results. Wherever possible, create descriptions that accurately describe the specific page. Use site-level descriptions on the main home page or other aggregation pages, and use page-level descriptions everywhere else.

### Include relevant information about the content in the description

The meta description doesn't just have to be in sentence format; it's also a great place to include information about the page. For example, news or blog postings can list the author, date of publication, or byline information. Similarly, product pages might have the key bits of information—price, age, manufacturer—scattered throughout a page. A good meta description can bring all this data together.

Example:
```html
<meta name="description" content="Written by A.N. Author, Illustrated by V. Gogh, Price: $17.99, Length: 784 pages">
```

### Programmatically generate descriptions

For larger database-driven sites, like product aggregators, hand-written descriptions can be impossible. In the latter case, programmatic generation of the descriptions can be appropriate and are encouraged. Good descriptions are human-readable and diverse.

### Use quality descriptions

Make sure your descriptions are truly descriptive. High-quality descriptions can be displayed in Google's search results, and can go a long way to improving the quality and quantity of your search traffic.

Examples of good vs bad meta descriptions:

Bad (list of keywords):
```html
<meta name="description" content="Sewing supplies, yarn, colored pencils, sewing machines, threads, bobbins, needles">
```

Better (explains what the shop sells):
```html
<meta name="description" content="Get everything you need to sew your next garment. Open Monday-Friday 8-5pm, located in the Fashion District.">
```

## Best practices for "Read more" deep links in Google Search

A "Read more" deep link is a link within a snippet that leads users to a specific section on that page. To increase the likelihood that "read more" deep links appear:

- Make sure content is immediately visible on the page to a human (and not hidden behind an expandable section or tabbed interface).
- Avoid using JavaScript to control the user's scroll position on page load.
- If you make history API calls or window.location.hash modifications on page load, make sure you don't remove the hash fragment from the URL, as this breaks deep linking behavior.
