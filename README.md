# Yulu Business case study :  Hypothesis Testing

## About Yulu

Yulu is India’s leading micro-mobility service provider, which offers unique vehicles for the daily commute. Starting off as a mission to eliminate traffic congestion in India, Yulu provides the safest commute solution through a user-friendly mobile app to enable shared, solo and sustainable commuting.

Yulu zones are located at all the appropriate locations (including metro stations, bus stands, office spaces, residential areas, corporate offices, etc) to make those first and last miles smooth, affordable, and convenient!

Yulu has recently suffered considerable dips in its revenues. They have contracted a consulting company to understand the factors on which the demand for these shared electric cycles depends. Specifically, they want to understand the factors affecting the demand for these shared electric cycles in the Indian market.

🎯 Objective

The company wants to know:

Which variables are significant in predicting the demand for shared electric cycles in the Indian market?
How well those variables describe the electric cycle demands

## Dataset

| Column Name  | Description                                                                                                                                     |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| `datetime`   | Date and time of the record.                                                                                                                 |
| `season`     | Season (1: spring, 2: summer, 3: fall, 4: winter).                                                                                          |
| `holiday`    | Indicates whether the day is a holiday (extracted from [DCHR Holiday Schedule](http://dchr.dc.gov/page/holiday-schedule)).                   |
| `workingday` | Indicates if the day is neither a weekend nor a holiday (1: yes, 0: no).                                                                     |
| `weather`    | Weather conditions: <br> 1: Clear, Few clouds, partly cloudy <br> 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist <br> 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds <br> 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog |
| `temp`       | Temperature in Celsius.                                                                                                                      |
| `atemp`      | Feels-like temperature in Celsius.                                                                                                           |
| `humidity`   | Humidity percentage.                                                                                                                          |
| `windspeed`  | Wind speed in km/h.                                                                                                                          |
| `casual`     | Count of casual users.                                                                                                                        |
| `registered`  | Count of registered users.                                                                                                                    |
| `count`      | Total count of rental bikes (including both casual and registered users).                                                                     |


# steps performed

1. **Import the Dataset**: Loaded the dataset and performed initial checks on its structure and characteristics.

2. **Exploratory Data Analysis**: Conducted exploratory data analysis to understand the dataset better.

3. **Establish Relationships**: Analyzed the relationship between the dependent variable (Count) and independent variables (Working Day, Weather, Season, etc.).

4. **Hypothesis Testing**: Selected appropriate tests to check:
   - The effect of Working Day on the number of electric cycles rented.
   - Whether the number of cycles rented differs across different seasons.
   - Whether the number of cycles rented differs under varying weather conditions.
   - The dependency of Weather on Season (analyzing the relationship between two predictor variables).

5. **Set Up Hypotheses**:
   - Null Hypothesis (H0): [State specific null hypotheses based on the tests above].
   - Alternate Hypothesis (H1): [State specific alternate hypotheses based on the tests above].

6. **Check Assumptions**: Assessed the assumptions of the selected tests (Normality and Equal Variance) using visual methods (Histogram, Q-Q plot) and statistical tests (Levene’s test, Shapiro-Wilk test).

7. **Continue Analysis**: Proceeded with the analysis even if some assumptions failed, corroborating findings through visual analysis and reporting any discrepancies.

8. **Set Significance Level**: Established a significance level (alpha) for the hypothesis tests.

9. **Calculate Test Statistics**: Computed the test statistics for the relevant tests.

10. **Decision Making**: Made decisions on accepting or rejecting the null hypothesis based on the results.

11. **Inference**: Drawn inferences from the analysis to summarize findings and implications.

# Business Recommendations/Insights

1. **Distribution Analysis**: The distributions for "Temperature" and "Wind Speed" show equal mean and median, indicating symmetry around the central value, although they are right-skewed (mode < mean). In contrast, "Humidity" is left-skewed (mode > mean), with data points clustering towards the right.

2. **Bike Rentals Summary**: The total bike rentals were significantly higher on working days compared to holidays. Rentals peaked in Weather Category 1 and Season 3, followed by Seasons 2 and 4.

3. **Impact of Working Days**: Both t-test and z-test results indicate no significant mean difference in bike rentals between working days and holidays, as the p-value exceeds the alpha level, suggesting no evidence of influence beyond random chance.

4. **Seasonal Variations**: The Kruskal-Wallis test reveals fluctuations in bike usage across the four seasons, indicating no equality. Focusing on the top two seasons through targeted strategies may enhance business prosperity.

5. **Weather Pattern Fluctuations**: Similarly, the Kruskal-Wallis test shows that bike usage varies across weather conditions, with no equality among them. Identifying the top two weather patterns can guide strategic decisions.

6. **Weather and Season Relationship**: Weather conditions are generally influenced by the season, though rare deviations can occur. Most weather variations align with seasonal changes.

7. **Correlation with Humidity**: A negative correlation between humidity and bike rentals suggests that less humid conditions could boost demand, although the correlation is weak, indicating other influencing factors.

8. **Correlation with Apparent Temperature**: A positive Spearman rank correlation between bike rentals and apparent temperature (atemp) indicates that as atemp increases, so does the demand for cycles. However, further variable analysis is needed for reliable conclusions.

9. **Influence of Continuous Variables**: The p-values for continuous variables were below the alpha level, signifying their influence on bike rentals. While these statistics provide some insights, a comprehensive understanding requires examining the overall F-statistic and combined p-values of all independent variables (season, weather, working day).
