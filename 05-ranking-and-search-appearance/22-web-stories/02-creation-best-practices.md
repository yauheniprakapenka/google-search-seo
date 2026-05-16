# Best practices for creating Web Stories

> Source: https://developers.google.com/search/docs/appearance/web-stories-creation-best-practices
> Last updated: 2026-03-02 UTC

## Storytelling

**Critical:** Use video first — video is more engaging than text or images. Use as much video as possible, and supplement with images and text.

**Recommended:**
- Bring your perspective — go beyond the facts, share your opinions.
- Have a narrative arc — create suspense from one page to another.

## Design

**Critical:**
- Reduce your character count — avoid multiple pages with walls of text. Consider reducing text to approximately 280 characters per page.
- Don't block text — make sure text is not blocked by other content on the page. Avoid burned in text.
- Keep text within bounds — ensure that all text in your Web Story is visible to the reader.
- Use animations mindfully — avoid distracting or repetitive animations.

**Recommended:**
- Use Web Stories-specific call to action (not platform-specific CTAs).
- Use full bleed videos and images for a more immersive experience.
- Avoid low resolution or distorted images and videos.
- Add a logo to your cover page.
- Shorten video length — less than 15 seconds per page, or 60 seconds maximum.
- Include audio — use high-quality audio clips that are at least 5 seconds long.

## SEO

**Critical:**
- Provide high-quality content that is useful and interesting.
- Keep titles shorter than 90 characters (descriptive titles shorter than 70 characters recommended).
- Make sure Google Search can find your story — don't include a `noindex` attribute; add your Web Stories to your sitemap.
- Make the story self-canonical — each Web Story must have a `link rel="canonical"` to itself.
- Attach metadata — follow the AMP story metadata guidelines. Include `title` and `description` meta tags, structured data, OGP, and Twitter card.

**Recommended:**
- Include structured data in your Web Story.
- Include alt text on images.
- Integrate stories into your website — link them from your home page or category pages.
- Include subtitles on video.

## Technical

**Critical:**
- Make the story valid — Web Stories must be valid AMP pages.
- Don't include text in the poster image.
- Include the right poster image size and aspect ratio — at least 640x853px, aspect ratio 3:4.
- Include the right aspect ratio for the logo — at least 96x96 px, aspect ratio 1:1.

**Recommended:**
- Include `og:image` in your `<meta>` tags.
