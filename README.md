# Mobile-Application-
User level data for a mobile application has been provided. You are expected to do the following:  Create user cohorts based on the user metrics provided. You may also choose to build cohorts using single/ a combination of the metrics provided. Explain the rationale for the cohorts created by you. How would it be useful in analysing.
List the top 5 insights which have been derived by you based on analysis of the data provided.

**Tools used: Power BI, Dax, and Excel **

DAX Formulas Used:

Monetization Cohort = 
SWITCH(
    TRUE(),
    'Dataset1 (2)'[Average Spent on App (INR)]< 30, "Low",
    'Dataset1 (2)'[Average Spent on App (INR)] >= 30 && 'Dataset1 (2)'[Average Spent on App (INR)] < 60, "Medium",
    'Dataset1 (2)'[Average Spent on App (INR)] >= 60, "High",
    "Unknown"
)

Engagement Cohort = 
SWITCH(
    TRUE(),
    'Dataset1 (2)'[Average Screen Time (mins)] < 30, "Low",
    'Dataset1 (2)'[Average Screen Time (mins)] >= 30 && 'Dataset1 (2)'[Average Screen Time (mins)] < 60, "Medium",
    'Dataset1 (2)'[Average Screen Time (mins)] >= 60, "High",
    "Unknown"
)

Security Behavior Cohort = 
SWITCH(
    TRUE(),
    'Dataset1 (2)'[New Password Request] = 0, "No Requests",
    'Dataset1 (2)'[New Password Request] > 0 && 'Dataset1 (2)'[New Password Request] <= 2, "1-2 Requests",
    'Dataset1 (2)'[New Password Request] > 2, "Multiple Requests",
    "Unknown"
)

Recency Cohort = 
SWITCH(
    TRUE(),
    'Dataset1 (2)'[Last Visited Minutes] <= 7, "Last Week",
    'Dataset1 (2)'[Last Visited Minutes] > 7 && 'Dataset1 (2)'[Last Visited Minutes] <= 30, "Last Month",
    'Dataset1 (2)'[Last Visited Minutes] > 30 && 'Dataset1 (2)'[Last Visited Minutes] <= 90, "Last Quarter",
    'Dataset1 (2)'[Last Visited Minutes] > 90, "Older",
    "Unknown"
)


Creating cohorts is a powerful way to users based on specific behaviors or characteristics, which can provide valuable insights into business performance. Here's the rationale behind the cohorts created and how they can be useful:

Engagement Cohort: Segmented by 'Average Screen Time (mins)', it helps understand user engagement levels. Useful for identifying which features keep users engaged and where there might be drop-offs.
Monetization Cohort: Based on 'Average Spent on App (INR)', it identifies spending behavior. Helps in tailoring marketing strategies and improving monetization efforts.
Security Behavior Cohort: Based on 'New Password Request', indicating security-conscious behavior. Helps in understanding user concerns about security and potentially improving trust.
Recency Cohort: Segmented by 'Last Visited Minutes', indicating user retention and app stickiness. Useful for measuring churn rates and the effectiveness of retention strategies.

In Power BI, these cohorts can be analyzed through various visualizations and dashboards. Here's how you can use Power BI to analyze business performance using these cohorts:
