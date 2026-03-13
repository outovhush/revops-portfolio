## __Background__

This data quality audit was conducted to evaluate the health of core company database. Specifically, we aimed to assess the accuracy of account hierarchies (Global Entities vs local Accounts), geographic classifications, and core firmographics. Ensuring high fidelity in these data points can reduce friction for our sales teams and increases our overall go-to-market efficiency.

## __Executive Summary__ 
Are our territories properly assigned? - Only 49.7% of records have the correct geographic attributes, leading to misrouted leads and unbalanced territories.  
Is our parent-child account hierarchy accurate? - It needs significant work. Only 58% of local Accounts are correctly linked to their Global Entities, blinding reps to existing corporate relationships.  
Can we rely on firmographic for segmentation? - Rather, not. Employee counts are highly inaccurate, sitting at 30% accuracy for Global Entities and 48% for Accounts.

### __RevOps recommendations__
- Automated Data Enrichment: Integrate a third-party data provider (e.g. ZoomInfo, Clearbit) directly into HubSpot to automatically source and overwrite Account_geo and Number of Employees.

- Enforce CRM Validation: Implement strict field-level validations and make crucial fields mandatory upon new company creation to reduce manual entry errors.

- Automate Hierarchy Building: Deploy HubSpot workflows or third-party automation to dynamically associate child Accounts to their respective parent Global Entities based on DUNS identifier.

- Repeated Cleansing: Establish a quarterly automated de-duplication and data-cleansing routine to maintain a healthy baseline.

### __Note on Data & Methodology__
We conducted a statistical quality assurance check using a random sample of 198 records drawn from a total of 2,246 HubSpot companies in the database. Results were calculated with a 95% confidence level. Records were manually classified into Global Entities (GE) and local Accounts to test specific business rules surrounding parent-child associations, naming conventions, and attribute accuracy.

## Detailed Findings
The tables below outline the specific outcomes of the sample audit.

#### 1. Overall Database Health & Composition are usable, though there is a room for improvement

<img src="https://github.com/outovhush/revops-portfolio/blob/main/account_db_data_quality_check/1_db_health_and_composition.jpg" width=70% height=70%>

The assessment of the sample revealed that the majority of records are usable, though roughly 1 out of 8 records lack enough data to be actionable in the motion.

#### 2. Headcount, Territory & Hierarchy are hardly satisfactory, while Account naming is ok  

<img src="https://github.com/outovhush/revops-portfolio/blob/main/account_db_data_quality_check/2_account_hierarchy_naming_and_headcount.jpg" width=70% height=70%>

About a half of our records accurately reflect their geographic location compromising routing logic and cross-sell visibility.  While standard naming conventions for local Account are generally adhered to (72% accuracy), our Account and SE headcount data is deeply unreliable (48% and 30% accuracy). Parent-child mapping remains poor limiting strategic account management and ABM efforts.

