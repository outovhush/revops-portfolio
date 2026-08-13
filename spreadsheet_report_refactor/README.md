## Background
This project refactors legacy spreadsheet-based reporting into a scalable analytics solution using Tableau for a B2B2C SaaS company. The business partners with global telecommunications providers to deliver its product to end-users. The objective was to replace static spreadsheets with interactive visualizations that track partnership performance, end-user adoption (penetration) within the subscriber bases, recurring revenue, and operational efficiency across the customer lifecycle.

## Executive Summary
This analysis provides a consolidated view of partnership performance, answering critical business questions regarding user acquisition, revenue generation, and time-to-market. The dashboards reveal that while the total addressable subscriber base is vast, actual end-user penetration varies heavily across regions and Customer Success Managers (CSMs). We tracked the transition of accounts from signing to launch, identifying specific bottlenecks in the integration cycle. The financial analysis breaks down Monthly Revenue Per User (MRPU) and compares Business-As-Usual (BAU) revenue against pipeline opportunities. It also highlights the forecast penetration rate inconsistencies looking at the MoM change in this metric.

### Business Metrics Reported
__Subscriber Base & Total Users:__ The total addressable market per partner vs. the actual active users of the product.

__Penetration Rate:__ The percentage of active users relative to the partner's total subscriber base.

__MRPU (Monthly Revenue Per User):__ The average monthly revenue generated per active end-user.

__Revenue (BAU vs Opportunity):__ Current recognized recurring revenue compared to projected pipeline revenue.

__Sales Cycle (Months):__ The time required to sign up a partner.

__Sign-to-Launch (Months):__ The operational timeline from contract sign-up to the product going live.   

## The Data Story
Full version of the Story is best viewed in Tableau Public with the interractive controls; featuring here the selected snapshots for demo purposes.

### Pipeline Overview



### Pipeline breakdown - by Partner location, by the Launch event

Green/Grey - Accounts Launched vs. All Accounts Signed (yet to Launch).  
Showing All CS Reps.  
<img src="https://github.com/outovhush/revops-portfolio/blob/main/spreadsheet_report_refactor/Pipeline_breakdown_geo.png">

### CS Rep Performance trends - Account Age vs. Penetration

CS CS Reps are shown in color, with the respective trend lines.  
Showing only launched Accounts.  
<img src="https://github.com/outovhush/revops-portfolio/blob/main/spreadsheet_report_refactor/account_age_vs_penetration_rep_performance.png">

### Sales & Integration Cycles

### Customer Penetration Heatmap

### Penetration Sources
Showing portfolio for CS Rep5.  
Showing 2025 per partner actuals in continuity with 2025 forecast.  
<img src="https://github.com/outovhush/revops-portfolio/blob/main/spreadsheet_report_refactor/rep5_penetration_sources.png">


### Key metrics: MRPU, Penetration and Revenue

<img src="https://github.com/outovhush/revops-portfolio/blob/main/spreadsheet_report_refactor/mrpu_penetration_revenue.png">

### Aggregate Penetration - Actuals vs Forecast
Showing spike in aggregate penetration forecast April on March. We can drill-down on the chart to identify where it comes from and if there is the forecast opportunity driving this vs just a forecasting error.  
<img src="https://github.com/outovhush/revops-portfolio/blob/main/spreadsheet_report_refactor/spike_in_penetration_forecast.png">
