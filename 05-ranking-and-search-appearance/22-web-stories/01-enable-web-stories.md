# Enable Web Stories on Google

> Source: https://developers.google.com/search/docs/appearance/enable-web-stories
> Last updated: 2025-12-10 UTC

Web Stories are a web-based version of the popular "Stories" format that blend video, audio, images, animation and text to create a dynamic consumption experience. This visual format lets you explore content at your own pace by tapping through it, or swiping from one piece of content to the next.

## Feature availability

Web Stories can appear as a single result on Google Search, which is available in all regions and languages where Google Search is available.

In the Discover feed, Web Stories can appear as a single card where you can tap through the story. While this appearance is available in all regions and languages where Google Discover is available, it's most likely to appear in the United States, India, and Brazil.

## Overview of how to enable Web Stories on Google

1. Create the Web Story.
2. Make sure the Web Story is valid AMP.
3. Verify the metadata.
4. Check if the Web Story is indexed.
5. Follow the Web Story Content Policies.

## Create the Web Story

Web Stories are web pages under the hood and must follow the same guidelines and best practices that apply to publishing regular web pages. There are two ways to get started:

- Pick one of several Story editor tools to start creating stories without any coding involved.
- If you have engineering resources, you can get started with AMP. To ensure your Web Story renders appropriately, we suggest using Chrome Developer Tools to simulate different device sizes and formats.

## Make sure the Web Story is valid AMP

After you've developed the story, make sure the Web Story is valid AMP. You can use the following tools:

- Web Stories Google Test Tool: Check that the Web Story is valid.
- URL Inspection Tool: Check that the Web Story is valid AMP and the Google indexing status of a URL.
- AMP Linter: Validate Web Stories during development via command line.

## Verify metadata

For your Web Stories to be eligible to appear on Google Search or Google Discover experiences, supply the necessary metadata to surface the Web Story in the preview.

Required fields on every Web Story: `publisher-logo-src`, `poster-portrait-src`, `title`, and `publisher`.

## Check if the Web Story is indexed

Check to see if Google Search has indexed your Web Story. Use the URL Inspection Tool to submit individual URLs or review status using Page Indexing report or Sitemaps report. If your Web Story isn't indexed:

1. Link to your Web Stories from your site or add your Web Story URL to your sitemap.
2. All Web Stories must be canonical. Make sure that each Web Story has a `link rel="canonical"` to itself.
3. Check to make sure the Web Story URL isn't blocked to Googlebot via robot.txt or the `noindex` tag.
