# Analyze and Visualize the Current Global Scenario of COVID-19

## Overview
This project analyzes and visualizes the global COVID-19 situation and explores the medical conditions contributing to COVID-19-related deaths. The goal is to present complex data in an intuitive, interactive format that helps users understand patterns and insights.

## Features
1. **Interactive Visualizations:**
   - Bar graphs for comparing key metrics.
   - Scatter plots showing relationships between variables (e.g., cases per million vs. deaths per million).
   - Choropleth maps for a global overview of COVID-19 metrics.
   - Word clouds for textual analysis of contributing medical conditions.

2. **Insights Provided:**
   - COVID-19 cases, deaths, and recovery statistics.
   - Geographical variations in COVID-19 impact.
   - Common medical conditions contributing to COVID-19-related deaths.

## Tools and Libraries
- **Plotly Express**: For creating interactive plots.
- **Wordcloud**: For generating visual representations of text data.
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical computations.
- **Matplotlib**: For supplementary visualizations.


## Visualizations

### Global COVID-19 Scenario
- **Bar Graphs:**
  - Compare total cases and deaths across countries.
  ![newplot (5)](https://github.com/user-attachments/assets/f6d24673-c02f-4ae1-87a6-20f18200ba48)
  ![newplot (6)](https://github.com/user-attachments/assets/0d83b8d2-deb7-4829-9186-3f25ea8fc173)


  
- **Scatter Plots:**
  - Visualize relationships between `Totalcases/1M` and `TotalDeath/1M`.
  - The interesting feature of this plot is that while the plot displayed is for all the countries combined, the numbers on the axes show the individual country stats of which the legend is selected.
  - Example:
    ```python
    px.scatter(df, x="Totalcases/1M", y="TotalDeath/1M", color="Country")
    ```
    ![newplot (7)](https://github.com/user-attachments/assets/cab96e65-2be4-4a11-9741-58f4abad74b8)


- **Choropleth Maps:**
  - Display global variations in COVID-19 cases and deaths using ISO Alpha-3 country codes.
  - Example:
    ```python
    px.choropleth(df, 
              locations="iso_alpha",
              hover_name="Country",
              color="TotalDeath/1M",
              projection="orthographic",
              color_continuous_scale="Viridis")
    ```
    ![newplot (8)](https://github.com/user-attachments/assets/6596b57d-e481-41c9-9db1-11ef50cb54c3)


### Medical Conditions Contributing to Death
- **Bar Graphs:**
  - Rank the most common pre-medical conditions the patient suffered from.
  - Example:
    ```python
    px.bar(df1, x="Age Group", y="COVID-19 Deaths", color="Condition", hover_name="Condition", log_y=True)
    ```
    ![newplot (10)](https://github.com/user-attachments/assets/200135cc-318f-48da-88ad-87346d00326a)
  
- **Word Clouds:**
  - Highlight the frequency of key medical terms related to COVID-19 deaths.
  ![image](https://github.com/user-attachments/assets/c9ddbf77-64e7-4c11-b996-fb073242b097)

  
