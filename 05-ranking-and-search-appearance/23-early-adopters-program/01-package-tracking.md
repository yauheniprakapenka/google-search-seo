# Package tracking Early Adopters Program

> Source: https://developers.google.com/search/docs/appearance/package-tracking
> Last updated: 2025-12-10 UTC

Package tracking is a feature that displays package tracking related information on Google. When people come to Search looking to track a package shipped with your company, they'll be able to enter a package ID directly. The feature uses your API to retrieve the package tracking information and then displays it to the user.

## Feature availability

Package tracking is available in all languages and countries where Google Search is available.

## Requirements

To be considered for participation in the package tracking early adopters program, you must meet the following requirements:

- Your package delivery company must either be based out of India, Japan, or Brazil, or must be the sole authorized provider of packing tracking information for a package delivery company that services those areas.
- Google Package Tracking makes real-time calls (POST requests only) to a RESTful JSON API to retrieve package tracking information. If you have an existing API that can return this information, we can work with you to re-use it.

### Availability and responsiveness

We expect almost no downtime from your API and require that your API respond within 700ms on average with the 95th percentile not exceeding 1,000ms.

### Content

Required field: `CurrentStatus` — The current status of the package including date, time, and error states.

Recommended fields: `DeliveredDate`, `PromisedDate`, `TrackingNumber`, `TrackingURL`, `SupportPhoneNumbers`, `TransitEvents`, `CreateDate`, `PickupDate`, `TimestampEvent`, `LocationEvent`, `CanReschedule`.

We don't accept: Any personal data about the recipient or sender, or any geographical information about the recipient or sender.
