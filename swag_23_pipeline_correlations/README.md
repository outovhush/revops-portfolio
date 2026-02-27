## __Background__

The reviewed sales opportunities pipeline was created up in 2023 upon the roll-out of the updated GTM process early that year, and features one-off B2B sales of physical goods (branded corporate merchandise). Unlike subscriptions, there is no customer lock-in - repeat purchases depend on ongoing customer loyalty. The company uses a one-meeting AE process for new sales-qualified leads (SQLs), with the BANT qualification decision to be made right after the first meeting.

The primary objective is to analyze "first deals" (new customer acquisition) to understand channel performance, target account firmographics (company headcount), and revenue conversion efficiency (win rates).

### __Note on the data__ 

The initial dataset contains 934 CRM deals records created between 2023-02-10 and 2024-01-30 (dataset cut-off date). Key limitations include significant data hygiene issues, e.g. 18% missing industry data, manually rounded headcount estimates, significant noise in separation between the new customer and the repeat purchases (aka ‘existing customer’) deals, and presence of extreme outliers in deal amounts and company (account) headcounts. Non-parametric statistical methods (Spearman's correlation) used in addition to linear methods to evaluate the relationships.

## __Executive Summary__ 

Outbound targeted larger accounts (median account size of 252 vs. Inbound's 65) but suffers from lower conversion (O/b volume winrate 22% vs 38% for Inbound, roughly lining up with market trends). With median account size of 144, Field performed reasonably well in targeting larger customers, but remains limited external factors such as the accessible events’ audiences. Field enjoys the volume winrate of 44% that is 15% in excess of Inbound’s 38%, likely due to personal touch and the material nature of the goods being sold.


While Inbound demonstrated significant strong positive correlation between deal amount and account size (Spearman: 𝜌≈0.36, 𝑝<0.00001), there is weak to non-existent correlation in Outbound. This indicates that while Outbound can steer us well to larger target accounts, the existing SQL-Opportunity-Closing process seems to fall short to capture higher potential value associated with those leads.


### __Business Recommendations__  
- Audit Outbound SQL-Opportunity-Closing motion to identify the value leaks. Add SQL data to evaluate SQL->Opportunity conversions per channel. Sample and review manually of a cohort of high-size account outbound leads to reveal details of their journey. 
- Upon validating, consider crafting the dedicated Sales qualification - Deal creation - Closing cadences for high-value outbound accounts leads.

### __Technical recommendations__

- Enforce 1:1 FirstDeal-to-Company architecture; implement CRM validation rules to prevent multiple "first deals" from being attached to a single company account.
- Automate data enrichment integrating firmographic providers (e.g., ZoomInfo, Clearbit, Linkedin scraping API’s) to eliminate the 18% missing industry data and replace manually rounded headcount numbers with more accurate data.

### Business Metrics 
- __Pipeline Generation Volume__, by Deal Source and Quarter.
- __Win Rate by Volume (%) and Win Rate by Revenue (%)__, Mean Deal Sizes segmented by Closed vs Won.
- __Account Size__ measured by company headcount.


