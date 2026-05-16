# A guide to Google Search ranking systems

> Source: https://developers.google.com/search/docs/appearance/ranking-systems-guide
> Last updated: 2025-12-10 UTC

Google uses automated ranking systems that look at many factors and signals about hundreds of billions of web pages and other content in our Search index to present the most relevant, useful results, all in a fraction of a second.

Our ranking systems are designed to work on the page level, using a variety of signals and systems to understand how to rank individual pages. Site-wide signals and classifiers are also used and contribute to our understanding of pages.

## Active systems

### BERT
Bidirectional Encoder Representations from Transformers (BERT) is an AI system Google uses that allows us to understand how combinations of words express different meanings and intent.

### Crisis information systems
Google has developed systems to provide helpful and timely information during times of crisis:
- **Personal crisis:** Our systems work to understand when people are seeking information about personal crisis situations to display hotlines and content from trusted organizations for certain queries related to suicide, sexual assault, poison ingestion, gender-based violence, or drug addiction.
- **SOS Alerts:** During times of natural disasters or wide-spread crisis situations, our SOS Alerts system works to show updates from local, national, or international authorities.

### Deduplication systems
Searches on Google may find thousands or even millions of matching web pages. Some of these may be very similar to each other. In such cases, our systems show only the most relevant results to avoid unhelpful duplication. Deduplication also happens with featured snippets — if a web page listing is elevated to become a featured snippet, we don't repeat the listing later on the first page of results.

### Exact match domain system
Our ranking systems consider the words in domain names as one of many factors to determine if content is relevant to a search. However, our exact match domain system works to ensure we don't give too much credit for content hosted under domains designed to exactly match particular queries.

### Freshness systems
We have various "query deserves freshness" systems designed to show fresher content for queries where it would be expected.

### Link analysis systems and PageRank
We have various systems that understand how pages link to each other as a way to determine what pages are about and which might be most helpful in response to a query. Among these is PageRank, one of our core ranking systems used when Google first launched.

### Local news systems
We have systems that work to identify and surface local sources of news whenever relevant, such as through our "Top stories" and "Local news" features.

### MUM
Multitask Unified Model (MUM) is an AI system capable of both understanding and generating language. It's not currently used for general ranking in Search but rather for some specific applications such as to improve searches for COVID-19 vaccine information and to improve featured snippet callouts.

### Neural matching
Neural matching is an AI system that Google uses to understand representations of concepts in queries and pages and match them to one another.

### Original content systems
We have systems to help ensure we are showing original content prominently in search results, including original reporting, ahead of those who merely cite it.

### Removal-based demotion systems
If we process a significant volume of removals involving a particular site, we use that as a signal to improve our results:
- **Legal removals:** When we receive a significant volume of valid copyright removal requests involving a given site, we are able to use that to demote other content from the site.
- **Personal information removals:** If we process a significant volume of personal information removals involving a site with exploitative removal practices, we demote other content from the site.

### Passage ranking system
Passage ranking is an AI system we use to identify individual sections or "passages" of a web page to better understand how relevant a page is to a search.

### RankBrain
RankBrain is an AI system that helps us understand how words are related to concepts. It means we can better return relevant content even if it doesn't contain all the exact words used in a search.

### Reliable information systems
Multiple systems work in various ways to show the most reliable information possible, such as to help surface more authoritative pages and demote low-quality content.

### Reviews system
The reviews system aims to better reward high quality reviews, content that provides insightful analysis and original research, and is written by experts or enthusiasts who know the topic well.

### Site diversity system
Our site diversity system works so that we generally won't show more than two web page listings from the same site in our top results.

### Spam detection systems
We employ a range of spam detection systems, including SpamBrain, to deal with content and behaviors that violate our spam policies.

## Retired systems

### Helpful content system
Announced in 2022, this system designed to better ensure people see original, helpful content written by people, for people. In March 2024, it evolved and became part of our core ranking systems.

### Hummingbird
A major improvement to our overall ranking systems made in August 2013.

### Panda system
Designed to better ensure high-quality and original content was appearing in our search results. Announced in 2011, it evolved and became part of our core ranking systems in 2015.

### Penguin system
Designed to combat link spam. Announced in 2012, it was integrated into our core ranking systems in 2016.
