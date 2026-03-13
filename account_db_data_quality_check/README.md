## __Background__

This data quality audit was conducted to evaluate the health of core company database. Specifically, we aimed to assess the accuracy of account hierarchies (Global Entities vs local Accounts), geographic classifications, and core firmographics. Ensuring high fidelity in these data points can reduce friction for our sales teams and increases our overall go-to-market efficiency.

## __Executive Summary__ 
Are our territories properly assigned? - Only 49.7% of records have the correct geographic attributes, leading to misrouted leads and unbalanced territories.  
Is our parent-child account hierarchy accurate? - It needs significant work. Only 58% of local Accounts are correctly linked to their Global Entities, blinding reps to existing corporate relationships.  
Can we rely on firmographics for segmentation? - Employee counts are highly inaccurate, sitting at 30% accuracy for Global Entities and 48% for Accounts.

### __RevOps recommendations__
- Automated Data Enrichment: Integrate a third-party data provider (e.g. ZoomInfo, Clearbit) directly into HubSpot to automatically source and overwrite Account_geo and Number of Employees.

- Enforce CRM Validation: Implement strict field-level validations and make crucial fields mandatory upon new company creation to reduce manual entry errors.

- Automate Hierarchy Building: Deploy HubSpot workflows or third-party automation to dynamically associate child Accounts to their respective parent Global Entities based on DUNS identifier.

- Repeated Cleansing: Establish a quarterly automated de-duplication and data-cleansing routine to maintain a healthy baseline.

### __Note on Data & Methodology__
We conducted a statistical quality assurance check using a randomized sample of 199 records drawn from a total population of 2,246 HubSpot companies. Results were calculated with a 95% confidence level. Records were manually classified into Global Entities (GE) and local Accounts to test specific business rules surrounding parent-child associations, naming conventions, and attribute accuracy.

## Detailed Findings
The tables below outline the specific outcomes of the sample audit.

