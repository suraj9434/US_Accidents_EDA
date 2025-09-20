# U.S. Road Accidents (2016–2022) EDA Report

## Project Overview

This analysis examines a dataset of **500,000** U.S. traffic accidents (2016–2023) to uncover patterns across **time, geography, weather, and road environments**. The goal is to provide insights that can guide safety strategies, urban planning, and policy decisions.

### Key Insights

- **Time Patterns**: Accidents increased steadily from 2016 to 2022, with particularly sharp rises after 2020. Crashes tend to cluster around **commuting hours (7–9 AM, 4–6 PM)**. Winter months, especially **December**, show higher crash counts, while summer months (June–July) generally record fewer accidents.

- **Geographic Patterns**: Larger states like **California, Texas, and Florida** report the most accidents, but smaller states like **South Carolina** and **Montana** have higher accident rates when normalized by population.

- **Environmental Factors**: Most accidents occur in clear weather, but severity increases in rain, snow, and fog. **Traffic signals** and **crossings** dominate in accident frequency, while **junctions** and **railways** are less frequent but carry higher severity.

### Recommendations

- Improve safety measures in high-risk areas like busy intersections and junctions with better signage, adaptive signals, and speed enforcement.
- Focus on safety campaigns during rush hours and winter months.
- Deploy weather-responsive measures on roads.
- Tailor interventions for states with high per-capita accident rates, not just high-volume states.

### Limitations

- Missing weather data may introduce bias into severity analysis.
- Accident reporting may vary across jurisdictions.
- Population normalization was done only for 2022; extending this across years would improve accuracy.

---

## Data

### Dataset Information

- **Source**: [U.S. Accidents (2016-2023)](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents/data?select=US_Accidents_March23.csv)
- **Size**: 500,000 sampled records
- **Key Variables**: 
  - Accident severity (1–4)
  - Timestamps
  - Location (state, city, lat/lng)
  - Weather conditions
  - Environmental flags (junction, traffic signal, etc.)

### Additional Data Source

- **State Population Estimates (2022)** for normalization: [U.S. Census](https://www2.census.gov/programs-surveys/popest/datasets/2020-2024/state/totals/)

---

## Setup and Requirements

1. **R Packages** used:
   - `readr`, `dplyr`, `tidyverse`, `tidyr`, `lubridate`, `stringr`
   
2. **Installation**:
   - Install the necessary R packages by running:
     ```r
     install.packages(c("readr", "dplyr", "tidyverse", "tidyr", "lubridate", "stringr"))
     ```

---

## Data Cleaning & Preprocessing

- **Data Selection**: Relevant columns like `Severity`, `Start_Time`, `End_Time`, `Start_Lat`, `Start_Lng`, and key weather variables were selected.
- **Missing Data**: Columns with high missingness (e.g., `End_Lat`, `End_Lng`, `Wind_Chill`, `Precipitation`) were excluded or handled accordingly.
- **Date & Time**: Time was converted into a usable format with the `lubridate` package.

---

## Key Analyses

### 1. Accident Severity Analysis

#### 1a. Severity Distribution
The distribution of accidents across severity levels reveals that most accidents are of **minor to moderate severity (Severity 2)**, while severe accidents (Severity 4) are less frequent but critical.

#### 1b. Accident Duration by Severity
Accident durations show that:
- Most accidents resolve within 1–2 hours.
- Severe accidents typically last longer, with some extreme outliers in the data.

#### 1c. Capping Durations
To account for extreme outliers, accident durations were capped at 72 hours. The median duration provides a stable measure of typical accident clearances.

---

### 2. Temporal Patterns

#### 2a. Accidents per Year
Accidents increased steadily from 2016 to 2022, with a sharp rise after 2020.

#### 2b. Accidents per Month
Accidents tend to dip in spring and summer, with peaks in late fall and winter months, particularly in December.

#### 2c. Accidents by Year and Month (Heatmap)
A heatmap analysis of accidents by year and month provides a clearer view of seasonal patterns, emphasizing the spike in December.

---

### 3. Environmental Features

#### Road Features and Severity
- **Traffic signals, crossings, and junctions** have the highest accident frequency.
- **Junctions** have the highest severity on average, while **railways** have low frequency but high severity.

---

## Conclusion

This exploratory data analysis highlights important trends in U.S. road accidents over the past several years, providing key insights into patterns of severity, time, and environmental factors. The findings can guide future policy decisions and traffic safety interventions.

---

## Future Research Directions

- Investigating traffic density and hospital outcomes for better prediction of accident severity and consequences.
- Expanding the dataset to include more granular data for each year and exploring the impacts of other variables such as road type or driver demographics.

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for more details.

---

## References

1. [U.S. Accidents Dataset (Kaggle)](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents/data?select=US_Accidents_March23.csv)
2. [U.S. Census State Population Estimates](https://www2.census.gov/programs-surveys/popest/datasets/2020-2024/state/totals/)
