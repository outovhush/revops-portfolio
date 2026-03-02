## __Background__

The reviewed pipeline was created up in 2023 upon the roll-out of the updated GTM process early that year. It features one-off B2B sales of physical goods (branded corporate merchandise). Unlike subscription, there is no customer lock-in; repeat purchases depend entirely on ongoing customer loyalty. The company uses a one-meeting AE process for new sales-qualified leads (SQLs), with the BANT qualification decision to be made right after the first meeting.

The primary objective is to analyze "first deals" (new customer acquisition) to understand channel performance, account firmographics (company headcount), deal cycles and revenue conversion efficiency (win rates).

### __Note on the data__ 

The initial dataset contains 934 CRM deals records created between 2023-02-10 and 2024-01-30 (dataset cut-off). Key limitations include significant data hygiene issues, e.g. 18% missing industry data, manually rounded headcount estimates, significant noise in separation between the new customer and the repeat purchases deals, and presence of extreme outliers in deal amounts and account headcounts. Confidence intervals for key metrics were estimated at .95, non-parametric methods such as Spearman's correlation were used in addition to linear methods to evaluate the relationships.

## __Executive Summary__ 

Outbound targeted largest accounts (median account size of 252 vs. Inbound's 65) but suffered low-end winrate (o/b volume winrate 22% is significantly lower than Inbound’s 38%, generally conforming to the market trends). With median account size of 144, Field targeted mid-size accounts, remaining limited in that department the accessible field events’ audiences. Winrate for Field is on par with Inbound however confidence interval broader to the upper side caused by the fewer data available. In terns of the sales cycles, the Inbound has min of 27, Field has 30, with Outbound having as many as 43 median days to close.  

It’s tempting to explain Field high performance by combination of the personal touches with  the material nature of the goods being sold, however confidence intervals for WR and Deal cycles remain broad and we’d want more data for better validation.

While Inbound demonstrated stat significant positive correlation between deal amount and account size (Spearman: 𝜌≈0.36, 𝑝-value<0.00001), there is weak to non-existent correlation in Outbound. This indicates that while Outbound can steer us to larger target accounts, the existing SQL-Opportunity-Closing process seems to fall short to capture higher potential value associated with such leads.

We can also observe statistically significant decline in the winrates, regardless of the channel, moving from the account size tier1 [0, 201) to tier2 [201, 901) and tier3 [901.0, inf).


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




