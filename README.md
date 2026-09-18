# 🚕 Chicago Taxi Trip Analysis

Exploratory data analysis of Chicago taxi trips using **Python**, **Pandas**, **Matplotlib**, and statistical hypothesis testing, with a focus on taxi market activity, destination patterns, and the relationship between weather conditions and airport trip duration.

## 📌 Context

Understanding urban transportation patterns can help identify areas of high passenger demand, differences in activity among transportation providers, and external factors that may affect travel times.

In this project, taxi trip data from **Chicago** was analyzed to explore the activity of taxi companies, identify the neighborhoods receiving the highest number of trips, and investigate whether adverse weather conditions are associated with changes in trip duration between the Loop and O'Hare International Airport.

The project was developed as part of my Data Science studies and reorganized for portfolio presentation, preserving the analytical process and results.

## 🎯 Problem

The main objective was to explore Chicago taxi activity and answer questions such as:

- Which taxi companies recorded the highest number of trips?
- How concentrated is taxi activity among companies?
- Which Chicago neighborhoods receive the highest average number of taxi trips?
- What are the main destination patterns observed in the data?
- Does the average duration of Saturday trips from the Loop to O'Hare International Airport differ under adverse weather conditions?

The project also required data quality validation and statistical hypothesis testing to evaluate whether the observed difference in trip duration was statistically significant.

## 📊 Dataset

The analysis uses three datasets containing information about taxi companies, destination neighborhoods, and airport trips.

### `moved_project_sql_result_01.csv`

Contains taxi company activity from November 15–16, 2017:

- `company_name` — taxi company name
- `trips_amount` — number of trips recorded for the company

### `moved_project_sql_result_04.csv`

Contains information about Chicago neighborhoods where taxi trips ended:

- `dropoff_location_name` — destination neighborhood
- `average_trips` — average number of trips ending in the neighborhood during November 2017

### `moved_project_sql_result_07.csv`

Contains Saturday trips from the Loop to O'Hare International Airport:

- `start_ts` — trip start date and time
- `weather_conditions` — weather conditions when the trip started
- `duration_seconds` — trip duration in seconds

## 🔎 Approach

The project followed a structured exploratory and statistical analysis workflow:

1. Data loading and initial inspection
2. Data type validation
3. Missing value analysis
4. Duplicate record investigation
5. Identification of the top destination neighborhoods
6. Analysis of taxi company activity
7. Visualization of trip distribution across companies
8. Visualization of the most frequent destination neighborhoods
9. Segmentation of airport trips by weather conditions
10. Formulation of null and alternative hypotheses
11. Statistical comparison of trip duration between weather groups
12. Interpretation of statistical and business findings

## 🧹 Data Preparation

Before performing the analysis, the datasets were inspected for consistency and quality.

The preparation stage included:

- verification of dataset dimensions;
- validation of column data types;
- explicit identification of missing values;
- investigation of duplicated records;
- conversion of timestamps to datetime format;
- validation of the variables required for the statistical analysis.

Repeated rows in the airport-trip dataset were retained because identical trip attributes can occur for different rides and the available data does not provide a unique trip identifier that would allow them to be classified confidently as erroneous duplicates.

## 📈 Analysis

### Taxi company activity

Taxi companies were compared according to the number of trips recorded between November 15 and 16, 2017.

The analysis shows an uneven distribution of activity, with a relatively small group of companies accounting for substantially more trips than the remaining operators.

### Top destination neighborhoods

Chicago neighborhoods were ranked according to the average number of taxi trips ending in each location.

The top 10 destinations reveal that taxi drop-off activity is concentrated in a limited number of neighborhoods, indicating areas with consistently higher passenger demand.

### Weather and airport trip duration

Saturday trips from the Loop to O'Hare International Airport were divided into two groups according to weather conditions:

- `Good`
- `Bad`

Average trip duration was then compared between these groups.

## 🧪 Hypothesis Testing

The statistical analysis investigated whether weather conditions were associated with different average trip durations.

**Null hypothesis (H₀):**

The average duration of Saturday trips from the Loop to O'Hare International Airport is the same under good and bad weather conditions.

**Alternative hypothesis (H₁):**

The average duration of Saturday trips from the Loop to O'Hare International Airport differs between good and bad weather conditions.

A significance level of **α = 0.05** was adopted.

Because the two weather groups are independent and equal population variances should not be assumed, **Welch's two-sample t-test** was used.

The resulting p-value was below the selected significance level, providing sufficient statistical evidence to reject the null hypothesis for the analyzed dataset.

Trips under adverse weather conditions also showed a higher average duration than trips under good weather conditions.

## 💡 Key Findings

The analysis reveals several patterns within the available Chicago taxi data:

- taxi activity is concentrated among a relatively small number of companies;
- some destination neighborhoods receive substantially more taxi trips than others;
- high-demand destinations can be clearly identified from average drop-off activity;
- Saturday trips from the Loop to O'Hare are longer on average in the adverse-weather group;
- the difference in average trip duration between good and bad weather conditions is statistically significant at the 5% level.

These findings describe patterns and statistical associations observed in the available dataset and should not automatically be interpreted as causal relationships.

## 🚀 Business Applications

The insights identified in this analysis could support decisions such as:

- identifying areas with consistently high transportation demand;
- supporting taxi fleet allocation and operational planning;
- understanding competitive concentration among taxi companies;
- anticipating travel-time differences during adverse weather;
- improving airport transfer planning and estimated arrival times;
- supporting demand forecasting and service availability decisions.

## ⚠️ Limitations

The analysis is based on historical data from a specific period in Chicago and should not automatically be generalized to other periods or transportation markets.

The available datasets also do not include every factor that could influence trip duration, such as detailed traffic conditions, route selection, accidents, road closures, or trip-level identifiers.

Therefore, the statistically significant relationship between weather conditions and trip duration should be interpreted as an association rather than proof that weather alone caused the observed difference.

## 🛠️ Technologies

- Python
- Pandas
- Matplotlib
- SciPy
- Jupyter Notebook
- Exploratory Data Analysis
- Statistical Hypothesis Testing

## 📁 Repository Structure

chicago-taxi-trip-analysis/
│
├── README.md
│
├── data/
│   ├── README.md
│   ├── moved_project_sql_result_01.csv
│   ├── moved_project_sql_result_04.csv
│   └── moved_project_sql_result_07.csv
│
└── notebook/
    ├── README.md
    └── chicago_taxi_trip_analysis.ipynb
