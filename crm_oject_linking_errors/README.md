## __Executive Summary__

Accurate revenue reporting relies on precise CRM data. In HubSpot, the "Deal Source" attribute distinguishes net-new business (e.g., Inbound, Outbound) from expansion revenue (Existing Customer). Misclassification here directly skews Customer Acquisition Cost (CAC) and marketing ROI metrics.  
This analysis visualizes the chronological timeline of deals across individual company accounts to identify attribution errors - such as subsequent deals being incorrectly tagged as net-new channels instead of existing business.

### __RevOps recommendations__

- Automate Data Validation: Implement a CRM workflow that automatically flags or restricts the creation of subsequent deals under an associated company if the "Deal Source" is set to anything other than "Existing Customer."

- Standardize Lead-to-Deal Mapping: Remove manual entry for the top-of-funnel "Deal Source" field where possible. For net-new deals, this should seamlessly auto-populate based on the originating Contact or Company lead source properties.

- Deploy Routine Audits: run this script on monhtly and quarterly basis to catch and correct attribution anomalies before month-end and quarter-end close.

## [View the chart in pdf](deal_source_plot_Create_date.pdf)
