# Organization (`Organization`) structured data

> Source: <https://developers.google.com/search/docs/appearance/structured-data/organization>

> Last updated: 2026-04-15 UTC

Adding organization structured data to your home page can help Google better understand your organization's administrative details and disambiguate your organization in search results. Some properties are used behind the scenes to disambiguate your organization from other organizations (like `iso6523` and `naics`), while others can influence visual elements in Search results (such as which `logo` is shown in Search results and your [knowledge panel](https://support.google.com/knowledgepanel/answer/9163198)). There are no required properties; instead, we recommend adding as many properties that are relevant to your organization.

## How to add structured data

1. Add as many [recommended properties](#structured-data-type-definitions) that apply to your web page. There are no required properties; instead, add the properties that apply to your content.
2. Follow the [guidelines](#guidelines).
3. Validate your code using the [Rich Results Test](https://search.google.com/test/rich-results).
4. Deploy a few pages that include your structured data and use the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289) to test how Google sees the page.
5. To keep Google informed of future changes, we recommend that you [submit a sitemap](/search/docs/crawling-indexing/sitemaps/build-sitemap).

## Examples

### `Organization`

```html
<html>
  <head>
    <title>About Us</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Organization",
      "url": "https://www.example.com",
      "sameAs": ["https://example.net/profile/example1234", "https://example.org/example1234"],
      "logo": "https://www.example.com/images/logo.png",
      "name": "Example Corporation",
      "description": "The example corporation is well-known for producing high-quality widgets",
      "email": "contact@example.com",
      "telephone": "+47-99-999-9999",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "Rue Improbable 99",
        "addressLocality": "Paris",
        "addressCountry": "FR",
        "addressRegion": "Ile-de-France",
        "postalCode": "75001"
      },
      "vatID": "FR12345678901",
      "iso6523Code": "0199:724500PMK2A2M1SQQ228"
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

### `OnlineStore` with shipping policy and return policy

```html
<html>
  <head>
    <title>About Us</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "OnlineStore",
      "name": "Example Online Store",
      "url": "https://www.example.com",
      "sameAs": [
        "https://example.net/profile/example12",
        "https://example.org/@example34"
      ],
      "logo": "https://www.example.com/assets/images/logo.png",
      "contactPoint": {
        "contactType": "Customer Service",
        "email": "support@example.com",
        "telephone": "+47-99-999-9900"
      },
      "vatID": "FR12345678901",
      "iso6523Code": "0199:724500PMK2A2M1SQQ228",
      "hasMerchantReturnPolicy": {
        "@type": "MerchantReturnPolicy",
        "applicableCountry": ["FR", "CH"],
        "returnPolicyCategory": "https://schema.org/MerchantReturnFiniteReturnWindow",
        "merchantReturnDays": 60,
        "returnMethod": "https://schema.org/ReturnByMail",
        "returnFees": "https://schema.org/FreeReturn",
        "refundType": "https://schema.org/FullRefund"
      }
    }
    </script>
  </head>
  <body>
  </body>
</html>
```

## Guidelines

- [Technical guidelines](#technical-guidelines)
- [Search Essentials](/search/docs/essentials)
- [General structured data guidelines](/search/docs/appearance/structured-data/sd-policies)

### Technical guidelines

We recommend placing this information on your home page, or a single page that describes your organization, for example the *about us* page. You don't need to include it on every page of your site.

We recommend using the most specific schema.org subtype of [`Organization`](https://schema.org/Organization) that matches your organization. For example, if you have an ecommerce site, then we recommend using the [`OnlineStore`](https://schema.org/OnlineStore) subtype.

## Structured data type definitions

Google recognizes the following properties of an [`Organization`](https://schema.org/Organization). There are no required properties; instead, add the properties that apply to your organization.

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `address` | `PostalAddress` | The address of your organization. Include all properties that apply to your country. |
| `address.addressCountry` | `Text` | Two-letter ISO 3166-1 alpha-2 country code. |
| `address.addressLocality` | `Text` | The city. |
| `address.addressRegion` | `Text` | The region (e.g., state). |
| `address.postalCode` | `Text` | The postal code. |
| `address.streetAddress` | `Text` | The full street address. |
| `alternateName` | `Text` | Another common name that your organization goes by. |
| `contactPoint` | `ContactPoint` | The best way for a user to contact your business. |
| `contactPoint.email` | `Text` | The email address. |
| `contactPoint.telephone` | `Text` | The phone number with country code. |
| `description` | `Text` | A detailed description of your organization. |
| `duns` | `Text` | The Dun & Bradstreet DUNS number. Prefer `iso6523Code` with prefix `0060:`. |
| `email` | `Text` | The email address to contact your business. |
| `foundingDate` | `Date` | The date founded in ISO 8601 format. |
| `globalLocationNumber` | `Text` | The GS1 Global Location Number. |
| `hasMerchantReturnPolicy` | `MerchantReturnPolicy` | The return policy. |
| `hasMemberProgram` | `MemberProgram` | A member (loyalty) program. |
| `hasShippingService` | `ShippingService` | The shipping policy. |
| `iso6523Code` | `Text` | The ISO 6523 identifier (ICD:identifier format). Common ICDs: `0060` (DUNS), `0088` (GLN), `0199` (LEI). |
| `legalName` | `Text` | The registered legal name if different from `name`. |
| `leiCode` | `Text` | The ISO 17442 identifier. Prefer `iso6523Code` with prefix `0199:`. |
| `logo` | `URL` or `ImageObject` | A logo representative of your organization. Minimum 112x112px. |
| `naics` | `Text` | The NAICS code. |
| `name` | `Text` | The name of your organization. |
| `numberOfEmployees` | `QuantitativeValue` | The number of employees (specific or range). |
| `sameAs` | `URL` | URLs to additional info pages (social media, review sites). |
| `taxID` | `Text` | The tax ID. Must match the country in `address`. |
| `telephone` | `Text` | Primary business phone number with country code. |
| `url` | `URL` | The website URL of your organization. |
| `vatID` | `Text` | The VAT code. |
