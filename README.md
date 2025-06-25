# Analysis
## What are the most demanded skills for popular data roles?
Next, an investigation was conducted into the most demanded skills for certain popular data roles: Data Analyst, Data Scientist, Data Engineer, and Business Analyst. First, the top 5 skills for each of these roles were determined. Then, they were visualized based on their frequency to highlight which skills should be targeted by candidates applying for these roles.

View my notebook with all steps here: 
[Skills_Count.ipynb](Final_Project/Skills_Count.ipynb)

### Generating Visualization
```python
fig, ax = plt.subplots(len(job_titles), 1,figsize=(6,8))
for i, job_title in enumerate(job_titles):
    df_plot_2 = df_merged[df_merged['job_title_short']==job_title].head(5)
    sns.barplot(data=df_plot_2,x='skill_perc',y='job_skills',ax=ax[i],hue='skill_perc',palette='rocket_r')
plt.show()
```
### Result
![Visualization of Top Skills for Data Jobs](Final_Project/Images/skill_demand_chart.png)

### Insights
- Python is heavily demanded in technical roles like Data Scientist and Data Engineer and drops off in lower-level jobs like Data Analyst and Business Analyst.
- SQL is the most consistent skill as it is the most demanded skill in every job except Data Scientist, where it is second to Python.
- Excel and Tableau, data analysis and management tools, are more common among Data/Business Analysts, whereas more specialized tools like AWS and Azure are reserved for Data Engineers.
