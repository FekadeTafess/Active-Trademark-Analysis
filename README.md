# Active-Trademark-Analysis
Clean, standardize, and analyze 60+ years of active trademark registrations from the State of Oregon to uncover business growth trends and geographic hotspots.

A research question I considered: How have active trademark registrations in Oregon changed over time, and which cities show the highest concentration of registrations?

Data Source:

The source of the data comes from the OREGON.GOV Open Data Portal, where I focused on a dataset titled Active Trademark Registrations, recorded by the Secretary of State’s Corporate Division. This dataset helps identify trademarks—such as specific words, symbols, or designs—that are uniquely used to distinguish goods and services sold by companies in Oregon and surrounding areas.

When I initially examined the Active Trademark Registration data, I noticed several inconsistencies. Some correspondent names were incomplete or not fully spelled out, the date-time values were not stored as strings, and there were missing values in the address-related columns. To address these issues, I used Python (Pandas) to fill missing values with “N/A” where no data was available.

Python Analysis:

I used Python Pandas to format the registration_date column into a proper date-time object. Since the dates were originally stored in a raw format, converting them allowed me to perform a chronological analysis. This made it possible to visualize trademark registration counts over time using line charts and to observe overall trends.

To preserve data integrity, I handled the many missing values in the DataFrame by filling them with “Unknown” or “N/A” instead of deleting entire columns. I was initially conflicted about keeping certain columns, especially address-related fields, since they did not always play a significant role in the analysis. However, I chose to retain them for completeness. I also filled missing ZIP codes with a placeholder value of 00000 for unknown locations.

Additionally, I standardized firm names to better identify important companies. Using a custom Python function (def standardize()), I normalized business names to clearly distinguish between entities such as LLCs and LLPs, which were difficult to differentiate in the raw data due to inconsistent naming conventions.

SQL Coding:

In this section, I imported SQLite while working within a Google Colab notebook. I used SQL queries to identify the top cities with the highest trademark registration counts in descending order. The results showed that Portland had the highest number of registrations, which aligns with its larger population and its status as the largest city in Oregon.

I also used SQL aggregate functions and date-string formatting to transform raw time-series data into summarized yearly growth trends, allowing for clearer interpretation of registration patterns over time.

Power BI:

After cleaning the Active Trademark dataset, I exported it as a CSV file and used Power BI to create visualizations such as bar graphs and line charts. These visuals helped conceptualize the analysis by showing trademark registration counts across major West Coast cities, with Portland consistently ranking highest.

I also created a line chart to illustrate the increasing trend in trademark registrations over the years and included a forecast to estimate potential future changes. Based on the trend, it appears likely that more firms and companies will continue to register trademarks as interest in selling goods and services increases.

Challenges:

One of the main challenges I faced was deciding whether to limit the analysis to specific cities or states on the West Coast. While the dataset included cities from the East Coast and Midwest, narrowing the scope geographically may have produced more focused results. (I struggled in finding a way to not include the non-oregon cities since it already was apaert of the data I downloaded.)

Data cleaning also presented challenges, particularly in selecting the correct functions to address inconsistencies and missing values. I relied on AI-assisted guidance to improve my approach, especially when developing visualizations and optimizing the overall analysis workflow. I had to work through some of SQL code to see what would fit best for my research question. 
