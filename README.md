# U.S. Road Accidents (2016–2022) Exploratory Data Analysis

**Author:** Suraj Shrestha

## Project Overview

This project presents an exploratory data analysis (EDA) of a **500,000-record sample** from the U.S. Traffic Accidents dataset, covering the period from 2016 to March 2023. The goal is to uncover patterns and insights across **time, geography, weather, and road environments** to inform road safety strategies, urban planning, and policy decisions.

This EDA demonstrates the ability to clean messy real-world data, uncover meaningful insights, and translate analytical findings into actionable recommendations.

👉 **View Interactive Dashboard:** [RPubs Link](https://rpubs.com/surajshrestha7494/1346885)

## Key Findings

The analysis reveals three main themes:

#### 1. Temporal Patterns
*   **Yearly Trend:** Accident counts increased steadily from 2016 to 2022, more than quadrupling over the period, with a sharp rise after 2020.
*   **Daily Peaks:** Crashes cluster around weekday commuting hours, specifically **7–9 AM** and **4–6 PM**.
*   **Seasonal Effects:** Winter months, particularly **December**, consistently show the highest crash counts. Summer months (June–July) generally record the fewest accidents.

#### 2. Geographic Patterns
*   **Raw Counts:** Large, populous states like **California, Texas, and Florida** report the most accidents due to high traffic volume.
*   **Per-Capita Rates:** When normalized by population, smaller states such as **South Carolina and Montana** rank significantly higher, revealing hidden hotspots with disproportionately high risk for residents.

#### 3. Environmental Factors
*   **Weather:** While most accidents occur in clear weather (due to higher exposure), accident **severity increases significantly** in adverse conditions like rain, snow, and fog.
*   **Road Features:** Traffic signals and crossings are the most frequent sites for accidents. However, crashes at **junctions and railway crossings** are less common but are associated with higher average severity.

## Recommendations

Based on the insights, the following actions are recommended:

1.  **Improve High-Risk Infrastructure:** Enhance safety at busy intersections and junctions with better signage, adaptive traffic signals, and increased speed enforcement.
2.  **Targeted Safety Campaigns:** Launch public awareness campaigns focused on high-risk periods like rush hours and winter months.
3.  **Deploy Weather-Responsive Measures:** Implement dynamic speed limits, enhanced road treatments, and real-time alerts during adverse weather.
4.  **Prioritize High-Risk States:** Allocate resources and tailored interventions to states with high per-capita accident rates, not just those with high raw counts.
5.  **Future Research:** Incorporate additional data like traffic density, hospital outcomes, and fatality records to build a more comprehensive model of accident consequences and prevention strategies.

## Data Sources

The analysis relies on two primary datasets:

1.  **U.S. Accidents (2016-2023)**
    *   **Source:** Kaggle
    *   **Link:** [https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents/data](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents/data)
    *   **Download Instructions:** From the link above, download the `US_Accidents_March23.csv` file. Note that this project uses a 500,000-record sample of this dataset for computational efficiency.

2.  **U.S. Census Bureau State Population Estimates (2022)**
    *   **Source:** U.S. Census Bureau
    *   **Link:** [https://www2.census.gov/programs-surveys/popest/datasets/2020-2024/state/totals/](https://www2.census.gov/programs-surveys/popest/datasets/2020-2024/state/totals/)
    *   **Download Instructions:** From the link above, download the `NST-EST2024-POPCHG2020-2024.csv` file.

## Tools and Libraries

This analysis was conducted in **R** using RStudio. The key libraries used include:
*   `dplyr` & `tidyverse` for data manipulation
*   `lubridate` for date/time processing
*   `ggplot2` for data visualization
*   `maps` & `usmap` for geographic plotting

## How to Run This Analysis

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    ```
2.  **Download the data:** Use the links in the **Data Sources** section to download the required `.csv` files and place them in the project's root directory.
3.  **Install R packages:** Open R or RStudio and run the following command in the console:
    ```r
    install.packages(c("readr", "dplyr", "tidyverse", "tidyr", "lubridate", "stringr", "ggplot2", "maps", "usmap"))
    ```
4.  **Run the analysis:** Open the `.Rmd` file in RStudio and click the "Knit" button to generate the full report.

## Limitations

*   **Missing Data:** Significant missingness in weather-related columns could introduce bias in the environmental analysis.
*   **Reporting Variability:** Accident reporting standards and diligence may vary by state or jurisdiction, potentially affecting geographic comparisons.
*   **Static Population Data:** Population normalization was performed using 2022 estimates only. Applying year-specific population data would improve the accuracy of time-series analysis.
