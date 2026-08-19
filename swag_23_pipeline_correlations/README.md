## __Background__

The reviewed pipeline was created up in 2023 upon the roll-out of the updated GTM process early that year. It features one-off B2B sales of physical goods. Unlike many subscription products, there is no customer lock-in; repeat purchases depend entirely on ongoing customer loyalty. The company uses a one-meeting AE process for new sales-qualified leads (SQLs), with the BANT qualification decision to be made right after the first meeting.

### Metrics reviewed: 
- Pipeline Volume by Deal Source.
- Win Rate by Volume, Median Deal Cycles.
- Account (Company) Size measured by Headcount.

## __Executive Summary__ 

Inbound channel shows a strong positive correletion between deal amount (AoL) and the account size, Outbound and Field have weak to non-existent correlation. While Outbound and Field can potentially steer us to bigger accounts, the current SQL-to-Opportunity-to-Close motion fails to capture the larger deal values from the larger accounts. We can also observe that winrate declines as account size grows. This indicates the AE team may need to address improving their skills in closing larger accounts.

in 2023 Outbound targeted largest accounts (median 252 vs. Inbound's 65 employees) but suffered low-end winrate (22% vs. Inbound’s 38%). Field (conferences) targeted mid-size accounts with median account of 144, and remained limited by the available conference audiences. Winrates and deal close cycles for Field is on par with Inbound.

It’s tempting to explain Field performance - its winrates and deal cycles on par with Inbound  - by the combination of the personal contact with the attractive physical items being marketed, however Field numbers are less certain with fewer datapoints available.


### __Business Recommendations__  
- Audit Outbound SQL-Opportunity-Closing process to identify the value leaks. Add SQL data to evaluate SQL->Opportunity conversions per channel. Sample and review manually of a cohort of high-size account outbound leads to reveal details of their journey. 
- Upon validation, consider crafting the dedicated Sales qualification - Deal creation - Closing cadences for high-size account leads focused on the leads originating from Outbound and Field channels.

### __Technical recommendations__

- Enforce 1:1 FirstDeal-to-Company architecture; implement CRM validation rules to prevent multiple "first deals" from being attached to a single company account.
- Automate data enrichment integrating firmographic providers (e.g., ZoomInfo, Clearbit, Linkedin scraping API’s) to eliminate the 18% missing industry data and replace manually rounded headcount numbers with more accurate data.

### __Note on the data__ 

The initial dataset contains 934 CRM deals records created between 2023-02-10 and 2024-01-30 (the dataset cut-off date). Key limitations include significant data hygiene issues, e.g. 18% missing industry data, manually rounded headcount estimates, significant noise in separation between the new customer and the repeat purchases deals, and presence of extreme outliers in deal amounts and account headcounts. Confidence intervals for key metrics were estimated at .95, non-parametric methods such as Spearman's correlation were used in addition to linear methods to evaluate the relationships.


## Data exploration and error correction

#### 1. There are 50 Accounts with two or more 1st Deals linked, and that's an error 

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/10_1st_deal_account_association.jpg" width=35% height=35%>

For simple let's fix these by programmatically by creating a mask that keeps only the earliest created deal per company, reducing the raw dataset down to 391 valid first-time deals.

#### 2. Account Industry not defined for 18% of the Accounts

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/20_account_industry_not_defined.jpg" width=80% height=80%>

Company (account) industry undefined for 70 or 18% of the total dataset accounts.

#### 3. Sharp round numbers for Account Headcounts have abnormal frequencies

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/30_headcount_abnormal_frequencies.jpg" width=40% height=40%>

A frequency analysis of company headcount reveals sharp round numbers (e.g., 10.7% of deals listed exactly "50", others listed "200" or "500"). This highlights that sales reps are manually setting the account sizes and provides for the recommendation to automate firmographic data enrichment.

### Deal source performance

#### 4. Deals created for each of the channels in 2023

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/41_2023_deals_created.jpg" width=35% height=35%>

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/42_2023_deals_created.jpg" width=40% height=40%>

#### 5. Account Size distribution and median for the three main channels in 2023

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/50_deals_by_channel_by_company_size.jpg" width=70% height=70%>

A clear separation in targeting performance emerges. Inbound attracts smaller accounts (Median Headcount = 65), while Outbound (Median Headcount = 252) and Field events (Median Headcount = 144) are successfully penetrating the mid-market and enterprise segments.

#### 6. Exploring the relationships between Deal Amount vs Account Headcount for each of the main channels

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/61_explore_linear_relationships.jpg">

Extreme outliers in Account HC and in the Deal Amounts obscure linear relationships for each of the channels. Trend’s confidence intervals look way too broad.  Pearson correlation coefficients:

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/62_pearson_corr.jpg" width=70% height=70%>

#### 7. Going deeper: exploring non-linear relationships between Deal Amount vs Account Headcount for each of the main channels

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

#### 8. Inbound volume winrate is higher than Outbound

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/81_deal_winrates_per_channel.jpg" width=60% height=60%>

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/82_deal_winrates_per_channel.jpg" width=50% height=50%>

Winrates computed on the cohort of the deals closed within the 2023.
inbound winrate is statistically higher than Outbound, conforming to known market trends. Field may have same or higher WR as inbound likely cause of human touch and material goods being sold. Note confidence interval for Field that is broader ‘cause of the limited 41 deal observations.

#### 9. Winrate drops for larger Accounts

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/91_deal_winrates_per_account_tier.jpg" width=60% height=60%>

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/92_deal_winrates_per_account_tier.jpg" width=50% height=50%>

Winrate decays significantly moving from the first to the upper Account size tiers, the 2nd and 3rd. Standard .95 confidence intervals shown.

#### 10. Inbound and Field are similar and have the shortest Deal Cycles

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/101_deal_cycles_per_account_tier.jpg" width=50% height=50%>

Inbound deals have a median closing time of 27 days, while outbound deals take 43 days - it is statistically significant. Field deals are similar to inbound at 30 days median, but their confidence interval extends more upward.

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/102_wonlost_deal_cycles_total.jpg" width=60% height=60%>

There is no significant difference in median close time between Won and Lost across all three channels, however bigger variance for won deal cycles is notable.  










