# Generate Structured Data with JavaScript

> Source: https://developers.google.com/search/docs/appearance/structured-data/generate-structured-data-with-javascript
> Last updated: 2025-12-10 UTC

Modern websites use JavaScript to display lots of dynamic content. There are a few things you need to look out for when using JavaScript to generate structured data on your websites.

There are different ways to generate structured data with JavaScript, but the most common are:

- **Google Tag Manager**
- **Custom JavaScript**

**Using `Product` markup?** Dynamically-generated markup can make Shopping crawls less frequent and less reliable, which can be an issue for fast-changing content like product availability and price.

## Use Google Tag Manager to generate JSON-LD dynamically

[Google Tag Manager](https://tagmanager.google.com/) is a platform that lets you manage tags on your website without editing the code.

1. Set up and install Google Tag Manager on your site.
2. Add a new **Custom HTML** tag to the container.
3. Paste a supported structured data block into the tag content.
4. Install the container as shown in the Install Google Tag Manager section.
5. Publish your container in the Google Tag Manager interface.
6. Test your implementation.

### Using variables in Google Tag Manager

GTM supports variables to use information on the page as part of your structured data. Use variables to extract the structured data from the page instead of duplicating the information in GTM.

Example custom variable `recipe_name`:

```javascript
function() { return document.title; }
```

Use `{{recipe_name}}` in your custom tag HTML:

```html
<script type="application/ld+json">
  {
    "@context": "https://schema.org/",
    "@type": "Recipe",
    "name": "{{recipe_name}}",
    "image": [ "{{recipe_image}}" ],
    "author": {
      "@type": "Person",
      "name": "{{recipe_author}}"
    }
  }
</script>
```

## Generate structured data with custom JavaScript

Google Search can understand and process structured data that's available in the DOM when it renders the page.

```javascript
fetch('https://api.example.com/recipes/123')
.then(response => response.text())
.then(structuredDataText => {
  const script = document.createElement('script');
  script.setAttribute('type', 'application/ld+json');
  script.textContent = structuredDataText;
  document.head.appendChild(script);
});
```

## Using server-side rendering

If you are using server-side rendering, you can also include the structured data in the rendered output.

## Test your implementation

1. Open the [Rich Results Test](https://search.google.com/test/rich-results).
2. Enter the URL that you want to test. Use the URL input instead of the code input.
3. Click **Test URL**.
   - **Success**: "Page is eligible for rich results".
   - **Try again**: Check for syntax errors or missing properties.
