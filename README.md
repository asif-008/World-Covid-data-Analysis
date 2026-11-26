# Exploring global COVID-19 data with SQL and Tableau

This follow-along project uses Alex Freberg’s SQL portfolio tutorial and historical data from Our World in Data. I used SQL Server to prepare summaries of reported cases, deaths and vaccinations, then explored geographic and time trends in Tableau.

[![Historical Tableau dashboard with global totals, a geographic breakdown and trends over time](https://public.tableau.com/static/images/Co/CovidDataanalysis_16740119126500/Dashboard1/1.png)](https://public.tableau.com/views/CovidDataanalysis_16740119126500/Dashboard1)

[Open the interactive Tableau dashboard](https://public.tableau.com/views/CovidDataanalysis_16740119126500/Dashboard1)

## From SQL to the map

The third Tableau query groups the records by location and population. It calculates `MAX(total_cases / population) * 100` to find the highest recorded cumulative case count relative to population in each group. This makes locations of different sizes easier to compare. The underlying measure counts reported cases, so it cannot tell us how many distinct residents had an infection.

The fourth query keeps the date in the grouping, providing a series for the trend view. Other sections join the deaths and vaccination tables by location and date, and use a window function to accumulate daily vaccine doses within each location.

[Explore the SQL queries](Covid_portfolio_project_scripts.sql) · [Visit the original data source](https://ourworldindata.org/covid-deaths)

The dashboard reflects the dataset used for this project. To run the SQL against another snapshot, import the corresponding deaths and vaccination tables and adjust the database and table names in the script.
