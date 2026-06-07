Credit Card Portfolio Analysis & Customer Segmentation EDA
Overview
This project delivers an end-to-end Exploratory Data Analysis (EDA) and data handling framework to analyze credit card lifecycle metrics, spend typologies, and repayment behaviors. By synthesizing separate banking data files, this solution exposes customer demographic profiles, enforces risk-mitigation rules via data capping, and tracks seasonal financial variables across corporate segments and geographical regions.

The project follows a rigorous data science workflow, including multi-file relational data merging, anomaly correction, out-of-bounds demographic engineering, business-rule capping, and multi-dimensional cohort aggregation.

Problem Statement
Retail banking institutions must monitor transactional spend metrics alongside repayment velocity to identify profitable customer segments and control credit risk. The objective of this analysis is to consolidate isolated user portfolios and provide clear visibility into:

Customer base distribution across demographic groups and asset tiers.

Behavioral spend patterns across distinct product categories.

Portfolio constraints caused by out-of-bounds demographic noise or transactions exceeding established credit limits.

Dataset
The analysis utilizes three primary data layers containing relational customer metrics:

1. Customer Acquisition
Dimensions: 100 unique customer accounts.

Features: Customer ID, Age, City, Product tier (Gold, Silver, Platinum), Credit Limit, and Segment.

2. Spend
Dimensions: Sequential credit card swipe records mapping itemized usage.

Features: Customer ID, Month (transaction date), Type (product category), and Amount.

3. Repayment
Dimensions: 1,500 historic repayment records capturing user payment streams.

Features: Customer ID, Month (repayment date), and Amount.

Data Handling & Preprocessing Pipeline
Data Ingestion & Relational Merging
Primary datasets were ingested from spreadsheet sources using pandas.

Synthesized separate tables into a centralized analytical data structure named customer_repayment using a relational outer join on the shared key Customer.

Demographic Noise Correction (Age Harmonization)
Raw consumer profile data contained decimal noise and extreme age attributes.

Applied systematic floor and ceiling functions to clean the profiles, structuring a standardized workforce demographic ranging from youth categories up to an established workforce limit of 42.28 years.

Business Rule Implementation (Credit Limit Capping)
To account for real-world risk-mitigation constraints, the script checks if a customer's individual transactional repayment or spend amount outstripped their card allowance.

Capping Logic: If Amount > Limit, the script dynamically adjusts the value to match that specific customer's Limit ceiling. For instance, entry-level tiers with structural limits of 10,000 or 10,001 automatically had excessive records capped at those exact thresholds.

Temporal Feature Engineering
Raw date columns were parsed from string representations into true Datetime objects.

Extracted independent Month and Year periods to serve as time-series anchors for seasonal trend analysis.

Exploratory Data Analysis & Methods
Several multi-dimensional aggregations were performed to profile credit card performance:

Key Operations Evaluated
Unique Count Profiling: Isolated distinct entities using .nunique() to establish baseline population sizes.

Geographic Segmentation: Aggregated financial transactions across 8 prominent cities to discover regional spend concentrations.

Product Tier Mapping: Grouped portfolio parameters across card tiers (Gold, Silver, Platinum) to monitor limit availability.

Macro-Segment Analysis: Classified customer profiles into 5 distinct corporate classes (Self Employed, Salaried_MNC, Salaried_Pvt, Govt, and Normal Salary).

Asset Category Tracking: Component-level spending was tracked across various item classifications (e.g., CAMERA, BUS TICKET).

Key Findings
1. Customer Base Topography
The analyzed portfolio represents 100 distinct customer accounts.

Customer records are uniformly spread across 8 key urban centers and divided among 5 primary employment segments.

2. Risk and Limit Constraints
High-wealth customers operating under premium profiles (Gold tier with credit ceilings up to 500,000) generate the most stable and high-volume transaction lines.

Consumers holding Silver or Platinum cards encounter hard credit boundaries much more frequently, as evidenced by the high invocation of the capping rule at lower boundaries (10,000 / 10,001).

3. Spend Dynamics
Spending behavior varies significantly depending on the product tier, with premium tiers showing higher engagement with high-value retail categories, while lower tiers primarily drive volume through daily utilities and transport.

Business Recommendations
Targeted Limit Extensions: Offer proactive credit limit increases to verified high-income customers within the Silver and Platinum tiers who frequently hit their credit ceilings.

Differentiated Reward Programs: Align credit card rewards with high-frequency categories; introduce specialized travel and transit incentives for entry-tier cards, and lifestyle rewards for premium gold tiers.

Dynamic Risk Adjustment: Use the temporal trend insights to predict peak seasonal spending months (e.g., holiday seasons) and adjust short-term transaction ceilings accordingly.

Technologies Used
Python

Pandas

NumPy

Matplotlib

Seaborn

OpenPyXL (Excel Ingestion Engine)

Project Workflow
Environment Setup & Library Ingestion (Pandas, NumPy, Seaborn)

Data Ingestion from isolated relational sheets

Data Profiling (.nunique() and structural shape verification)

Age Harmonization & demographic data cleaning

Credit Limit Capping Implementation (Business rule application)

Temporal Feature Extraction (Month and Year parsing)

Relational Table Merging via outer joins on Customer

Cohort Aggregation across Cities, Segments, and Product Tiers

Behavioral Tracking across asset spend categories

Data Visualization of seasonal trends and portfolio distributions

Insight Extraction & Reporting
