## __Background__

The reviewed pipeline was created up in 2023 upon the roll-out of the updated GTM process early that year. It features one-off B2B sales of physical goods. Unlike many subscription products, there is no customer lock-in; repeat purchases depend entirely on ongoing customer loyalty. The company uses a one-meeting AE process for new sales-qualified leads (SQLs), with the BANT qualification decision to be made right after the first meeting.

### __Note on the data__ 

The initial dataset contains 934 CRM deals records created between 2023-02-10 and 2024-01-30 (the dataset cut-off date). Key limitations include significant data hygiene issues, e.g. 18% missing industry data, manually rounded headcount estimates, significant noise in separation between the new customer and the repeat purchases deals, and presence of extreme outliers in deal amounts and account headcounts. Confidence intervals for key metrics were estimated at .95, non-parametric methods such as Spearman's correlation were used in addition to linear methods to evaluate the relationships.

## __Executive Summary__ 

Outbound targeted largest accounts (median account size of 252 vs. Inbound's 65) but suffered low-end winrate (volume winrate 22% is significantly less than Inbound’s 38%, generally conforming to observable market trends). With median account size of 144, Field (conferences) targeted mid-size accounts, remaining likely limited by the accessible field events’ audiences. Winrates and deal close cycles for Field is on par with Inbound, however Field confidence intervals are broader to the upper as fewer datapoints available. Deal cycles for won and lost are highly spread-out irrespective of the channel, no reliable difference is observed between win and lost cycle times.  

It’s tempting to explain high Field performance - that is on par with Inbound for winrates and deal cycles - by the combination of the personal touch with the attractive material merchandise items being sold, however Field confidence intervals are on a broader side asking for more data.

Inbound shows a strong positive correletion between deal amount and account size, it is statistically significant. But Outbound and Field have weak weak to non-existent correlation. While Outbound and Field can steer us to bigger accounts, yet our current SQL-to-Opportunity-to-Close motion fails to capture the larger deal values from those larger accounts.

We can observe that regardless of the channel the winrates are in significant decline from the account size tier1 [0, 201) to tier2 and tier3 ([201, 901) and [901.0, inf)). This shows the AE team needs to address improving its skills in closing bigger new accounts.

### __Business Recommendations__  
- Audit Outbound SQL-Opportunity-Closing motion to identify the value leaks. Add SQL data to evaluate SQL->Opportunity conversions per channel. Sample and review manually of a cohort of high-size account outbound leads to reveal details of their journey. 
- Upon additional validation, consider crafting the dedicated Sales qualification - Deal creation - Closing cadences for high-size account leads, Outbound in the first place.

### __Technical recommendations__

- Enforce 1:1 FirstDeal-to-Company architecture; implement CRM validation rules to prevent multiple "first deals" from being attached to a single company account.
- Automate data enrichment integrating firmographic providers (e.g., ZoomInfo, Clearbit, Linkedin scraping API’s) to eliminate the 18% missing industry data and replace manually rounded headcount numbers with more accurate data.

### Business Metrics 
- Pipeline Volume, by Deal Source and Quarter.
- Win Rate by Volume, Median Deal Cycles.
- Account Size measured by company headcount.

## Data exploration and error correction

#### 1. 1st Deal-Account association

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/10_1st_deal_account_association.jpg" width=35% height=35%>

There multiple 1st deals related with one account (company) in the raw dataset, this is an error. For simple let's fix these by programmatically by creating a mask that keeps only the earliest created deal per company, reducing the raw dataset down to 391 valid first-time deals.

#### 2. Account industry not defined

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/20_account_industry_not_defined.jpg" width=80% height=80%>

Insight: Company (account) industry undefined for 70 or 18% of the total dataset accounts.

#### 3. Headcount Abnormal Frequencies

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/30_headcount_abnormal_frequencies.jpg" width=40% height=40%>

A frequency analysis of company headcount reveals sharp round numbers (e.g., 10.7% of deals listed exactly "50", others listed "200" or "500"). This highlights that sales reps are manually setting the account sizes and provides for the recommendation to automate firmographic data enrichment.

### Deal source performance

#### 4. 2023 Cohort Deals created

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/41_2023_deals_created.jpg" width=35% height=35%>

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/42_2023_deals_created.jpg" width=40% height=40%>

#### 5. Deals by Channel by Company (Account) size

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/50_deals_by_channel_by_company_size.jpg" width=70% height=70%>

Insight: A clear separation in targeting strategy emerges. Inbound attracts smaller accounts (Median Headcount = 65), while Outbound (Median Headcount = 252) and Field events (Median Headcount = 144) are successfully penetrating the mid-market and enterprise segments.

#### 6. Exploring linear relationships - Deal Amount vs. Headcount Scatterplots & Correlations

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/61_explore_linear_relationships.jpg">

Extreme outliers in Account HC and in the Deal Amounts obscure linear relationships for each of the channels. Trend’s confidence intervals look way too broad.  Pearson correlation coefficients:

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/62_pearson_corr.jpg" width=70% height=70%>

#### 7. Non-parametric test - Deal Amount vs. Headcount Scatterplots & Correlations

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/71_non_parametric_test.jpg">

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/72_spearman_corr.jpg" width=70% height=70%>

Inbound:  
Pearson: rho ~0.09 (p = 0.27) - Not statistically significant  
Spearman: rho ~0.36 (p < 0.00001) - Highly significant  
There is a clear, reliable positive relationship here, but it isn't linear. Likely outliers are breaking the Pearson calculation. However, the rank-order is consistent.

Outbound:  
Pearson: rho ~-0.01 (p = 0.88)  
Spearman: rho ~0.14 (p = 0.10)  
Neither test shows a significant relationship at the standard 95% confidence level (p < 0.05). The correlation is weak to non-existent. Outbound deals in this dataset don't seem to follow a predictable pattern based on the variables tested.

Field: 
Pearson: rho ~0.37 (p = 0.005) - Significant  
Spearman: rho ~0.19 (p = 0.16) - Not significant  
This is the opposite of Inbound, Pearson is strong but Spearman is weak. This usually means that a few massive outliers are driving the linear correlation. Data is limited here to 56 observations, Field results need to be taken with caution.

#### 8. Deal Winrates per channel

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/81_deal_winrates_per_channel.jpg" width=60% height=60%>

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/82_deal_winrates_per_channel.jpg" width=50% height=50%>

Winrates computed on the cohort of the deals closed within the 2023.
inbound winrate is statistically higher than Outbound, conforming to known market trends. Field may have same or higher WR as inbound likely cause of human touch and material goods being sold. Note confidence interval for Field that is broader ‘cause of the limited 41 deal observations.

#### 9. Deal Winrates per Account size tiers

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/91_deal_winrates_per_account_tier.jpg" width=60% height=60%>

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/92_deal_winrates_per_account_tier.jpg" width=50% height=50%>

#### 10. Deal Cycles

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/101_deal_cycles_per_account_tier.jpg" width=50% height=50%>

Inbound deals have a median closing time of 27 days, while outbound deals take 43 days - it is statistically significant. Field deals are similar to inbound at 30 days median, but their confidence interval extends more upward.

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/102_wonlost_deal_cycles_total.jpg" width=50% height=50%>

There is no significant difference in median close time between Won and Lost across all three channels, however bigger variance for won deal cycles is notable.  










