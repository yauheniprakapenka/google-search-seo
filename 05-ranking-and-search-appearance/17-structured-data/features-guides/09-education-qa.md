# Education Q&A (`Quiz`, `Question`, and `Answer`) structured data

> Source: https://developers.google.com/search/docs/appearance/structured-data/education-qa
> Last updated: 2026-01-06 UTC

If you have flashcard pages, you can help students better find answers to educational questions by adding `Quiz` structured data to your flashcard pages. Adding structured data makes your content eligible to appear in the Q&A carousel in Google Search results, Google Assistant, and Google Lens results.

The following page types are eligible for the education Q&A carousel:

- **Flashcard page**: A page that contains flashcards that typically have a question on one side and an answer on the other side.
- **Single Q&A page**: A page that only contains one question and is followed by user-submitted answers. To mark up single Q&A pages, add `QAPage` markup instead.

## Feature availability

The education Q&A carousel is only available when searching for education-related topics on desktop and mobile.

Available languages and regions:

| Language | Available regions |
|----------|-------------------|
| English | All regions where Google Search is available |
| Portuguese | All regions where Google Search is available |
| Spanish | Mexico |
| Vietnamese | All regions where Google Search is available |

## How to add structured data

1. Add the required properties.
2. Follow the guidelines.
3. Validate your code using the Rich Results Test.
4. Deploy and test with URL Inspection tool.
5. Submit a sitemap.

## Examples

Here's an example of a flashcard page with education Q&A structured data.

```html
<html>
  <head>
    <title>Cell Transport</title>
    <script type="application/ld+json">
    {
      "@context": "https://schema.org/",
      "@type": "Quiz",
      "about": {
        "@type": "Thing",
        "name": "Cell Transport"
      },
      "educationalAlignment": [
        {
          "@type": "AlignmentObject",
          "alignmentType": "educationalSubject",
          "targetName": "Biology"
        }
      ],
      "hasPart": [
        {
          "@context": "https://schema.org/",
          "@type": "Question",
          "eduQuestionType": "Flashcard",
          "text": "This is some fact about receptor molecules.",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "receptor molecules"
          }
        },
        {
          "@context": "https://schema.org/",
          "@type": "Question",
          "eduQuestionType": "Flashcard",
          "text": "This is some fact about the cell membrane.",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "cell membrane"
          }
        }
      ]
    }
    </script>
  </head>
</html>
```

## Guidelines

- General structured data guidelines
- Search Essentials
- Technical guidelines
- Content guidelines

### Technical guidelines

- Put structured data on the most detailed leaf page possible. Don't add structured data to pages without questions.
- All questions must use the `Flashcard` value for the `eduQuestionType` property.
- Ensure that Googlebot can crawl your site efficiently.
- The questions on your site should be immediately visible to users on the page.
- If your page has only one question followed by several user-submitted answers, use `QAPage` markup instead.

### Content guidelines

- Education Q&A pages must follow the same content guidelines for Q&A pages.
- Your page must contain education related questions and answers. There must be at least one question and answer pairing.
- You are responsible for the accuracy and quality of your education Q&A pages.

## Structured data type definitions

### Quiz

A `Quiz` is a set of flashcards (one or more), which are typically about the same concept or subject. The full definition is provided on schema.org.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `hasPart` | `Question` | Nested information about the specific flashcard question for the quiz. Use one `hasPart` property to represent a single flashcard. To include multiple flashcards, repeat this property. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `about` | `Thing` | Nested information about the underlying concept behind the `Quiz`. |
| `about.name` | `Text` | The name of the underlying concept. Multiple entries allowed. |
| `educationalAlignment` | `AlignmentObject` | The quiz's alignment to an established educational framework. |
| `educationalAlignment.alignmentType` | `Text` | A category of alignment. Use `educationalSubject` for field of study and `educationalLevel` for target grade/standard. |
| `educationalAlignment.targetName` | `Text` | The name of a node of an established educational framework. |

### Question

Each question corresponds to one flashcard, nested under the `hasPart` property of `Quiz`.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `acceptedAnswer` | `Answer` | The full text of the answer to a flashcard. There must only be one `acceptedAnswer` per `Question`. |
| `eduQuestionType` | `Text` | The type of question. Must use the fixed value: `Flashcard`. |
| `text` | `Text` | The full text of the flashcard question. |
