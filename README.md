# Seattle_Crisis_Data_Analysis

Table of Contents
=================
  * [Data sources](#data-sources)
  * [Data cleaning](#data-cleaning)
  * [Data exploration and analysis](#data-exploration-and-analysis)
  * [Time series analysis](#time-series-analysis)
  * [Machine learning](#machine-learning)
  * [Conclusion](#conclusion)

## Data sources

 The data is accquired from City of [Seattle Open Data portal](https://data.seattle.gov/Public-Safety/Crisis-Data/i2q9-thny)

 And also available through [API Dev.Socrata](https://dev.socrata.com/foundry/data.seattle.gov/ri7i-gfqd)

## Data cleaning

 Start with initial exploring and having a general feel for the data

 Let's start by asking few questions
 * What are the features
 * What are the expected types (int, float, string, boolean)?
 * Is there obvious missing data ?
 * Is there other types of missing data that’s not so obvious ?

 ![results_df_info](/Images/results_df_info.PNG)

 Things to dealing with
 * Standard missing values (Pandas can detect them)
 * Non-standard missing values (different formats)
 * Unexpected missing values (can be mix of above two or totally different ones)
 They can be dealth with removing or replacing or doing some conversions or some combination of mentioned.

 And finally summarizing any missing values.

 The final processed or refined data info looks like this. <br/>
 ![results_df_info2](/Images/results_df_info2.PNG)

 Additional things done for refinement
 * Converted strings to categorical
 * Converted time to datetime format
 * Taking mean for floating numbers if missing or inconsistent
 * If not categorizable or fewer data points, clubbed into seperate category

 [Data cleaning notebook](https://github.com/ambatirahul/Seattle_Crisis_Data_Analysis/blob/master/DataWrangling/DataWrangling.ipynb) provides information on what has been done to refine the data.

## Data exploration and analysis

 Visualizing features

 * Beat  <br/>
 ![beat](/Images/beat.PNG)

 * Sector and Precinct  <br/>
 ![sector_precinct](/Images/sector_precinct.PNG)

 * Sector vs Precinct (combining above graphs)  <br/>
 ![sector_v_precinct](/Images/sector_v_precinct.PNG)

 * Sector vs Office race <br/>
 ![sector_v_race](/Images/sector_v_race.PNG)

 * Sector vs Officer gender count <br/>
 ![sector_v_officer_gender](/Images/sector_v_officer_gender.PNG)

 * Officer Squad desc <br/>
 ![officer_squad_desc](/Images/officer_squad_desc.PNG) <br/>
 There is one category which spikes, let's get top 50 categories.

 * Top 50 Officer squad <br/>
 ![officer_squad_desc_top50](/Images/officer_squad_desc_top50.PNG)<br/>
 TRAINING - FILED TRAINING SQUAD is one category which has been dealing with crisis.

 * Officer precinct desc <br/>
 ![officer_precinct_desc](/Images/officer_precinct_desc.PNG)<br/>
 Most of the occurrencies happened in SOUTH, WEST, EAST, NORTH, SOUTHWEST PCT

 * Officer precinct vs Officer squad <br/>
 ![officer_precinct_desc_v_officer_precinct_desc](/Images/officer_precinct_desc_v_officer_precinct_desc.PNG)

 * Officer bureau desc <br/>
 ![officer_bureau_desc](/Images/officer_bureau_desc.PNG)<br/>
 OPERATIONS BUREAU is the main bureau dealing with crisis.

 * Officer precinct vs Officer bureau <br/>
 ![officer_precinct_desc_v_officer_bureau_desc](/Images/officer_precinct_desc_v_officer_bureau_desc.PNG)<br/>
 Observed EAST, NORTH, SOUTH, SOUTHWEST, WEST PCT are the precincts where OPERATIONS BUREAU are the ones dealing with crisis.

 * Officer years of experience and year of birth <br/>
 ![officer_year_of_exp_year_of_birth](/Images/officer_year_of_exp_year_of_birth.PNG)

 * Officer race <br/>
 ![officer_race](/Images/officer_race.PNG)<br/>
 Majority are White officers.

 * Initial call type <br/>
 ![initial_call_type](/Images/initial_call_type.PNG)<br/>
 Top 2 are related to Suicide and emotional crisis.

 * Final call type <br/>
 ![final_call_type](/Images/final_call_type.PNG)<br/>
 Since this data is related to CRISIS, we see the final call type to be.

 * Call type <br/>
 ![call_type](/Images/call_type.PNG)<br/>
 Most are telephonic.

 * Officer year of birth vs Officer gender <br/>
 ![officer_year_of_exp_v_officer_gender](/Images/officer_year_of_exp_v_officer_gender.PNG) <br/>
 Majority is less than 4 years of experience.

 * Officer year of birth vs Officer gender <br/>
 ![officer_year_of_birth_v_officer_gender](/Images/officer_year_of_birth_v_officer_gender.PNG)<br/>
 i)   Most of them are from 1977 - 1992. <br/>
 ii)  From 1985-1990 there is an uptick of hires, but female officers were hired less. <br/>
 iii) From 1985 there is an upward trend of hiring more female officers.

 * Officer race vs Officer gender <br/>
 ![officer_race_v_officer_gender](/Images/officer_race_v_officer_gender.PNG)<br/>
 Most female officers are white.

 * Officer year of birth vs Use of force indicator <br/>
 ![officer_year_of_exp_v_force_ind](/Images/officer_year_of_exp_v_force_ind.PNG)

 * Officer year of birth vs use of force indicator
 ![officer_year_of_birth_v_force_ind](/Images/officer_year_of_birth_v_force_ind.PNG)

 * Officer race vs Use of force indicator <br/>
 ![officer_race_v_force_ind](/Images/officer_race_v_force_ind.PNG)

 * Disposition count <br/>
 ![disposition](/Images/disposition.PNG)

 * Disposition vs Initial call type <br/>
 ![disposition_v_inital_call_type](/Images/disposition_v_inital_call_type.PNG)

 * Disposition vs Final call type <br/>
 ![disposition_v_final_call_type](/Images/disposition_v_final_call_type.PNG)

 There are **952** unique officers in this data set.

 Instead of dealing with all the cases, let's deal with officers who handled more than **100** cases.<br/>
 Extracting the data and doing analysis on the data.

 * Call type  <br/>
 ![call_type_top100](/Images/call_type_top100.PNG)

 * Final Call type  <br/>
 ![final_call_type_top100](/Images/final_call_type_top100.PNG)

 * Officer race  <br/>
 ![officer_race_top100](/Images/officer_race_top100.PNG)

 * Officer precinct vs Officer bureau <br/>
 ![officer_precinct_desc_v_officer_bureau_desc_top100](/Images/officer_precinct_desc_v_officer_bureau_desc_top100.PNG)

 * Officer squad desc  <br/>
 ![officer_squad_desc_top100](/Images/officer_squad_desc_top100.PNG)

 * Officer precinct desc  <br/>
 ![officer_precinct_desc_top100](/Images/officer_precinct_desc_top100.PNG)

 * Sector vs Officer gender  <br/>
 ![sector_v_officer_gender_top100](/Images/sector_v_officer_gender_top100.PNG)

 * Sector vs Officer race  <br/>
 ![sector_v_race_top100](/Images/sector_v_race_top100.PNG)

 * Officer precinct <br/>
 ![officer_precinct_desc](/Images/officer_precinct_desc.PNG)

 * Officer precinct vsTemplate <br/>
 ![officer_precinct_desc_df_template_grp_ge2](/Images/officer_precinct_desc_df_template_grp_ge2.PNG)

 * Officer year of experience greater than 30 <br/>
 ![officer_year_of_exp_mean_ge30yrs](/Images/officer_year_of_exp_mean_ge30yrs.PNG)


## Time series analysis

 * Reported time and Occurred time  <br/>
 ![ts_day_time](/Images/ts_day_time.PNG)<br/>
 There are no reporting before 05-15-2016, so removed date before 05-15-2016.

 * Reported time and Occurred time after 05-15-2016  <br/>
 ![ts_day_time_after_05](/Images/ts_day_time_after_05.PNG) <br/>
 There are certain time frames where there are more Crisis occurrences.

 * Time difference percentile  <br/>
 ![reported_minus_occurred_percentile](/Images/reported_minus_occurred_percentile.PNG)

 * Time difference percentile after 05-15-2016 <br/>
 ![reported_minus_occurred_percentile_after_05](/Images/reported_minus_occurred_percentile_after_05.PNG)

 * Distplot for time difference in days <br/>
 ![ts_days_distplot](/Images/ts_days_distplot.PNG) <br/>
 Usually it's handled with in a day.

 * Distplot for time difference in hours <br/>
 ![ts_hours_displot](/Images/ts_hours_displot.PNG) <br/>
 Most of the time it is handled within 5 hours of the reported time.

 * Reported vs Occurred date time plot <br/>
 ![ts_reported_v_occurred_date_time_after_05](/Images/ts_reported_v_occurred_date_time_after_05.PNG)

 * Reported vs Occurred time difference (15 minute rounding) <br/>
 ![ts_15min_rounding_after_05](/Images/ts_15min_rounding_after_05.PNG)

 * Reported vs Occurred time difference in hours <br/>
 ![ts_rolling_hours_after_05](/Images/ts_rolling_hours_after_05.PNG)

 * Reported vs Occurred time difference in days <br/>
 ![ts_rolling_day_time_after_05](/Images/ts_rolling_day_time_after_05.PNG) <br/>
 From the above graphs we see those occurrences spiking up during early part of the year.

 * Difference of hours <br/>
 ![ts_hours_diff_after_05](/Images/ts_hours_diff_after_05.PNG)

 * Difference of days <br/>
 ![ts_day_diff_after_05](/Images/ts_day_diff_after_05.PNG)

 * Difference of hours <br/>
 ![ts_24_hours_diff_after_05](/Images/ts_24_hours_diff_after_05.PNG)

 * Difference of weekdays <br/>
 ![ts_weekday_diff_after_05](/Images/ts_weekday_diff_after_05.PNG)

 * Time difference between Reported and occurred (in seconds)<br/>
 ![ts_reported_minus_occurred_date_time_diff](/Images/ts_reported_minus_occurred_date_time_diff.PNG) <br/>
 We see as the year goes on, the time difference also increases and we see early of the year the time difference reduces.<br/>
 And observing patterns we see the crisis cases appear (spikes up) during the early part of a year, and that's where the crisis team are active and response time is less.


 For further info about exploration and analysis refer [Data exploration and analysis notebook](https://github.com/ambatirahul/Seattle_Crisis_Data_Analysis/blob/master/AnalysisAndStoryTelling/DataAnalysis.ipynb) and for time series refer [Time Series notebook](https://github.com/ambatirahul/Seattle_Crisis_Data_Analysis/blob/master/AnalysisAndStoryTelling/TimeSeriesAnalysis.ipynb)


## Machine learning

## Conclusion
