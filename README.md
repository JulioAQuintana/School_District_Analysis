# School_District_Analysis
Code Version 1.0
 #### Code file reference: PyCitySchools_Challenge.ipynb

## Project Overview
This analysis shows evidence of academic dishonesty; for reading and math grades for Thomas High School ninth graders that appear to have been altered. Although the school board does not know the full extent of the academic dishonesty, so with this analysis we will see before and after analysis with discrepances to describe how these changes affected the overall analysis.

## Results.

* ### 1. How is the district summary affected?
#### looks like minimal changes in final results compared before and after changes for dishonesty results based on district summary, when the round format is applied the   final results looks like same values in the averages of math, reading and overall results. in the following images we can see the tables for minimal changes 

####  Results before changes
 ![before update](https://github.com/JulioAQuintana/School_District_Analysis/blob/main/Resources/FinalResults.png)
  
####  Results after changes
![before update](https://github.com/JulioAQuintana/School_District_Analysis/blob/main/Resources/FinalResultsEnd.png)  
* ### 2. How is the school summary affected?
     ####  looks like minimal changes in final results compared before and after also for school summary, when the round format is applied the final results looks like same values in the averages of math, reading and overall results. in the following images we can see the tables for minimal changes
* ### 3.How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
     ####  It decrease in the overall passing result in 0.3% 
* ### 4.How does replacing the ninth-grade scores affect the following:
   * #### Math and reading scores by grade, decrease the values en every grade but when it is rounded no major changes appears
   * #### Scores by school spending = No major changes un the clasification of every school group
      code reference by column calculation
      ```Python script 
        # Calculate averages for the desired columns. 
        spending_math_scores = per_school_summary_df.groupby(["Spending Ranges (Per Student)"]).mean()["Average Math Score"]

        spending_reading_scores = per_school_summary_df.groupby(["Spending Ranges (Per Student)"]).mean()["Average Reading Score"]

        spending_passing_math = per_school_summary_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Passing Math"]

        spending_passing_reading = per_school_summary_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Passing Reading"]

        spending_overall_passing = per_school_summary_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Overall Passing"]

        ```    
    * #### _Scores by school size increase the overall values with no major changes after rounded values_
      code reference of bins and group definition
      ```Python script 
       # Establish the bins.
        size_bins = [0, 1000, 2000, 5000]
        group_names = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]

       # Categorize spending based on the bins.
        per_school_summary_df["School Size"] = pd.cut(per_school_summary_df["Total Students"],size_bins, labels = group_names)
        per_school_summary_df

        ```
    * #### _Scores by school type reduce 0.1 in the overall passing results scores _
      Code reference of fomrat
       ```Python script 
       # # Format the DataFrame 
        type_summary_df["Average Math Score"] = type_summary_df["Average Math Score"].map("{:.1f}".format)

        type_summary_df["Average Reading Score"] = type_summary_df["Average Reading Score"].map("{:.1f}".format)

        type_summary_df["% Passing Math"] = type_summary_df["% Passing Math"].map("{:.0f}".format)

        type_summary_df["% Passing Reading"] = type_summary_df["% Passing Reading"].map("{:.0f}".format)

        type_summary_df["% Overall Passing"] = type_summary_df["% Overall Passing"].map("{:.0f}".format)

        type_summary_df

        ```
## Summary
 ### this code represent all the functions during the module as loc(), replace() as the main NaN requiriment replacement from the starter code, my conclusion at the end results looks with no major changes in the values after rounded values process and finally good challenge was to keep the order for every analysis using similar formula to allow me the good comprension of the data cleaning. 
   
   Finally, feel free to take reference into the code by PyPoll.py file located in the repository "School District Analysis"
   #### (https://github.com/JulioAQuintana/School_District_Analysis)

