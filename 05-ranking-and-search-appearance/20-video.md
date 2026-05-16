# Video SEO best practices

> Source: https://developers.google.com/search/docs/appearance/video
> Last updated: 2025-12-18 UTC

If you have videos on your site, following these video SEO best practices can help more people find your site through video results on Google. Videos can appear in several different places on Google, including the main search results page, Video mode, Google Images, and Discover.

## Help Google find your videos

- Use HTML elements commonly used for embedding videos: `<video>`, `<embed>`, `<iframe>`, or `<object>`.
- Don't use fragment identifiers to load the video.
- If you're using JavaScript to inject the video, make sure that it appears in the rendered HTML.
- Don't rely on user actions (such as swiping, clicking, or typing) to load the video.

To make it easier for Google to find your videos, we recommend providing metadata about the video. We support structured data, video sitemaps, and the Open Graph protocol (OGP).

## Ensure your videos can be indexed

To be eligible for video features, a video must meet the following indexing requirements:

- The watch page must be indexed.
- The indexed watch page must be performing well in Search before its video can be considered for indexing.
- The video must be embedded on a watch page.
- The video can't be hidden behind other elements.
- The video must have a valid thumbnail that's available at a stable URL.

### Use a supported video file type

Google can process: 3GP, 3G2, ASF, AVI, DivX, M2V, M3U, M3U8, M4V, MKV, MOV, MP4, MPEG, OGV, QVT, RAM, RM, VOB, WebM, WMV, and XAP. Data URLs aren't supported.

### Use stable URLs

Some CDNs use quickly expiring URLs. If the video's thumbnail URL changes too often, Google may not be able to successfully index your videos. Use a single unique and stable thumbnail URL for each video.

### Create a dedicated watch page for each video

A *watch page*'s main purpose is to show users a single video. To be eligible for video features, create a dedicated watch page for each video, if it makes sense for your business.

## Which URL is which?

- **Watch page**: The URL of the watch page that's embedding the video.
- **Video player**: The URL of a specific player for the video (often the `src` value for an `<iframe>`).
- **Video file**: The URL of the video file's actual content bytes.

## Enable specific video features

### Video previews

Google selects a few seconds from your video to display a moving preview. To make your videos eligible, allow Google to fetch your video files. You can set the maximum duration using the `max-video-preview` robots meta tag.

### Key moments

The key moments feature is a way for users to navigate video segments like chapters in a book. Google Search tries to automatically detect segments. Alternatively, you can tell Google about the important points through `Clip` structured data, `SeekToAction` structured data, or YouTube description timestamps.

### Live Badge

For livestreaming videos, you can enable a red "LIVE" badge by using `BroadcastEvent` structured data.

## Allow Google to fetch your video files

Google needs to successfully fetch the actual bytes of a video file to enable features like video previews and key moments. Best practices:

- Allow Google to fetch the video's streaming file URL. Don't block it with `noindex` or robots.txt.
- The video file must be available at a stable URL.
- Use structured data to provide the `contentURL` value of a supported file type.
- The host of the video watch page and the streaming server must have enough resources.

## Remove or restrict your videos

### Remove a video

- Return a `404 (Not found)` for any watch page embedding the removed video.
- Include a `noindex` robots meta tag on any watch page embedding a removed video.
- Indicate an expiration date in structured data (`expires` property) or video sitemap (`<video:expiration_date>`).

### Restrict a video based on the user's location

You can restrict search results for your video based on the user's location using structured data (`regionsAllowed` or `ineligibleRegion` properties) or video sitemap (`<video:restriction>` tag).

## Monitor video watch pages with Search Console

- **Video indexing report**: See how many indexed watch pages contain an indexed video.
- **Video rich result report**: Review and fix issues with your `VideoObject` structured data.
- **Performance report**: Use the Videos search appearance filter to monitor performance.
