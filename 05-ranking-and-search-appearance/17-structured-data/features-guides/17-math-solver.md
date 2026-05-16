# Math solver (`MathSolver`) structured data

> Source: <https://developers.google.com/search/docs/appearance/structured-data/math-solvers>

> Last updated: 2025-12-18 UTC

To help students, teachers, and others with math problems, you can use structured data to indicate the type of math problems and links to step-by-step walkthroughs for specific math problems.

## How to add structured data

Structured data is a standardized format for providing information about a page and classifying the page content. If you're new to structured data, you can learn more about [how structured data works](/search/docs/appearance/structured-data/intro-structured-data).

Here's an overview of how to build, test, and release structured data.

1. Add the [required properties](#structured-data-type-definitions). Based on the format you're using, learn where to [insert structured data on the page](/search/docs/appearance/structured-data/intro-structured-data#format-placement).
2. Follow the [guidelines](#guidelines).
3. Validate your code using the [Rich Results Test](https://search.google.com/test/rich-results) and fix any critical errors.
4. Deploy a few pages that include your structured data and use the [URL Inspection tool](https://support.google.com/webmasters/answer/9012289) to test how Google sees the page.
5. To keep Google informed of future changes, we recommend that you [submit a sitemap](/search/docs/crawling-indexing/sitemaps/build-sitemap).

## Examples

### One solver action

Here's an example of a math solver home page that has one solver action that can solve polynomial equations and derivative problems and is available in English and Spanish.

```html
<html>
<head>
<title>An awesome math solver</title>
</head>
<body>
<script type="application/ld+json">
[
  {
    "@context": "https://schema.org",
    "@type": ["MathSolver", "LearningResource"],
    "name": "An awesome math solver",
    "url": "https://www.mathdomain.com/",
    "usageInfo": "https://www.mathdomain.com/privacy",
    "inLanguage": "en",
    "potentialAction": [{
      "@type": "SolveMathAction",
      "target": "https://mathdomain.com/solve?q={math_expression_string}",
      "mathExpression-input": "required name=math_expression_string",
      "eduQuestionType": ["Polynomial Equation","Derivative"]
    }],
    "learningResourceType": "Math solver"
  },
  {
    "@context": "https://schema.org",
    "@type": ["MathSolver", "LearningResource"],
    "name": "Un solucionador de matemáticas increíble",
    "url": "https://es.mathdomain.com/",
    "usageInfo": "https://es.mathdomain.com/privacy",
    "inLanguage": "es",
    "potentialAction": [{
      "@type": "SolveMathAction",
      "target": "https://es.mathdomain.com/solve?q={math_expression_string}",
      "mathExpression-input": "required name=math_expression_string",
      "eduQuestionType": ["Polynomial Equation","Derivative"]
    }],
    "learningResourceType": "Math solver"
  }
]
</script>
</body>
</html>
```

### Two solver actions

Here's an example of a math solver home page that has two solver endpoints: one endpoint can solve polynomial equations and the other endpoint can solve trigonometric equations.

```json
{
  "@context": "https://schema.org",
  "@type": ["MathSolver", "LearningResource"],
  "name": "An awesome math solver",
  "url": "https://www.mathdomain.com/",
  "usageInfo": "https://www.mathdomain.com/privacy",
  "inLanguage": "en",
  "potentialAction": [{
    "@type": "SolveMathAction",
    "target": "https://mathdomain.com/solve?q={math_expression_string}",
    "mathExpression-input": "required name=math_expression_string",
    "eduQuestionType": "Polynomial Equation"
  },
  {
    "@type": "SolveMathAction",
    "target": "https://mathdomain.com/trig?q={math_expression_string}",
    "mathExpression-input": "required name=math_expression_string",
    "eduQuestionType": "Trigonometric Equation"
  }],
  "learningResourceType": "Math solver"
}
```

## Guidelines

For your page to be eligible for math solver rich results, you must follow these guidelines:

- [General structured data guidelines](/search/docs/appearance/structured-data/sd-policies)
- [Search Essentials](/search/docs/essentials)
- [Technical guidelines](#technical-guidelines)
- [Content guidelines](#content-guidelines)

### Technical Guidelines

- Add `MathSolver` structured data to the home page of your site.
- Ensure that Googlebot can [crawl your site efficiently](/search/docs/crawling-indexing/troubleshoot-crawling-errors#improve_crawl_efficiency).
- If you have several identical copies of the same math solver hosted under different URLs, use the [canonical URLs](/search/docs/crawling-indexing/consolidate-duplicate-urls) on each copy of the page.
- We don't allow math solvers that are entirely hidden behind a login or paywall. Once users navigate from the feature on Google to your site, the solution and a step-by-step walkthrough for their initial problem must be accessible to them. Additional content can be behind a login or paywall.

### Content guidelines

- We don't allow promotional content disguised as a math solver, such as those posted by a third party (for example, [affiliate programs](/search/docs/essentials/spam-policies#thin-affiliate-pages)).
- You are responsible for the accuracy and quality of your math solver through this feature. If a certain amount of your data is found to be inaccurate based on our quality review processes, then your solver may be removed from the feature until you resolve the issues depending on the severity. This applies to:
  - The accuracy of the problem types your solver is capable of solving.
  - The accuracy of your solutions for math problems your solver declares it can solve.

## Structured data type definitions

### MathSolver

A `MathSolver` is a tool that assists students, teachers, and others with math problems by laying out step-by-step solutions. Use `MathSolver` structured data on your site's home page.

The full definition of `MathSolver` is available at [schema.org/MathSolver](https://schema.org/MathSolver).

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `potentialAction` | `SolveMathAction` | The action that leads to a mathematical explanation of a math expression. |
| `potentialAction.mathExpression-input` | `Text` | A placeholder for a mathematical expression that is sent by Google to your website. The string can take many formats (e.g., LaTeX, Ascii-Math, or mathematical expressions). |
| `url` | `URL` | The URL of the `MathSolver`. |
| `usageInfo` | `URL` | The privacy policy for your math problem solving site. |
| `potentialAction.target` | `EntryPoint` | The URL target entrypoint for an action. |

**Recommended properties:**

| Property | Type | Description |
|----------|------|-------------|
| `inLanguage` | `Text` | The language(s) that are supported by your math problem solving site. |
| `assesses` | `Text` list | The problem type(s) that are solved with the `HowTo`. |
| `potentialAction.eduQuestionType` | `Text` list | The problem type(s) that are capable of being solved by the `potentialAction.target` property. |

### LearningResource

A `LearningResource` indicates that the subject of the markup is a resource that assists students, teachers, and others with educational learning.

**Required properties:**

| Property | Type | Description |
|----------|------|-------------|
| `learningResourceType` | `Text` | The type of this learning resource. Use this fixed value: `Math Solver`. |

## Problem Type Definitions

Use the following list of problem types as either the `eduQuestionType` for a `MathSolver.potentialAction` or for the `assesses` field.

| Problem Type | Description |
|-------------|-------------|
| `Absolute Value Equation` | Absolute value equations. E.g.: \|x - 5\| = 9 |
| `Algebra` | A generic problem type. E.g.: polynomial equations, exponential equations, and radical expressions. |
| `Arc Length` | Arc length problems. |
| `Arithmetic` | Arithmetic problems. E.g.: Find the sum of 5 + 7. |
| `Biquadratic Equation` | Biquadratic equations. E.g.: x^4 - x^2 - 2 = 0. |
| `Calculus` | A generic problem type. E.g.: integrals, derivatives, and differential equations. |
| `Characteristic Polynomial` | Find the characteristic polynomial. |
| `Circle` | Circle related problems. |
| `Derivative` | Derivative of 5x^4 + 2x^3 + 4x - 2. |
| `Differential Equation` | Differential equation problems. E.g.: y+dy/dx=5x. |
| `Distance` | Distance problems. |
| `Eigenvalue` | Eigenvalue problems. |
| `Eigenvector` | Eigenvector problems. |
| `Ellipse` | Ellipse problems. |
| `Exponential Equation` | Exponential equations. E.g.: 7^x = 9. |
| `Function` | Polynomial simplifications. |
| `Function Composition` | f(g(x)) when f(x)=x^2-2x, g(x)=2x-2. |
| `Geometry` | A generic problem type. E.g.: circle, ellipse, parabola, slope. |
| `Hyperbola` | Hyperbola problems. |
| `Inflection Point` | Find the inflection point. |
| `Integral` | Integral of sqrt (x^2 - y^2). |
| `Intercept` | Line intercept problems. |
| `Limit` | Limit problems. E.g.: Find the limit of x as x approaches 1. |
| `Line Equation` | Line equation problems. |
| `Linear Algebra` | A generic problem type. E.g.: matrix and characteristic polynomial. |
| `Linear Equation` | Linear equations. E.g.: 4x - 3 = 2x + 9. |
| `Linear Inequality` | Linear inequalities. E.g.: 5x - 6 > 3x - 8. |
| `Logarithmic Equation` | Logarithmic equations. E.g.: log(x) = log(100). |
| `Logarithmic Inequality` | Logarithmic inequalities. |
| `Matrix` | Matrix row reduce. |
| `Midpoint` | Midpoint problems. |
| `Parabola` | Parabola problems. |
| `Parallel` | Parallel line problems. |
| `Perpendicular` | Perpendicular problems. |
| `Polynomial Equation` | Polynomial equations. E.g.: x^5 - 3x = 0. |
| `Polynomial Expression` | Polynomial expressions. |
| `Polynomial Inequality` | Polynomial inequalities. |
| `Quadratic Equation` | Quadratic equations. E.g.: x^2 - 3x - 4 = 0. |
| `Quadratic Expression` | Quadratic expressions. |
| `Quadratic Inequality` | Quadratic inequalities. |
| `Radical Equation` | Radical equations. E.g.: sqrt(x) - x = 0. |
| `Radical Inequality` | Radical inequalities. |
| `Rational Equation` | Rational equations. E.g.: 5/(x - 3) = 2/(x - 1). |
| `Rational Expression` | Rational expressions. |
| `Rational Inequality` | Rational inequalities. |
| `Slope` | Slope problems. |
| `Statistics` | Statistics problems. |
| `System of Equations` | System of equations problems. |
| `Trigonometry` | Solve sin(t) + cos(t) = 1. |
