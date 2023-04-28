## BootCamp_Challenge_4

# Code provided to me in office hours
school_count = school_data_complete["school_name"].nunique()
Under the first [in] of District Summary

district_summary =pd.DataFrame({"Total Schools":[school_count],"Total Students":[student_count],"Total Budget":[total_budget],
                               "Avg Math Score":[average_math_score],"Avg Reading Score":[average_reading_score], 
                               "Passing Math %":[passing_math_percentage],"Passing Reading %":[passing_reading_percentage],
                               "Overall Passing Rate":[overall_passing_rate]})
Located at the end of the District Summary section.

student_count_by_school = school_data_complete.groupby('school_name').size()
student_count_by_school
Second section of School Summary
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.size.html

per_school_budget = school_data_complete.groupby("school_name")["budget"].first()
per_school_capita = student_count_by_school / per_school_budget
per_school_capita
Third section of School Summary
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.first.html

per_school_summary["School Size"] = per_school_summary["School Size"] = pd.cut(per_school_summary["Total Students"], size_bins, labels=labels)
per_school_summary

# Use `pd.cut` to categorize spending based on the bins.
school_spending_df["Spending Ranges (Per Student)"] = school_spending_df["Spending Ranges (Per Student)"] = pd.cut(school_spending_df["Per Student Budget"],
                                                            bins=spending_bins)
Located at the Scores by School Size section. 
https://pandas.pydata.org/docs/reference/api/pandas.cut.html
https://www.geeksforgeeks.org/pandas-cut-method-in-python/
