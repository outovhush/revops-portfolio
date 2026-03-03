## __Background__

The reviewed pipeline was created up in 2023 upon the roll-out of the updated GTM process early that year. It features one-off B2B sales of physical goods. Unlike many subscription products, there is no customer lock-in; repeat purchases depend entirely on ongoing customer loyalty. The company uses a one-meeting AE process for new sales-qualified leads (SQLs), with the BANT qualification decision to be made right after the first meeting.

### __Note on the data__ 

The initial dataset contains 934 CRM deals records created between 2023-02-10 and 2024-01-30 (the dataset cut-off date). Key limitations include significant data hygiene issues, e.g. 18% missing industry data, manually rounded headcount estimates, significant noise in separation between the new customer and the repeat purchases deals, and presence of extreme outliers in deal amounts and account headcounts. Confidence intervals for key metrics were estimated at .95, non-parametric methods such as Spearman's correlation were used in addition to linear methods to evaluate the relationships.

## __Executive Summary__ 

Outbound targeted largest accounts (median account size of 252 vs. Inbound's 65) but suffered low-end winrate (o/b volume winrate 22% is significantly lower than Inbound’s 38%, generally conforming to observable market trends). With median account size of 144, Field (conferences) targeted mid-size accounts, remaining limited by the accessible field events’ audiences. Winrate for Field is on par with Inbound, however its confidence interval is broader to the upper as the fewer datapoints available. Deal cycles for won and lost are highly spread-out for all three channels, making it difficult to infer. With a low confidence, medians for Inbound and Field wins are at roughly same 33 days, while for the Lost it’s at 27 days.  

It’s tempting to explain high Field conference performance by combination of the personal touches with the material goods (the corporate merchandise) being marketed, however confidence intervals for WR and Deal cycles are broad asking for more data for better inference.

While Inbound demonstrated statistically significant positive correlation between deal amount and account size (Spearman: 𝜌≈0.36, 𝑝-value<0.00001), there is weak to non-existent correlation in Outbound and Field. This indicates that while Outbound adn Field can steer us to larger target accounts, the existing SQL-Opportunity-Closing process seems to fall short to capture the higher potential value associated with such leads.

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

#### 1st Deal-Account association

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/10_1st_deal_account_association.jpg" width=70% height=70%>

There multiple 1st deals related with one account (company) in the raw dataset, this is an error. For simple let's fix these by programmatically by creating a mask that keeps only the earliest created deal per company, reducing the raw dataset down to 391 valid first-time deals.

#### Account industry not defined

<img src="https://github.com/outovhush/revops-portfolio/blob/main/swag_23_pipeline_correlations/20_account_industry_not_defined.jpg" width=70% height=70%>

Insight: Company (account) industry undefined for 70 or 18% of the total dataset accounts.



