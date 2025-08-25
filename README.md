# Screen-Time-Analysis-Using-Python
This project, “Screen Time Analysis using Python”, is developed using Pandas, NumPy, Matplotlib, and Seaborn. It leverages data analytics techniques to analyze, process, and visualize how much time users spend on apps, how often apps are opened, and overall digital behavior.
 Screen Time Analysis using Python

A Data Analytics & Visualization Project by D. Munibabu

 Overview

Screen time is one of the most important behavioral metrics in the digital era, reflecting how individuals spend time across different applications on their devices. With the rapid growth of smartphones, social media, and digital platforms, understanding screen time patterns has become crucial for:

Health & wellness (reducing overuse)

Productivity tracking

Digital addiction research

Application usage insights for developers

Time management for individuals

This project, “Screen Time Analysis using Python”, is developed using Pandas, NumPy, Matplotlib, and Seaborn. It leverages data analytics techniques to analyze, process, and visualize how much time users spend on apps, how often apps are opened, and overall digital behavior.

The project was done as part of my internship / academic project, applying data analytics in Python to a real-world problem: digital wellbeing and user behavior analysis.

 Problem Statement

 Why is screen time analysis important?

Excessive screen time can lead to digital addiction, poor sleep, and reduced productivity.

Parents and organizations want to monitor device usage for health and work efficiency.

Developers and businesses want to understand user engagement patterns with apps.

This project aims to provide a data-driven approach to answer questions like:

Which apps are most frequently used?

How much time is spent daily on screens?

What is the average session length per app?

Which apps are opened most frequently?

How do screen time patterns vary over days?

 Objectives

 Build a Python-based data analytics pipeline to analyze screen time.
 Process and clean a dataset of 1000+ app usage records.
 Extract meaningful metrics such as:

Daily usage per user

Most used apps

Frequency of app openings

Average session length per app
 Create visualizations (line charts, bar graphs) to present insights.
 Demonstrate the application of Pandas + NumPy for analytics and Seaborn + Matplotlib for visualization.

 Features

 Daily Screen Time Calculation – Track total usage minutes for each day.
 Top Apps Identification – Find which apps consume the most time.
 App Opening Frequency – Count how many times each app was opened.
 Average Session Length – Find average minutes per open.
 Visualizations – Line charts for trends, bar charts for app comparisons.
 Scalable Dataset – Works with 1000+ rows of app usage data.
 Customizable Analysis – Can extend with new metrics like hourly trends or user-based segmentation.

 Tech Stack

Programming Language → Python 3.x

Libraries:

Pandas → Data cleaning, grouping, analysis
NumPy → Numerical operations
Matplotlib → Data visualization
Seaborn → Advanced statistical plots

Dataset: screen_time_dataset_with_opens.csv (1000 records)

Environment: Jupyter Notebook / Python scripts

 Dataset Description

 File: screen_time_dataset_with_opens.csv
Rows: 1000

Column Name	Description
date	The date of the recorded activity (50 days period)
app_name	Name of the application used (YouTube, Instagram, Chrome, etc.)
usage_minutes	Number of minutes spent on the app in a session
times_opened	Sequence count showing how many times the app has been opened cumulatively

 Example (first 5 rows):

date	app_name	usage_minutes	times_opened
2024-01-01	YouTube	120	1
2024-01-01	Chrome	60	1
2024-01-01	YouTube	95	2
2024-01-02	Instagram	80	1
2024-01-02	WhatsApp	75	1

 Methodology / Approach

1. Data Collection → Prepared synthetic dataset of 1000 entries simulating real user app usage.
2.  Data Preprocessing → Using Pandas to parse dates, group apps, and handle duplicates.
3.   Feature Engineering → Introduced times_opened to measure session counts.
4.     xploratory Data Analysis (EDA) → Daily totals, app-level totals, frequency counts.
5.  Visualization → Charts to show trends and distributions.
6.   Insight Generation → Deriving actionable insights from analytics.

 Analysis & Functions
1. Daily Usage
def daily_usage(df):
    return df.groupby("date")["usage_minutes"].sum()


 Shows total screen time per day.

2. App Usage
def app_usage(df):
    return df.groupby("app_name")["usage_minutes"].sum().sort_values(ascending=False)


 Shows most time-consuming apps.

3. Top Apps
def top_apps(df, n=5):
    return app_usage(df).head(n)


 Shows top 5 apps by usage.

4. Average Daily Usage
def average_usage(df):
    return df.groupby("date")["usage_minutes"].sum().mean()


 Shows average daily screen time.

5. Most Opened Apps
def most_opened_apps(df, n=5):
    return df.groupby("app_name")["times_opened"].max().sort_values(ascending=False).head(n)


 Shows apps opened most frequently.

6. Average Session Length
def avg_session_length(df):
    return (df.groupby("app_name")["usage_minutes"].sum() /
            df.groupby("app_name")["times_opened"].max()).sort_values(ascending=False)


 Average minutes per app opening.

 Visualizations
 Daily Usage (Line Chart)

Shows screen time trend across dates.

plot_daily_usage(daily_usage(df))

 App Usage (Bar Chart)

Compares total time spent across apps.

plot_app_usage(app_usage(df))

 App Opens (Bar Chart)

Shows how many times each app was opened.

plot_app_opens(df)

 How to Run

Clone repository:

git clone https://github.com/your-username/screen-time-analysis.git
cd screen-time-analysis


Install dependencies:

pip install -r requirements.txt


Run main script:

python src/main.py


Or use in Jupyter Notebook:

df = load_data("screen_time_dataset_with_opens.csv")
plot_daily_usage(daily_usage(df))

 Results & Insights

Daily Usage → Average screen time ~ 250 minutes/day.
Most Used Apps → YouTube, Instagram, WhatsApp dominate.
Most Opened Apps → WhatsApp & Gmail are opened frequently but sessions are short.
Session Lengths → YouTube sessions are longer per open, while WhatsApp has short frequent sessions.
Trend Observation → Weekends show higher screen time than weekdays.

 Future Enhancements

Add hourly usage breakdown.
Multi-user dataset support.
Predictive analysis using ML (forecast future usage).
Integration with real device APIs (Android/iOS).
Dashboard (Streamlit / Flask) for interactive visualizations.

 Real-world Applications

Digital Wellbeing apps.
Parental control dashboards.
Productivity tracking tools for professionals.
User behavior analytics for app developers.
Healthcare research on digital addiction.

 Learnings

From this project, I learned:
Using Pandas & NumPy for large-scale data handling.
Exploratory Data Analysis (EDA) techniques.
Designing modular Python code with functions and modules.
Data visualization best practices.
Real-world application of Data Analytics in Digital Health.
Internship/Project Relevance

This project was part of my Data Analytics Internship, where I worked on real-world inspired problems.
It demonstrates end-to-end project skills: dataset preparation, analytics, visualization, documentation, and GitHub publishing.

Name: D. Munibabu
Degree: B.Tech – Computer Science & Technology
Focus Areas: Python, Data Analytics
