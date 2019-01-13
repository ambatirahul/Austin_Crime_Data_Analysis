# Seattle_Crisis_Data_Analysis

Table of Contents
=================
  * [Data sources](#data-sources)
  * [Data cleaning](#data-cleaning)
  * [Data analysis](#data-analysis)
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
 
 This [Data cleaning notebook](https://github.com/ambatirahul/Seattle_Crisis_Data_Analysis/blob/master/DataWrangling/DataWrangling.ipynb) provides information on what has been done to refine the data.

## Data analysis

 ![beat](/Images/beat.PNG)
 ![sector_precinct](/Images/sector_precinct.PNG)
 ![sector_v_precinct](/Images/sector_v_precinct.PNG)
 ![sector_v_race](/Images/sector_v_race.PNG)
 ![sector_v_officer_gender](/Images/sector_v_officer_gender.PNG)
 ![officer_squad_desc](/Images/officer_squad_desc.PNG)
 ![officer_squad_desc_top50](/Images/officer_squad_desc_top50.PNG)
 ![officer_precinct_desc](/Images/officer_precinct_desc.PNG)
 ![officer_precinct_desc_v_officer_precinct_desc](/Images/officer_precinct_desc_v_officer_precinct_desc.PNG)
 ![officer_bureau_desc](/Images/officer_bureau_desc.PNG)
 ![officer_precinct_desc_v_officer_bureau_desc](/Images/officer_precinct_desc_v_officer_bureau_desc.PNG)
 ![officer_year_of_exp_year_of_birth](/Images/officer_year_of_exp_year_of_birth.PNG)
 ![officer_race](/Images/officer_race.PNG)
 ![initial_call_type](/Images/initial_call_type.PNG)
 ![final_call_type](/Images/final_call_type.PNG)
 ![call_type](/Images/call_type.PNG)
 ![officer_year_of_exp_v_officer_gender](/Images/officer_year_of_exp_v_officer_gender.PNG)
 ![officer_year_of_birth_v_officer_gender](/Images/officer_year_of_birth_v_officer_gender.PNG)
 ![officer_race_v_officer_gender](/Images/officer_race_v_officer_gender.PNG)
 ![officer_year_of_exp_v_force_ind](/Images/officer_year_of_exp_v_force_ind.PNG)
 ![officer_year_of_birth_v_force_ind](/Images/officer_year_of_birth_v_force_ind.PNG)
 ![officer_race_v_force_ind](/Images/officer_race_v_force_ind.PNG)
 ![disposition](/Images/disposition.PNG)
 ![disposition_v_inital_call_type](/Images/disposition_v_inital_call_type.PNG)
 ![disposition_v_final_call_type](/Images/disposition_v_final_call_type.PNG)
 
## Time series analysis

## Machine learning

## Conclusion

## Conclusion
