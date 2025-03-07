# revops-data-portfolio
Showcasing few examples of my work in sales and revenue operations

Hey there! I'm Andrew 👋

Ever heard of Revenue Operations (RevOps)? It's shaking things up a bit. Imagine a superhero Go-To-Market team where sales, marketing, and customer service all work together aligned perfectly to bring in more revenue. And the infrastructure is robust and up-to-date, and the workflow automation ensures that work is done in most efficient way. That's what the RevOps does! More companies, especially in SMB are catching on, realising it's not just a fad, but a real thing.

So, why am I the right person for RevOps? Well, I've done a quite bit of many things. I can see the big picture for a company strategic pursuits but also know how to get things done and aligned day-to-day. It's like being able to plan an awesome party and also know how to set up the decorations. I'm good at talking to different teams, understanding what they need, and finding ways to balance their needs and hit the revenue goals.

The data is super important on the operations side of things, but here's the thing – real world data is messy unlike what you see in the Titanic dataset. My job is to clean it up, make sense of it, and turn it into actionable insights. With the right tools, the CRM well set and customised, we can track everything important, get insights and make better business decisions.

Want to see how I've put all this into action? Check out some examples of my work below:👇🏼

* [Business Analysis and BP Engineering](#business-analysis-and-bp-engineering)  
* [Business and Revenue Modelling](#business-and-revenue-modelling)
* [Reporting and Business intelligence](#reporting-and-business-intelligence)
* [Data analysis and data hygiene](#data-analysis-and-data-hygiene) 

<br>Thank you for reading;)</br>

## Business Analysis and BP Engineering

#### 👉 BPMN chart for business process visualisation

__Goal:__ Provide a easy-to-read visual of the Appointment Setting workflow for better process analysis, improvement, documenting, and onboarding new reps.

__Skills:__ Business analysis, BPMN 2.0

__Results: [The BPMN chart for AS process](https://miro.com/app/board/uXjVNiNbKiI=/)__

#### 👉 Design and implement major update for the company revenue process

__Goal:__ Plan, document and deploy two new pipelines in CRM, the Appointment Setting and the Account Execution pipeline, integrating all discrete lead sources and mirroring the agreed Go-To-Market process; infuse max automation to handle low-level data entry, integration and notification tasks      

__Skills:__ Business analysis, process engineering, project management, requirement solicitation, HubSpot, process automation, revenue and sales KPI

__Results:__ All lead sources merged in the single Appointment Setting pipeline that in turn delivered new deals into the Account Execution pipe, allowing AS and AE teams do their parts in the most effective way. Visibility increased, reporting went live, conversions and deal win rates grew x2.  
__[Design doc with some deliverables ](https://docs.google.com/document/d/1giJFaFxC3llHn1Sc5179GKAzNN8zob2pVR4KSCcrLL4/edit?usp=sharing)__       

## Business and Revenue Modelling

#### 👉 One-pager quick revenue model

__Goal:__ Provide a quick reality-check of growth expectations together with grounded annual revenue forecasts for a scale-up business; identify the bottle necks and key sensitivities.

__Skills:__ Business analysis, business modelling, revenue and sales metrics, Google sheets

__Results: [The revenue model (redacted)](https://docs.google.com/spreadsheets/d/1YiU6LmTOVAg8TatVKFloPJm_9UbvCY93DYsBcNjTBmE/edit?gid=748648396#gid=748648396)__
   

## Reporting and Business Intelligence

#### 👉 Ad-hoc analytics focused on the reps' performance and deal lost reasons

Once in a while you spot an anomaly on the operating dashboards and need a quick dive into the specific area of the revenue operations. Basics tools are enough to do the job.

__Goal:__ Assess sales reps performance for the deals that take longer to close; get insights and support the decision making.  

__Skills:__ Sales KPIs, descriptive statistics, pivot tables, data visualisation, analytical thinking

__Tech:__ Hubspot, Google sheets

__Results: [pdf report](https://github.com/outovhush/revops-data-portfolio/blob/main/Ad-hoc%20reports_AE%20WR%20lost%20deals%20quickstat_anon_upd.pdf)__

#### ✴️ Reporting with the tools outside CRM

The native reporting toos of your CRM may be too restrictive at times. Put together a script to pull data via API, do the data transform and the fast drawing.
   
__Goal:__ Check historical Appoinment Setting pipeline performance, estimate conversion rates, present data in an easy-to-read visual.  

__Skills:__ Lead generation metrics and KPI's, data visualisation, analytical thinking

__Tech:__ Hubspot API, Python, Pandas, Matplotlib, Seaborn

__Results: [Appoinment Setting pipe historical stat](https://github.com/outovhush/revops-data-portfolio/blob/main/AS%20pipe%20-%20annon_channels%20history%20data.jpg)__


## Data analysis and data hygiene

#### 👉 Data quality quick check

Suppose you have to combine manual data entry with a custom data structures that is not natively supported by your system. Entry errors become likely. Automated validation are hardly an option at this stage. You'd want a fast check to estimate extent of errors in the database.
     
__Goal:__ Provide statistically significant estimate for the extent of data errors in the customer account database.

__Steps:__
- figure out sample size given the CLT limitations for binomial
- set up the observations
- get the random sample
- check the sample manually collecting observations
- calculate sample means and confidence intervals

__Skills:__ Statistics (Binomial distribution, CLT), analytical thinking, Google sheets

__Results: [Google Sheet report](https://docs.google.com/spreadsheets/d/107Ku2k5vmR8ulyRyZNqTPoGAuRe9W2vTZqMGrSvtl5c/edit?gid=1064755575#gid=1064755575)__

#### 👉 CRM deal dataset exploration

__Goal:__  Explore raw CRM annual deal dataset, check some business metrics, identify inconsistencies and errors in the data

__Skills:__ Data cleaning, data exploration, Pearson correlation, data visualisation

__Tech:__ Python, Pandas, Matplotlib, Seaborn

__Code: [Example notebook](https://github.com/outovhush/revops-data-portfolio/blob/main/Example%20notebook_Deal%20dataset%20exploration.ipynb)__

__Results:__ Few essential business metrics were visualised; the analysis revealed that expected correlations were not held for all lead generation channels. Major inconsistencies in the data were identified    

#### 👉 Visualised data errors in the account db (CRM data)

__Goal:__ Visualise inconsistencies in the account data that are critical for proper revenue and deal reporting; enable further manual checks and corrections

__Skills:__ Data cleaning, data analysis, data visualisation

__Tech:__ Python, Pandas, Matplotlib

__Code: [Example notebook](https://github.com/outovhush/revops-data-portfolio/blob/main/Example%20notebook_check%20deals%20source.ipynb)__

__Results: [image with clickable links in a standalone pdf](https://github.com/outovhush/revops-data-portfolio/blob/main/deal_source_plot_Create_date.pdf)__



