# emma-empanadas-marketing-data-24-
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
