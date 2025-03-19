# US-hurricane

1. **Data Loading & Cleaning:**
- The function `load_and_clean_data` reads the hurricane CSV file, removes rows with missing or anomalous values (including wind speeds >200 knots), and cleans the hurricane names.
- Feature engineering is performed by creating new columns such as `decade`, `name_initial` (only if `name_clean` is valid), `intensity_metric`, `strong_hurricane` (flagging Category 4 & 5), and both categorical and numeric versions of computed hurricane categories.

2. **Visualization Functions:**
- Separate functions create Plotly figures:
    - ***Scatter Plot:*** A bubble chart showing max wind speed vs. central pressure.
    - ***Strong Hurricanes Line Plot:*** Displays the count of strong hurricanes per decade with a moving average, linear regression, and polynomial regression.
    - ***Choropleth Map:*** Shows hurricane frequency by state, using the exploded `states_list` column.
    - ***Category Bar Chart & Box Plot:*** Visualize hurricane counts by category and wind speed distributions.
    - ***Histogram:*** Displays the distribution of max wind speeds.
    - ***Stacked Bar Chart:*** Shows hurricane name initials by decade, with an optional top‑N filter.

3. **App Layout:**
- The layout uses Dash Bootstrap Components and is organized into rows and tabs.
- Filters (dropdowns, slider, and input) are provided at the top.
- Tabs (Overview, Geography, Categories, Naming Trends, Distributions) display corresponding graphs and analysis.
- By default, the year range slider is set to cover the entire dataset period.

4. **Callbacks:**
- The main callback updates all figures and analysis texts based on the selected filters, including additional trend analyses for strong hurricanes and naming trends (using exponential smoothing).
- A separate callback resets all filters to default values when the reset button is clicked.

5. **Running the App:**
- Finally, the Dash server is launched in debug mode.
