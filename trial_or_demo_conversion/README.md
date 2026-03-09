## Background
This analysis evaluates the effectiveness of two primary Call-to-Action (CTA) strategies for a B2B: starting a free trial versus booking a sales demo. By analyzing historical CRM data encompassing prospect contacts and their associated companies, we aim to determine which initial engagement method yields a higher lead-to-customer conversion rate. This insight will help optimize the marketing funnel, allocate sales resources efficiently, and drive revenue growth.

### Note on the Dataset
The dataset comprises 5,000 unique CRM contacts and 3,266 companies. A lack of reliable relational IDs required merging records based on email domain matching. Missing timestamp data for funnel events required imputation to facilitate chronological comparisons.

## Executive Summary
Our analysis answered a common pipeline question: Do prospect customers convert at a higher rate when their first interaction is a free trial or a demo? The data reveals that companies initiating a free trial convert at 13.16%, compared to 11.05% for those starting with a demo. This 2.1% absolute lift represents a nearly 19% relative increase in conversion likelihood. While the statistical significance sits just outside the strict 95% confidence threshold (p-value: 0.07), the substantial business upside—a 19% boost in customer acquisition—strongly supports prioritizing the free-trial funnel in top-of-funnel marketing efforts.

## Business Recommendations:

- __Prioritize Trial CTAs.__ Shift top-of-funnel website design and marketing spend to heavily feature the Free Trial CTA, as it demonstrates a stronger pull to closed-won revenue.

- __Monitor Downstream Quality.__ Track the post-conversion metrics (e.g., Net Revenue Retention, Churn Rate) of both cohorts to ensure the higher volume of trial conversions translates into sustainable Long-Term Value gain.

### Business Metrics Evaluated
Lead-to-Customer Conversion Rate, Absolute and Relative Conversion Lift, Confidence Intervals.

#### Conversion estimates with .95 confidence intervals

<img src="https://github.com/outovhush/revops-portfolio/blob/main/trial_or_demo_conversion/conversion_likelihood.jpg" width=35% height=35%>

The plot shows that companies starting with a trial generally have a higher likelihood of conversion than those starting with a demo, but the slight overlap in confidence intervals (CIs) adds a layer of nuance to the statistical significance.  
The point estimate for "trial" (~0.132) is well outside the "demo" interval, and vice versa. This suggests that while there is some uncertainty, there is a strong probability that the trial group truly converts at a higher rate.

#### Chi-squared test and p-value

<img src="https://github.com/outovhush/revops-portfolio/blob/main/trial_or_demo_conversion/contingency_table.jpg" width=35% height=35%>

The Statistical Verdict: we use threshold of 0.05 is used to determine significance. Our Result: p-value = 0.0724. Since 0.0724 > 0.05, we fail to reject the null hypothesis.  
In plain English, we cannot say with 95% certainty that the "Trial" converts better than the "Demo" group.  
 
Despite the lack of a statistical rigor, the data still tells a compelling story:  
Trial Conversion: 13.16% (206 / 1565)  
Demo Conversion: 11.05% (188 / 1701)  
The Lift: The Trial group is converting roughly 19% better than the Demo group in relative terms. There is a 7.24% chance that the 2.1% observed is just "noise" or random luck.


