# revops-data-portfolio
Showcasing few examples of my work in sales and revenue operations

Hey there! I'm Andrew 👋

Ever heard of Revenue Operations (RevOps)? It's shaking things up a bit. Imagine a superhero Go-To-Market team where sales, marketing, and customer service all work together aligned perfectly to bring in more revenue. And the infrastructure is robust and up-to-date, and the workflow automation ensures that work is done in most efficient way. That's what the RevOps does! More companies, especially in SMB are catching on, realising it's not just a fad, but a real thing.

So, why am I the right person for RevOps? Well, I've done a quite bit of many things. I can see the big picture for a company strategic pursuits but also know how to get things done and aligned day-to-day. It's like being able to plan an awesome party and also know how to set up the decorations. I'm good at talking to different teams, understanding what they need, and finding ways to balance their needs and hit the revenue goals.

The data is super important on the operations side of things, but here's the thing – real world data is messy unlike what you see in the Titanic dataset. My job is to clean it up, make sense of it, and turn it into actionable insights. With the right tools, the CRM well set and customised, we can track everything important, get insights and make better business decisions.

Want to see how I've put all this into action? Check out some examples of my work below:👇🏼

* [Business Analysis and BP Engineering](#business-analysis-and-bp-engineering)  
* [Business and Revenue Modelling](#business-and-revenue-modelling)
* [Operational reporting and BI](#operational-reporting-and-bi)
* [Data analysis and data hygiene](#data-analysis-and-data-hygiene) 

<br>Thank you for reading;)</br>

## Business Analysis and BP Engineering

#### 👉 BPMN chart for business process visualisation

__Goal:__ Provide a easy-to-comprehend visual of the Appointment Setting process for analysis, documentation, onboarding, etc.

__Skills:__ Business analysis, BPMN 2.0

__Results: [The BPMN chart for AS process](https://miro.com/app/board/uXjVNiNbKiI=/)__

#### 👉 Plan and design for the revenue process update

__Goal:__ Plan, prepare and document a major update of the company revenue process  

__Skills:__ Business analysis, process engineering, project management, requirement solicitation, revenue and sales KPI

__Results: [Design doc with example charts (redacted)](https://docs.google.com/document/d/1giJFaFxC3llHn1Sc5179GKAzNN8zob2pVR4KSCcrLL4/edit?usp=sharing)__

## Business and Revenue Modelling

#### 👉 One-pager revenue model

__Goal:__ Provide the qualitative sanity-check and annual revenue forecasting going down to top; identify the bottle necks and key sensitivity.

__Skills:__ Business analysis, modelling, revenue and sales metrics, Google sheets

__Results: [The revenue model (redacted)](https://docs.google.com/spreadsheets/d/1YiU6LmTOVAg8TatVKFloPJm_9UbvCY93DYsBcNjTBmE/edit?gid=748648396#gid=748648396)__
   

## Operational reporting and BI

#### 👉 Ad-hoc analytics focused on the reps' performance and deal lost reasons

Once in a while you spot an anomaly on the operating dashboards and need a quick dive into the specific area of the revenue operations. Basics tools are enough to do the job.

__Goal:__ Assess sales reps performance for the deals that take longer to close; get insights and support the decision making.  

__Skills:__ Sales KPIs, descriptive statistics, pivot tables, data visualisation, analytical thinking

__Tech:__ Hubspot, Google sheets

__Results: [pdf report](https://github.com/outovhush/revops-data-portfolio/blob/main/Ad-hoc%20reports_AE%20WR%20lost%20deals%20quickstat_anon_upd.pdf)__


## Data analysis and data hygiene

#### 👉 Data quality check

Suppose you have to combine manual data entry with a custom data structures that is not natively supported by your system. Entry errors become very likely. Automated validation are hardly an option at this stage. You'd need a fast check to estimate extent of errors in the database, and the full manual inspection would be too expensive.
     
__Goal:__ Provide reliable estimate for the extent of data errors in the customer account database.

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



