# Megaline Prepaid Plan Analysis
By James Weaver

## Introduction
[cite_start]This project focuses on analyzing customer behavior for the telecom operator **Megaline**[cite: 2, 1324]. [cite_start]The objective is to determine which of two prepaid plans—**Surf** or **Ultimate**—generates more revenue to help the commercial department optimize the advertising budget[cite: 4, 1326]. [cite_start]The analysis is based on a sample of 500 clients from the year 2018[cite: 6, 1328].

## Files
1. **SDA.ipynb** The main Jupyter Notebook containing the code for data cleaning, monthly usage aggregation, behavioral analysis, and statistical hypothesis testing.
2. [cite_start]**megaline_calls.csv, megaline_internet.csv, megaline_messages.csv, megaline_users.csv, megaline_plans.csv** Datasets containing information on clients, calls, text messages, web traffic, and plan conditions [cite: 15-18, 1351-1355].
3. **README.md** Overview of the project, methodology, tools used, and key findings.

## Approach
1. **Data Preparation**
   - [cite_start]Converted data to appropriate types (dates to `datetime`, IDs to `category`) [cite: 316-327].
   - [cite_start]Applied Megaline billing rules: rounding individual calls up to the nearest minute and monthly total web traffic up to the nearest gigabyte [cite: 393-401, 1330-1333, 1378-1381].
2. **Data Enrichment**
   - [cite_start]Aggregated usage per user per month for calls, minutes, messages, and internet data [cite: 798, 809, 835, 843, 1360-1363].
   - [cite_start]Calculated monthly revenue for each user by accounting for plan fees and overage charges [cite: 989-1003, 1364].
3. **Exploratory Data Analysis (EDA)**
   - [cite_start]Compared the average monthly minutes, messages, and GB used across both plans [cite: 1012-1016, 1100-1103, 1244-1246].
   - [cite_start]Visualized usage distributions to identify patterns and outliers [cite: 1024-1027, 1076-1080, 1131, 1179-1183, 1229-1233].
4. **Hypothesis Testing**
   - [cite_start]Formulated null and alternative hypotheses to test if average revenue differs between plans [cite: 1368-1374].
   - [cite_start]Tested for revenue differences between users in the NY-NJ area versus other regions[cite: 1370].

## Tools Used
- **Python**: Core programming and data processing.
- [cite_start]**Pandas**: Data cleaning and monthly usage aggregation[cite: 9].
- [cite_start]**NumPy**: Numerical operations and revenue logic[cite: 10].
- [cite_start]**Matplotlib**: Creating visualizations for usage distributions[cite: 11].
- [cite_start]**SciPy**: Performing statistical hypothesis tests[cite: 12].

## Key Findings
1. **Sample Distribution**
   - [cite_start]The dataset includes 339 Surf users and 161 Ultimate users [cite: 1284-1287].
2. **Usage Patterns**
   - [cite_start]Users on both plans show very similar behavior regarding call duration and messaging [cite: 1126-1129, 1186-1194].
   - [cite_start]Most distributions are right-skewed, showing a high concentration of users with low-to-moderate consumption[cite: 1086, 1153, 1187, 1250].
3. **Revenue Insights**
   - [cite_start]The average monthly revenue for **Surf** users is approximately **$48.38**[cite: 1276].
   - [cite_start]The average monthly revenue for **Ultimate** users is approximately **$71.53**[cite: 1276].
   - [cite_start]Ultimate users rarely exceed their generous limits, while Surf users frequently pay overage fees[cite: 1091, 1191, 1250].

## Visuals
### Month vs Average Duration Per Plan
![Average Duration Bar Chart](pics/bar_duration.png)

### Monthly Text Messages Per Plan
![Text Message Histogram](pics/hist_messages.png)

### Monthly Revenue Per Plan
![Revenue Histogram](pics/hist_revenue.png)

## Recommendations
1. **Promote the Ultimate Plan**
   - [cite_start]Since the average revenue per user is significantly higher for the Ultimate plan ($71.53 vs $48.38), marketing efforts should focus on upselling this plan to high-usage Surf customers[cite: 1276].
2. **Monitor Surf Overage**
   - Surf users frequently hit limits; Megaline could benefit from a "mid-tier" plan to prevent potential churn from users frustrated by high overage fees.
3. **Regional Strategy**
   - Use the results of the NY-NJ regional hypothesis test to determine if local pricing or promotions are needed for the metropolitan area.

## Future Improvements
- Analyze the correlation between high overage fees and customer churn rates.
- Incorporate customer age and demographics into the behavioral models.
- Build a predictive model to identify which Surf users are most likely to switch to Ultimate.
