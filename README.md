[Q2_2024_QuickBooks_Retention_Data.csv](https://github.com/user-attachments/files/19674935/Q2_2024_QuickBooks_Retention_Data.csv)# emma-empanadas-marketing-data-24-
Weekly marketing data for a empanada catering business, covering Q4 2023 to Q3 2024.
Emma's Empanadas: Q4 2023 – Q3 2024 Marketing Analysis
Overview
This project showcases a comprehensive marketing performance analysis for a small local business, Emma's Empanadas. The objective was to measure the effectiveness of email and SMS campaigns, track customer engagement, and assess ROI across four fiscal quarters.

This is a fictional project built using mock data and SQL analysis to demonstrate marketing data storytelling, technical proficiency, and reporting skills.

Objective
Analyze the performance of multichannel marketing campaigns (email and SMS).

Evaluate engagement metrics: impressions, open rates, click-through rates, and conversions.

Perform A/B testing analysis on campaign variants.

Calculate ROI and customer retention using SQL queries and visualizations.

Present time-based trends and quarter-over-quarter improvements.

Dataset Highlights
Time Period: Q4 2023 to Q3 2024

Channels Analyzed: Email & SMS

Sample Size: 700+ records of marketing performance data

Columns Included:
Campaign Type (Email/SMS)

Campaign Variant (A/B Test)

Impressions

Opens (Emails)

Clicks (Emails & SMS)

Conversion Rate

Revenue

Cost per Campaign

Customer Segment

Campaign Date

Tools Used
import pandas as pd

import pandas as pd
import numpy as np
from datetime import datetime

# Load the existing dataset
file_path = '/mnt/data/Emma_s_Empanadas_Q4_2023_-_Q3_2024_Marketing_Data.csv'
df = pd.read_csv(file_path)

# Add new KPI columns with mock data
np.random.seed(42)  # For reproducibility

# Engagement & Reach
df['Website Visits'] = np.random.randint(800, 2000, size=len(df))
df['Unique Visitors'] = (df['Website Visits'] * np.random.uniform(0.7, 0.9, size=len(df))).astype(int)

# Conversion & Revenue
df['Orders'] = np.random.randint(50, 200, size=len(df))
df['Revenue'] = df['Orders'] * np.random.uniform(10.0, 25.0, size=len(df)).round(2)
df['Average Order Value (AOV)'] = (df['Revenue'] / df['Orders']).round(2)
df['Conversion Rate (%)'] = ((df['Orders'] / df['Website Visits']) * 100).round(2)
df['Cart Abandonment Rate (%)'] = np.random.uniform(20.0, 40.0, size=len(df)).round(2)

# Marketing Efficiency
df['Cost per Click (CPC)'] = np.random.uniform(0.5, 2.5, size=len(df)).round(2)
df['Cost per Acquisition (CPA)'] = np.random.uniform(5.0, 20.0, size=len(df)).round(2)
df['Return on Ad Spend (ROAS)'] = np.random.uniform(1.5, 4.0, size=len(df)).round(2)
df['Email Bounce Rate (%)'] = np.random.uniform(0.5, 5.0, size=len(df)).round(2)
df['Unsubscribe Rate (%)'] = np.random.uniform(0.1, 2.0, size=len(df)).round(2)

# Retention & Loyalty
df['Repeat Purchase Rate (%)'] = np.random.uniform(10.0, 30.0, size=len(df)).round(2)
df['Customer Lifetime Value (CLV)'] = np.random.uniform(100.0, 400.0, size=len(df)).round(2)
df['Churn Rate (%)'] = np.random.uniform(5.0, 20.0, size=len(df)).round(2)

# Save the expanded file
expanded_file_path = '/mnt/data/Emma_s_Empanadas_Expanded_Marketing_Data.csv'
df.to_csv(expanded_file_path, index=False)

import ace_tools as tools; tools.display_dataframe_to_user(name="Expanded Marketing Dataset", dataframe=df)

expanded_file_path
[Uploa
-- Table Creation
CREATE TABLE emmas_empanadas_marketing (
    month VARCHAR(20),
    social_followers INT,
    website_orders INT
);

-- Insert Data
INSERT INTO emmas_empanadas_marketing (month, social_followers, website_orders)
VALUES 
('January', 150, 45),
('February', 230, 78),
('March', 390, 130),
('April', 520, 165);

-- Monthly Growth in Followers
SELECT 
    month,
    social_followers,
    LAG(social_followers) OVER (ORDER BY 
        CASE month
            WHEN 'January' THEN 1
            WHEN 'February' THEN 2
            WHEN 'March' THEN 3
            WHEN 'April' THEN 4
        END
    ) AS prev_followers,
    social_followers - LAG(social_followers) OVER (ORDER BY 
        CASE month
            WHEN 'January' THEN 1
            WHEN 'February' THEN 2
            WHEN 'March' THEN 3
            WHEN 'April' THEN 4
        END
    ) AS growth
FROM emmas_empanadas_marketing;

-- Conversion Rate of Followers to Orders
SELECT 
    month,
    social_followers,
    website_orders,
    ROUND((website_orders * 1.0 / social_followers) * 100, 2) AS conversion_rate_percentage
FROM emmas_empanadas_marketing;

-- Cumulative Orders Over Time
SELECT 
    month,
    SUM(website_orders) OVER (
        ORDER BY 
            CASE month
                WHEN 'January' THEN 1
                WHEN 'February' THEN 2
                WHEN 'March' THEN 3
                WHEN 'April' THEN 4
            END
    ) AS cumulative_orders
FROM emmas_empanadas_marketing;
[Uploading Q2_2024_QuickBFirm ID,Firm Name,Q2 2024 Revenue (USD),Attached Products,Retained Q3 2024
Firm_001,Accounting Co 1,221958,QB Time,True
Firm_002,Accounting Co 2,771155,QB Payments,True
Firm_003,Accounting Co 3,231932,None,True
Firm_004,Accounting Co 4,1514414,QB Payments,False
Firm_005,Accounting Co 5,359178,QB Payroll,True
Firm_006,Accounting Co 6,1792743,None,True
Firm_007,Accounting Co 7,210268,QB Time + Payments,True
Firm_008,Accounting Co 8,832180,All Products,True
Firm_009,Accounting Co 9,1203462,QB Payroll + Payments,True
Firm_010,Accounting Co 10,237337,QB Payroll,False
Firm_011,Accounting Co 11,1099890,None,True
Firm_012,Accounting Co 12,1670006,QB Payments,False
Firm_013,Accounting Co 13,1236074,QB Time,True
Firm_014,Accounting Co 14,1012756,None,True
Firm_015,Accounting Co 15,275203,QB Time,False
Firm_016,Accounting Co 16,1339911,None,False
Firm_017,Accounting Co 17,378167,QB Time + Payments,True
Firm_018,Accounting Co 18,141090,QB Payroll,False
Firm_019,Accounting Co 19,429365,QB Payments,True
Firm_020,Accounting Co 20,1213396,QB Payroll,True
Firm_021,Accounting Co 21,887201,QB Time,True
Firm_022,Accounting Co 22,1470455,QB Time,True
Firm_023,Accounting Co 23,1866891,QB Payroll,True
Firm_024,Accounting Co 24,427069,All Products,True
Firm_025,Accounting Co 25,1925573,QB Payroll + Time,True
Firm_026,Accounting Co 26,1347617,QB Time + Payments,True
Firm_027,Accounting Co 27,891743,QB Payroll + Payments,True
Firm_028,Accounting Co 28,203355,QB Payments,False
Firm_029,Accounting Co 29,1384372,QB Time + Payments,True
Firm_030,Accounting Co 30,1362752,None,True
Firm_031,Accounting Co 31,284779,QB Payroll,False
Firm_032,Accounting Co 32,1496025,None,True
Firm_033,Accounting Co 33,1570485,QB Payroll,True
Firm_034,Accounting Co 34,1089436,QB Time,True
Firm_035,Accounting Co 35,1407371,QB Payroll,True
Firm_036,Accounting Co 36,586232,QB Payroll + Payments,False
Firm_037,Accounting Co 37,1017040,QB Time,False
Firm_038,Accounting Co 38,1648762,QB Payroll,True
Firm_039,Accounting Co 39,256730,QB Time,False
Firm_040,Accounting Co 40,1533257,None,False
Firm_041,Accounting Co 41,1298079,QB Payroll + Payments,True
Firm_042,Accounting Co 42,754811,None,False
Firm_043,Accounting Co 43,627035,All Products,True
Firm_044,Accounting Co 44,748143,QB Payroll + Time,False
Firm_045,Accounting Co 45,1600942,QB Payroll,False
Firm_046,Accounting Co 46,165725,None,True
Firm_047,Accounting Co 47,1278557,QB Payroll + Payments,True
Firm_048,Accounting Co 48,184654,QB Payroll + Time,True
Firm_049,Accounting Co 49,1053277,QB Payroll + Time,True
Firm_050,Accounting Co 50,691723,QB Payroll + Time,False
ooks_Retention_Data.csv…]()

ding emmas_empanadas_marketing_analysis.sql…]()


emma-empanadas-marketing-data/
│
├── marketing_data_generator.py          # Script to generate and expand mock data
├── schema.sql                           # SQL schema for MySQL table
├── insert_marketing_data.sql            # INSERTs (optional, or generate on the fly)
├── Emma_s_Empanadas_Expanded_Marketing_Data.csv  # Final dataset
├── requirements.txt                     # Dependencies
└── README.md                            # Docs & instructions


SQL (PostgreSQL-style syntax)

Tableau (for visualization)

Sample SQL Capabilities Demonstrated
A/B Test performance joins across campaign variants

Rolling 3-month averages for click-through and open rates

Revenue per campaign by channel and customer segment

ROI calculation using campaign cost and attributed revenue

CTEs and subqueries for layered aggregation

Campaign attribution funnel analysis

README.md — this documentation

Outcome
This project illustrates how marketing data can be transformed into actionable insights using SQL and data visualization. It's designed to simulate real-world data analysis for marketers or analysts managing campaign performance across digital channels.
