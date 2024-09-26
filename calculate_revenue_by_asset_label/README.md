# Calculate Partner Revenue by Asset Label using Asset Revenue Reports

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YouTubeLabs/code-samples/blob/main/calculate_revenue_by_asset_label/calculate_revenue_by_asset_label.ipynb)

<br>

### Prerequisites
This colab to calculate your revenue by asset label is meant to work alongside the [Bulk Download Reports from the Reporting API colab](https://github.com/YouTubeLabs/code-samples/blob/main/authentication_and_report_bulk_download/authentication_and_report_bulk_download.ipynb) in this same [GitHub Repository](https://github.com/YouTubeLabs/code-samples) that downloads all of the available reports from a content owner into a `reports` folder in Google Drive.

<br>
<font color="red" size=5><strong>
Please note that this colab does not currently support asset label calculations for Music Publisher or Music Label content owners.
</strong></font>
<br>

## Types of Revenue by Asset Label

After you've downloaded your revenue reports from the YouTube Reporting API, you can calculate your revenue by asset label. The asset label field is only available in some revenue reports, so not all reports will be used in this script. This script uses the `partner_revenue` and `asset_labels` fields in the following revenue categories:

- [Ads Revenue](https://developers.google.com/youtube/reporting/v1/reports/system_managed/ads#aggregate-ad-revenue-per-asset)
- [Subscription Music Revenue](https://developers.google.com/youtube/reporting/v1/reports/system_managed/subscriptions#monthly-subscriptions-music-assets-revenue)
- [Subscription Non-Music Revenue](https://developers.google.com/youtube/reporting/v1/reports/system_managed/subscriptions#monthly-subscriptions-non-music-assets-revenue)
- [Ads Adjustment Revenue](https://developers.google.com/youtube/reporting/v1/reports/system_managed/ads#monthly-asset-ad-adjustment-revenue-summary)
- [Subscriptions Adjustment Music Revenue](https://developers.google.com/youtube/reporting/v1/reports/system_managed/subscriptions#monthly-music-asset-subscription-adjustment-revenue-raw)
- [Subscriptions Adjustment Non-Music Revenue](https://developers.google.com/youtube/reporting/v1/reports/system_managed/subscriptions#monthly-non-music-asset-subscription-adjustment-revenue-raw)

This colab does not take the following revenue categories or reports into account, and will need to be accounted for separately. Please check your [Payment Summary Report](https://support.google.com/youtube/answer/6085590?hl=en-GB#zippy=%2Cpayment-summary-report) for further details. This list is non-exhaustive.

- [Shorts Revenue](https://support.google.com/youtube/answer/6085590?hl=en-GB#zippy=%2Cshorts-revenue-report%2Cshorts-ads-report%2Cshorts-subscription-report)
- [Transactions](https://support.google.com/youtube/answer/6085590?hl=en-GB#zippy=%2Ctransactions-revenue-report)
- [Paid Features](https://support.google.com/youtube/answer/6085590?hl=en-GB#zippy=%2Cpaid-features-report)
- [Tax Withholding](https://support.google.com/youtube/answer/10391273?hl=en-GB&ref_topic=9257988&sjid=7232590298913281400-EU)
- [Channel Level Adjustments](https://support.google.com/youtube/answer/6085590?hl=en-GB#zippy=%2Cchannel-level-adjustment-report)

<font color="red" size=4><strong>
Use at your own risk: It is your responsibility to check that the revenue calculations of this colab are correct for your revenue and that all applicable revenue categories are accounted for.
</strong></font>