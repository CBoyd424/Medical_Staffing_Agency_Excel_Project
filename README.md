# Medical Staffing Agency Data Analysis Project

![](https://user-images.githubusercontent.com/101165108/157816449-da34ef29-2df1-4a61-b077-28f8f61e2c3e.jpeg)

## **Overview and Purpose**

To help a medical staffing agency that provides temporary workers to clinics and hospitals on an as-needed basis. The analysis will help plan for influenza season, a time when additional staff are in high demand. The final results will examine trends in influenza and how they can be used to proactively plan for staffing needs across the country.

## **Context**

The United States has an influenza season where more people than usual suffer from the flu. Some people, particularly those in vulnerable populations, develop serious
complications and end up in the hospital. Hospitals and clinics need additional staff to adequately treat these extra patients. The medical staffing agency provides this temporary staff.

The agency covers all hospitals in each of the 50 states of the United States, and the project will plan for the upcoming influenza season.

Stakeholders include medical frontline staff, healthcare providers using the staffing agency, influenza patients, and staffing agency administrators.

Download a .csv of the CDC's dataset [here](https://coach-courses-us.s3.amazonaws.com/public/courses/da_program/CDC_Influenza_Deaths_edited.xlsx).
Download a .csv of the US Census Bureau's dataset [here](https://coach-courses-us.s3.amazonaws.com/public/courses/data-immersion/A1-A2_Influenza_Project/Census_Population_transformed_202101.csv).
Download a .csv of the CDC FLUview visits dataset [here](https://images.careerfoundry.com/public/courses/data-immersion/A1-A2_Influenza_Project/CDC_Influenza_Visits.xlsx).
Download a .csv of the CDC FLUview lab tests dataset [here](https://images.careerfoundry.com/public/courses/data-immersion/A1-A2_Influenza_Project/CDC_Lab_Tests.xlsx).

## **Objective**

- Provide information to support a staffing plan, detailing what data can help inform the timing and spatial distribution of medical personnel throughout the United States.

- Prioritize states with large vulnerable populations. Consider categorizing each state as low-, medium-, or high-need based on its vulnerable population count.

- Assess data limitations that may prevent you from conducting your desired analyses.

## **Tools and Skills**

![](https://user-images.githubusercontent.com/101165108/157819527-428966ad-c605-4dea-8381-b370dcf7cf99.png)
### **Microsoft Excel:**   Intermediate to advanced level statistical analyses and visualizations

  - Data Sourcing

  - Data profiling and integrity checks

  - Data cleaning and quality measures

  - Data mapping, transformation, and integretation
    -VLOOKUP
    -Concatonate 
    -Keys

  - Conduct statistical analyses
    - Descriptive statistics
    - Probability distributions
    - Standard deviation and variances
     - Z-scores to measure distance from the mean, as standard deviations
    - Looking for correlations using correlation coefficient (z-scores)

  - Statistical hypothesis testing
    - Z-test where the mean can be compared between population and sample to measure variability
    - p-value and strength of the evidence against the null hypothesis
    - T-test where populaion variance is unknown
    - T-score where needed, using the standard error 

  - DELETE commands using DROP and WHERE

![](https://user-images.githubusercontent.com/101165108/157404857-78432359-3535-46e6-8c46-4bc01e31acde.png) 
### **Tableau:**  Visualization of Results Following Visual Design Standards

  - Spatial analysis using point maps, heat maps, choropleth maps, graduated symbol maps, and combination maps

  - Textual analysis using word clouds and packed bubble charts

  - Scatterplots and bubble charts

  - Statistical visualizations such as histograms and boxplots

  - Composition and comparison charts such as treemaps and pie charts

  - Frequencies and distributions

  - Temporal charts such as line charts, bar and column charts, area charts

  - Forecasting using linear extrapolation, averaging, and exponential smoothing

  - Create dashboards and a storyboard for presentation purposes.

## **Project Steps**

First, I uploaded the dataset to PostgreSQL and then generated an entity relationship diagram (ERD), which is shown below. I chose PostgreSQL as my tool of choice because we were using Rockbuster&#39;s database, and their questions lent themselves to SQL querying. The questions dealt with subsets of the data, and SQL makes it easy to pull specific portions from datasets. The ERD is necessary for the analysis because it shows how the data tables are connected to one another. We needed an understanding of those relationships to combine the tables while querying the data. There were no difficulties with this stage of the project, as the data was ready to be uploaded into a relational database management system, and PostgreSQL has a built-in ERD generator.

![](https://user-images.githubusercontent.com/101165108/157405817-bbb013d2-b7b5-46de-9d99-a1cfc6e9e2ea.png)

Next, I queried the data to answer business questions. These were the most involved steps of the project, requiring SQL expertise. The goal was to come up with result tables that could be exported for visualization.

The select queries required aggregate functions, multiple joins as well as group by, order by, having, and limit clauses. I also used CTE (common table expressions) and subqueries. Fortunately, I was able to save time by taking advantage of the way many of the questions built on one another. I then was able to copiy previous queries and tweak them to create the common table expressions.

A challenge I faced is that more than nine cities—in the top ten countries by customer count—were tied for second in terms of customer count, and Rockbuster wanted the top ten. Moreover, they were tied at a value of one, so any active city was truly in second place. SQL generated ten results, seemingly arbitrarily. In fact, cities 2-9 changed when using a subquery instead of common table expression. To navigate the &quot;multiple-second-place-cities&quot; dilemma, I included a histogram of customer counts in my final analysis after displaying on a point map the top 10 that SQL generated.

![](https://user-images.githubusercontent.com/101165108/157405893-2674a613-3124-4763-876f-a3fc6be7a468.png)

In hindsight, it would have been better to include all the active cities in the table and the point map. This would have drawn more attention to the &quot;many-way&quot; tie. Additionally had this been a true analysis and not for educational purposes, I would have contacted the data engineer, my direct report, and/or client to see if the data they sent us was incomplete/corrupted. After each successful query, I exported the resulting data to .csv for version control and to be easily read by Microsoft Excel and Tableau.

To see the queries individually, see the SQL query project folder [here](https://github.com/CBoyd424/Rockbuster_SQL_Project/tree/main/Example_Queries).

In Tableau, I made a story board to present my findings to Rockbuster stakeholders. I started with an executive summary, then answer the questions the company posed, and finally displayed some of my own analyses that were discovered. I chose this order to first set the stage and share key results, then show what Rockbuster requested, and finally elucidate with more visualizations of findings.

Although many different charts and graphs were created, only a select few made it to the final presentation. My favorite of the visualizations were the point maps, which were great for geospatial trend spotting. I used size and color to denote the magnitude of the values.

![](https://user-images.githubusercontent.com/101165108/157405477-a41fa121-c26f-4cd0-852b-479f18831ae7.png)

Other additions to the analysis were a scatterplot, which showed the correlation between a country&#39;s customer count and revenue, and a histogram of the customer count by city. A correlation between customers and revenue is often assumed, but we were able to confirm that assumption with the scatterplot; its trendline had a correlation coefficient very close to 1—a near-perfect correlation. The histogram illustrated the lack of customer depth in active cities, as almost every city had just one customer.

There were no setbacks during the storyboard process, as the visualizations were straightforward.

## **Conclusion**

I was able to answer all the questions that Rockbuster asked. The most surprising finding was how many cities had just one customer. If this were not an educational project, I would have reached out to a direct report, data engineer, and/or the client before delivering the final product, to find out whether the lack of customers per city is an error, or not. I did speak with my course mentor about this, mentioning that it may have been a measure to reduce the total amount of data in the dataset. He confirmed this suspicion.

If I were to change anything, I would have included all the active cities in my point map of the top cities by customer count within the top ten countries and explore more questions that came to my mind during this project, that I believed would help Rockbuster enter the online streaming service market and remain competitive.

View my final PowerPoint presentation [here](https://coach-courses-us.s3.amazonaws.com/exercises/1054/44753/2ce7ad8426ccf76531020d2587128f01/Data_Imm_3.10_PPT_Cboyd_PDF.pdf)

