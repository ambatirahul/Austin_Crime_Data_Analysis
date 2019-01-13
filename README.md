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
 - Most of them are from 1977 - 1992.
 - From 1985-1990 there is an uptick of hires, but female officers were hired less.
 - From 1985 there is an upward trend of hiring more female officers.
 
 * Officer race vs Officer gender <br/>
 ![officer_race_v_officer_gender](/Images/officer_race_v_officer_gender.PNG)<br/>
 More White female officers.
 
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
 
 [Data exploration and analysis notebook](https://github.com/ambatirahul/Seattle_Crisis_Data_Analysis/blob/master/AnalysisAndStoryTelling/DataAnalysis.ipynb)
 
## Time series analysis

## Machine learning

## Conclusion

## Conclusion
