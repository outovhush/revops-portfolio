# revops-portfolio

Hey there! I'm Andrew👋

Revenue Operations sits at the critical intersection of commercial strategy, business analysis, data, and technical expertise. It goes beyond managing SalesForce or HubSpot instance; it demands more holistic approach to driving measurable growth through process efficiency, solid infrastructure and cross-functional project and stakeholder management.

This portfolio shows my ability to drive real impact at every stage of the revenue process. It features specific tasks and projects across the full range of Revenue and Sales Operations that contributed to the broader business goals and strategic initiatives.

Key Highlights:👇🏼

* [Business Analysis and Process Modeling](#business-analysis-and-process-modeling)  
* [Revenue Modeling and Capacity Planning](#revenue-modeling-and-capacity-planning)
* [Data Analysis, Reporting and BI](#data-analysis-reporting-and-bi)
* [Data Quality and Hygiene](#data-quality-and-hygiene) 

Thank you for reading! I hope these examples demonstrate the value I can bring on your team.

## Business Analysis and Process Modeling

#### 👉 Concept design for end-2-end B2B GTM process

__Goal:__ Give stakeholders a high-level overview of the proposed B2B go-to-market process, from marketing and lead generation through customer success. Highlight the main stages, key activities, and handover points.     

__Skills:__ B2B sales processes, business analysis, requirements gathering, process design, and visualization.

__Results: [E2E Process map](https://github.com/outovhush/revops-data-portfolio/blob/main/GTM_process_hi-level_map.jpg)__       

#### 👉 Design of field event leadgen process

__Goal:__ Share a hi-level diagram of the proposed field event process with stakeholders for approval. Include a detailed process map to support implementation and team onboarding. 

__Results: [Field lead gen at hi-level](https://github.com/outovhush/revops-data-portfolio/blob/main/Field_lead_gen_hi-level.jpg), and [Detailed process diagram](https://github.com/outovhush/revops-data-portfolio/blob/main/Field_lead_gen_detailed_diag.jpg)__ 

## Revenue Modeling and Capacity Planning

#### 👉 SaaS Revenue & Team compensation model

__Goal:__ Identify bottlenecks, validate unit economics, and create a data-driven hiring and compensation roadmap that scales sales and CS together with the revenue growth.

__Skills:__ Business and financial modeling, SaaS metrics, Compensation planning, Excel/Google Sheets

__Results: [Model summary with recommendations](revenue_modelling/README.md)__
   

## Data Analysis, Reporting and BI

#### 👉 Ad-hoc pipeline analytics focused on the team performance and the lost deals

Sometimes oeprational dahsboards do not provide sufficient detail and you need a quick dive into the specific section of your data.

__Goal:__ To evaluate sales performance and pipeline health following major operational shift, identifying growth drivers, pinpointing weak spots, and providing recommendations.

__Skills:__ Sales KPI's, descriptive statistics, data visualization, analytical thinking

__Tech:__ HubSpot, Google Sheets

__Results: [The report](AE_adhoc_data_analysis_GR/README.md)__

#### 👉 Deal pipelime exploration, data cleaning and check on channel performance

__Goal:__  Explore raw CRM pipeline dataset, identify and correct errors, compute deals to compare channel performance  

__Skills:__ Data cleaning, data exploration, correlations, data visualization

__Tech:__ Python, Pandas, Matplotlib, Seaborn

__Results: [Analysis report](swag_23_pipeline_correlations/README.md)__

#### 👉 Ad-hoc reporting
   
__Goal:__ Evaluate and benchmark historical leadgen channel performance in terms of MQL, SQL throughput and conversion rates. Since the CRM's built-in reporting tools are limited, pull data through the API, clean and transform it to build custom visualization.

__Skills:__ Leadgen KPI's, data analysis and visualization, HubSpot API, Python/Pandas

__Results: [Historical performance of the lead generation channels](https://github.com/outovhush/revops-data-portfolio/blob/main/AS%20pipe%20-%20annon_channels%20history%20data.jpg)__


## Data Quality and Hygiene

#### 👉 Data quality quick check

Suppose you combine manual data entry with a custom data model that is not fully supported by your CRM. Entry errors become likely, but automated entry validation is not an option at this stage. You'd want a fast check to estimate extent of errors in the database.
     
__Goal:__ Provide significant estimate for the extent of data errors in the customer account CRM database.

__Steps:__
- figure out sample size given CLT limitations for binomial
- set up the observations and get the random sample
- check the sample manually collecting observations
- calculate sample means and confidence intervals

__Skills:__ Statistics, analytical thinking, Google sheets

__Results: [Google Sheet report](https://docs.google.com/spreadsheets/d/107Ku2k5vmR8ulyRyZNqTPoGAuRe9W2vTZqMGrSvtl5c/edit?gid=1064755575#gid=1064755575)__


#### 👉 Visualized data errors in the account db (CRM data)

__Goal:__ Visualize inconsistencies in the account data that are critical for proper revenue and deal reporting; enable further manual checks and corrections

__Skills:__ Data cleaning, data analysis, data visualization

__Tech:__ Python, Pandas, Matplotlib

__Code: [Example notebook](https://github.com/outovhush/revops-data-portfolio/blob/main/Example%20notebook_check%20deals%20source.ipynb)__

__Results: [image with clickable links in a standalone pdf](https://github.com/outovhush/revops-data-portfolio/blob/main/deal_source_plot_Create_date.pdf)__



