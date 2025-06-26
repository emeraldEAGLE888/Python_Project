# Analysis
## What are the most demanded skills for popular data roles?
An investigation was conducted into the most demanded skills for certain popular data roles: Data Analyst, Data Scientist, Data Engineer, and Business Analyst. First, the top 5 skills for each of these roles were determined. Then, they were visualized based on their frequency to highlight which skills should be targeted by candidates applying for these roles.

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

## How did the top skills for Data Analysts trend over 2023?
Next, skills for Data Analysts specifically were analyzed. First, the total postings for each different skill were determined and the top 6 skills were obtained. Next, the percent likelihood of those skills appearing was calculated. Finally, the top 6 Data Analyst skills were graphed based on month to demonstrate how their demand fluctuated in 2023.

View my notebook with all steps here: 
[Skills_Trend.ipynb](Final_Project/Skills_Trend.ipynb)

### Generating Visualization
```python
fig, ax = plt.subplots()
sns.lineplot(data=my_df_percent.iloc[:,:6])
for i, skill in enumerate(my_df_percent.columns[0:7]):
    ax.plot(my_df_percent.index, my_df_percent[skill], label=skill)
    x_pos = 11
    y_pos = my_df_percent[skill].iloc[-1]
    ax.text(x_pos + 0.2, y_pos, skill, fontsize=10, va='center')
```
### Result
![Visualization of Top Skills Trends for Data Analysts](Final_Project\Images\real_skill_trend_chart.png)

### Insights
- Although SQL is by far the most in-demand skill for data analysts, it is also on a downward trend as it decreased about 5% in 2023.
- Excel, the second most likely skill to appear, also experienced a downward trend towards the second half of the year.
- Less common skills like SAS, Power BI and R demonstrated a steady trend throughout the year.