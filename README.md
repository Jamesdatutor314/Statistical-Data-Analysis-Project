# Megaline Prepaid Plan Analysis
By James Weaver

## Introduction
This project focuses on analyzing customer behavior for the telecom operator **Megaline**. The objective is to determine which of two prepaid plans—**Surf** or **Ultimate**—generates more revenue to help the commercial department optimize the advertising budget. The analysis is based on a sample of 500 clients from the year 2018.

## Files
1. **SDA.ipynb** The main Jupyter Notebook containing the code for data cleaning, monthly usage aggregation, behavioral analysis, and statistical hypothesis testing.
2. **megaline_calls.csv, megaline_internet.csv, megaline_messages.csv, megaline_users.csv, megaline_plans.csv** Datasets containing information on clients, calls, text messages, web traffic, and plan conditions.
3. **README.md** Overview of the project, methodology, tools used, and key findings.

## Approach
1. **Data Preparation**
   - Converted data to appropriate types (dates to `datetime`, IDs to `category`).
   - Applied Megaline billing rules: rounding individual calls up to the nearest minute and monthly total web traffic up to the nearest gigabyte.
2. **Data Enrichment**
   - Aggregated usage per user per month for calls, minutes, messages, and internet data.
   - Calculated monthly revenue for each user by accounting for plan fees and overage charges.
3. **Exploratory Data Analysis (EDA)**
   - Compared the average monthly minutes, messages, and GB used across both plans.
   - Visualized usage distributions to identify patterns and outliers.
4. **Statistical Analysis**
   - Calculated the mean, variance, and standard deviation for usage metrics.
   - Established **Confidence Intervals** to estimate the true population mean for revenue and usage with a high degree of certainty.
5. **Hypothesis Testing**
   - Formulated null and alternative hypotheses to test if average revenue differs between plans.
   - Tested for revenue differences between users in the NY-NJ area versus other regions.

## Tools Used
- **Python**: Core programming and data processing.
- **Pandas**: Data cleaning and monthly usage aggregation.
- **NumPy**: Numerical operations and revenue logic.
- **Matplotlib**: Creating visualizations for usage distributions.
- **SciPy / Stats**: Performing statistical hypothesis tests and calculating confidence intervals.

## Key Findings
1. **Sample Breakdown**
   - The analysis covered 500 unique clients: **339 (67.8%)** used the Surf plan, while **161 (32.2%)** used the Ultimate plan.
2. **Usage Behavior**
   - **Calls:** Surf users averaged **305.53** minutes per month, while Ultimate users averaged **292.79**. Despite the higher limit on Ultimate, calling behavior was remarkably similar between the two groups.
   - **Messages:** Messaging was low for both groups; half of all users in each plan sent fewer than **15 messages** per month.
   - **Internet:** Data usage was the primary driver of overage fees. About **32%** of Surf users exceeded their 15 GB limit, whereas only **4%** of Ultimate users exceeded their 30 GB limit.
3. **Revenue Performance**
   - **Average Revenue:** The Ultimate plan averaged **$71.53** per user, while Surf averaged **$48.38**.
   - **Profitability:** While Surf has a low entry price ($20), users frequently incur overage fees that double or triple their monthly bill. Ultimate provides more stable, higher-margin revenue.
4. **Confidence Intervals**
   - Calculated 95% confidence intervals for monthly revenue, confirming that the revenue difference between the plans is statistically significant and not due to random chance.
5. **Hypothesis Test Results**
   - **Plans:** Rejected the null hypothesis that average revenue is the same; there is a significant difference between Surf and Ultimate revenue.
   - **Region:** Failed to reject the null hypothesis regarding the NY-NJ area; data suggests revenue from the NY-NJ region is not significantly different from other regions.

## Visuals
### Month vs Average Duration Per Plan
![Average Duration Bar Chart](pics/bar_duration.png)

### Monthly Text Messages Per Plan
![Text Message Histogram](cite: 1181)

### Monthly Revenue Per Plan
![Revenue Histogram](pics/hist_revenue.png)

## Recommendations
1. **Focus Marketing on Ultimate**
   - Marketing budgets should prioritize the Ultimate plan. Even though Surf has more users, Ultimate's average revenue per user (ARPU) is nearly **50% higher**.
2. **Target Heavy Data Users**
   - Identify Surf users who consistently exceed 20 GB of data and target them with "Upgrade & Save" campaigns for the Ultimate plan to increase long-term retention.
3. **Data-Centric Promotions**
   - Since internet usage is the biggest differentiator, consider seasonal data promotions in the late fall and winter when usage peaks.

## Future Improvements
- Analyze the correlation between high overage fees and customer churn rates.
- Incorporate customer age and demographics into the behavioral models.
- Build a predictive model to identify which Surf users are most likely to switch to Ultimate.
