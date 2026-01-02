# Panic Data Analysis

## 🧩Problem Statement
Panic attacks are complex and can vary widely from person to person, depending on symptoms, sleep habits, lifestyle factors, age, triggers, and medical history. Although this information is available in structured dataset, it is difficult to understand these patterns by simply looking at raw data or single-view summaries. Important questions such as which symptoms are most common, how sleep and panic severity are related, or how panic attacks differ across age groups require deeper, structured analysis.

This project addresses this challenge by building a multi-page analytical report in Power BI that explores panic attack data from multiple perspectives. Each report page focuses on a specific aspect, such as symptom distribution, panic attack characteristics, behavioral patterns, and age-group analysis. By organizing insights across multiple report pages, the analysis allows users to gradually explore the data, uncover meaningful relationships, and gain a clearer understanding of panic attack patterns in a structured and interpretable way.


&nbsp;

## 📋Objectives
* Analyze the distribution of panic attack symptoms to identify which physical symptoms are most commonly reported across individuals.

* Examine panic severity using panic scores and attack duration, helping understand how intense and prolonged panic episodes are.

* Study the relationship between sleep hours and panic behavior, including how reduced sleep is associated with higher panic scores and attack frequency.

* Compare panic attack patterns across different age groups, focusing on variations in panic scores, sleep behavior, and attack duration.

* Assess the impact of different trigger reasons on panic attacks to understand how factors such as stress, anxiety, or lifestyle habits influence panic severity.


&nbsp;

🛠 Tools & Technologies

* Power BI Desktop – Data transformation and Multi-page report creation

* Snowflake (Cloud Data Warehouse) – Data storage

* Snowflake SQL Worksheet – Database and Table creation, Data validation using SQL queries

* Power Query Editor – Data profiling, Cleaning, Formatting, and Transformation

* CSV File – Source dataset uploaded into Snowflake

Techniques Used

* Cloud-based data ingestion (CSV → Snowflake)

* SQL-based data validation and exploration

* Data type standardization and conditional column creation

* Exploratory Data Analysis (EDA) using column profiling

* Interactive Slicers and Drill Through Filters



&nbsp;


🔄 Project Workflow

1️⃣ Snowflake Account Setup

A free trial Snowflake account was created to use Snowflake as the primary data source for this project.

2️⃣ Database and Table Creation in Snowflake

From the Snowflake home page, a SQL Worksheet was opened.

A new database named Power BI Project was created.

Inside this database, a table named Panic_Attack_Data was created by defining the required column names and data types using SQL.

The SQL statement was executed successfully, creating the table.

3️⃣ Data Upload into Snowflake

The Upload Local Files option was used to upload the CSV file from the local system.

The Power BI Project database was selected.

The option to create a new table was chosen, and data was loaded into the Panic_Attack_Data table.

A simple SELECT query was executed to verify that the data was inserted correctly, and the results were displayed as expected.

4️⃣ Connecting Snowflake to Power BI

A blank report was opened in Power BI Desktop.

Using Get Data, the Snowflake connector was selected.

Server and warehouse details were provided, followed by Snowflake login credentials.

After successful authentication, the list of Snowflake databases was displayed.

The Power BI Project database and Panic_Attack_Data table were selected and opened in Transform Data mode.

5️⃣ Data Transformation in Power Query

In Power Query Editor, Column Distribution, Column Quality, and Column Profile options were enabled to understand data completeness and structure.

All columns were converted to their appropriate data types.

A new conditional column named Panic Score (HML) was created to classify panic severity:

Panic score < 4 → Low

Panic score > 8 → High

Else → Medium

This helped categorize panic severity for better analysis and visualization.

6️⃣ DAX Calculated Column Creation

A DAX calculated column was created to group individuals by age:

Age Group =
SWITCH(
    TRUE(),
    PANIC_ATTACK_DATA[AGE] <= 30, "Youth",
    PANIC_ATTACK_DATA[AGE] <= 50, "Adults",
    PANIC_ATTACK_DATA[AGE] <= 64, "Senior Adults",
    "Super Seniors"
)

This enabled age-wise comparison of panic patterns across the report.

7️⃣ Report Development

Multiple visuals were created across several report pages, each focusing on different aspects such as symptoms, panic severity, sleep patterns, age groups, and trigger reasons.

Visuals were designed to support structured, step-by-step analysis rather than a single dashboard view.

8️⃣ Publishing to Power BI Service

After completing the report, the file was published to Power BI Service, enabling online access and sharing.

&nbsp;

## 💡 Key Insights
* Symptoms like sweating, shortness of breath, and dizziness are reported most often, making them some of the most common physical signs during panic attacks.

* People who get less sleep generally show higher panic scores, suggesting that poor sleep is closely linked to more severe panic experiences.

* Most panic attacks fall into the medium severity range, while severe panic episodes are less common but tend to last longer when they do occur.

* The length of panic attacks varies widely from person to person, with more intense panic episodes typically lasting longer than milder ones.

* Adults account for the highest number of reported panic attack cases, followed by senior adults and youth, indicating that panic attacks are most prevalent within the adult age group in this dataset.

&nbsp;

## Screenshots



<img width="1920" height="1080" alt="Screenshot 2026-01-02 115332" src="https://github.com/user-attachments/assets/571d0109-bb09-40da-9ad0-7d555b763556" />

&nbsp;

<img width="1920" height="1080" alt="Screenshot 2026-01-02 110919" src="https://github.com/user-attachments/assets/a8111ccc-d4b8-4380-b32c-a014da62a86a" />

&nbsp;

<img width="1920" height="1080" alt="Screenshot 2026-01-02 111034" src="https://github.com/user-attachments/assets/62513bc4-f51c-48ae-835d-3366518b32e2" />

&nbsp;



<img width="1920" height="1080" alt="Screenshot 2026-01-02 111205" src="https://github.com/user-attachments/assets/22b78ad4-8a51-4e47-8fb8-bd6e795f78fd" />

&nbsp;



<img width="1920" height="1080" alt="Screenshot 2026-01-02 111323" src="https://github.com/user-attachments/assets/59a8f113-7870-42f1-9786-502da3479a1d" />







