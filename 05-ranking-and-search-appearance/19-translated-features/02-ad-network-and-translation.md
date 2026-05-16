# Enabling your ad network to work with translation-related Google Search features

> Source: https://developers.google.com/search/docs/appearance/ad-network-and-translation
> Last updated: 2025-12-10 UTC

Google Search offers several translation-related features that enable users to access translated content. If you run an ad network and your ads aren't working properly on translated web pages, you'll need to follow the steps in this guide to make sure your ads render or attribute correctly.

## Our approach

When users access translated content provided by Google Translate from within search results, Google retrieves the page from the publisher, rewrites the source URL, and translates the web page after the user clicks the translated result.

## Convert the Google Translate URL to the original URL

If you run an ad network that relies on the publisher's source URL, you'll need to convert the Google Translate URL to make sure your ads are working properly. Follow these steps to decode the publisher's hostname:

1. Extract the domain prefix from the hostname, by removing the `.translate.goog` suffix.
2. Split the `_x_tr_enc` parameter by the `,` (comma) character and save it as `encoding_list`.
3. Prepend the value of the `_x_tr_hp` parameter to the domain prefix, if it exists.
4. If `encoding_list` contains `1` and the output begins with `1-`, remove the `1-` prefix from the output of step 2.
5. If `encoding_list` contains `0` and the output begins with `0-`, remove the `0-` prefix from the output of step 3. If you removed the prefix, set `is_idn` to `true`. Otherwise, set `is_idn` to `false`.
6. Replace `/\b-\b/` (regex) with the `.` (dot) character.
7. Replace the `--` (double hyphen) character with the `-` (hyphen) character.
8. If `is_idn` is set to `true`, add the punycode prefix `xn--`.
9. **Optional**: Convert to Unicode.

## Reconstruct the URL

1. Using the original page URL, replace the hostname with the decoded hostname.
2. Remove all `_x_tr_*` parameters.
