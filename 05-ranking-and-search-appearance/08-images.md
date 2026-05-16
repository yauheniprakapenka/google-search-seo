# Google image SEO best practices

> Source: https://developers.google.com/search/docs/appearance/google-images
> Last updated: 2026-03-02 UTC

Google provides several Search features and products that help users visually discover information on the web, such as the text result images, Google Discover, and Google Images. While each feature and product looks different, the general recommendations for getting images to appear in them is the same.

## Help us discover and index your images

The technical requirements for getting your content in Google's search results applies to images too. Since images are a substantially different format compared to HTML, it means there are additional requirements for getting images indexed.

### Use HTML image elements to embed images

Using standard HTML image elements helps crawlers find and process images. Google can find images in `src` attribute of `<img>` element (even when it's a child of other elements, such as the `<picture>` element). Google doesn't index CSS images.

Good: `<img src="puppy.jpg" alt="A golden retriever puppy" />`
Bad: `<div style="background-image:url(puppy.jpg)">A golden retriever puppy</div>`

### Use an image sitemap

You can provide the URL of images we might not have otherwise discovered by submitting an image sitemap. Unlike regular sitemaps, you can include URLs from other domains in the `<image:loc>` elements of the image sitemaps. This lets you use CDNs to host images.

### Responsive images

Designing responsive web pages leads to better user experience. Web pages use the `<picture>` element or the `srcset` attribute of an `img` element to specify responsive images. However, some browsers and crawlers don't understand these attributes. We recommend that you always specify a fallback URL using the `src` attribute.

### Use supported image formats

Google Search supports images in the following file formats: BMP, GIF, JPEG, PNG, WebP, SVG, and AVIF. It's also a good idea to have the extension of your filename match with the file type.

### Optimize for speed and quality

High-quality photos appeal to users more than blurry, unclear images. Also, sharp images are more appealing to users in the result thumbnail and can increase the likelihood of getting traffic from users. That said, images are often the largest contributor to overall page size, which can make pages slow and expensive to load. Make sure to apply the latest image optimization and responsive image techniques.

## Optimize the image landing pages

### Specify a preferred image with metadata

You can influence which image gets selected by providing your preferred image through one of the following metadata sources:

- Specify the schema.org `primaryImageOfPage` property with a `URL` or `ImageObject`.
- Or specify an image `URL` or `ImageObject` property and attach it to the main entity (using the schema.org `mainEntity` or `mainEntityOfPage` properties).
- Specify the `og:image` meta tag.

When choosing your preferred image, follow these best practices:
- Choose an image that's relevant and representative of the page.
- Avoid using a generic image (for example, your site logo) or an image with text.
- Avoid using an image with an extreme aspect ratio.
- Use a high resolution, if possible.

### Check your page title and description

Google Search automatically generates a title link and snippet to best explain each result and how it relates to the user query. You can help us improve the quality by following Google's title and snippet guidelines.

### Add structured data

If you include structured data, Google can display your images in certain rich results, including a prominent badge in Google Images, which give users relevant information about your page and can drive better targeted traffic to your site.

### Use descriptive filenames, titles, and alt text

Google extracts information about the subject matter of the image from the content of the page, including captions and image titles. Wherever possible, make sure images are placed near relevant text and on pages that are relevant to the image subject matter.

The most important attribute when it comes to providing more metadata for an image is the alt text (text that describes an image), which also improves accessibility for people who can't see images on web pages. Google uses alt text along with computer vision algorithms and the contents of the page to understand the subject matter of the image.

When writing alt text, focus on creating useful, information-rich content that uses keywords appropriately and is in context of the content of the page. Avoid filling `alt` attributes with keywords (keyword stuffing).

Bad (missing alt text): `<img src="puppy.jpg"/>`
Bad (keyword stuffing): `<img src="puppy.jpg" alt="puppy dog baby dog pup pups puppies..."/>`
Better: `<img src="puppy.jpg" alt="puppy"/>`
Best: `<img src="puppy.jpg" alt="Dalmatian puppy playing fetch"/>`

## Opt out of Google Images inline linking

You can prevent the full-sized image from appearing in the Google Images search results page by opting out of inline linking:

1. When your image is requested, examine the HTTP referrer header in the request.
2. If the request is coming from a Google domain, reply with a `200` HTTP status code, or a `204` HTTP status code and no content.

Google will still crawl your page and see the image, but will display a thumbnail image generated at crawl time in search results.

## Optimize for SafeSearch

SafeSearch is a setting in Google user accounts that specifies whether to show, blur, or block explicit images, videos, and websites in Google Search results. Make sure Google understands the nature of your site so that Google can apply SafeSearch filters to your site if appropriate.
