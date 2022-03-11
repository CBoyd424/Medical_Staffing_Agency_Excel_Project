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

- Assess data limitations that may prevent conducting the desired analyses.

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

First, I layed out a design for the project. See it [here](https://github.com/CBoyd424/Medical_Staffing_Agency_Excel_Project/raw/main/Project%20Design.docx). I included my project management plan, questions to guide my analysis, and an initial hypothesis.

Then, I familiarized myself with the datasets and created the [data summary](https://github.com/CBoyd424/Medical_Staffing_Agency_Excel_Project/raw/main/Data%20summary.docx). I decided to focus on the Census data and flu death data to determine the relationship between vulnerable populations and flu severity. Because age was the only vulnerability present in the datasets, I made age a focal point of my analysis.

Once I had a grasp of the data I was working with, I assessed the integrity of the data. Frequency tables and basic statistics informed this process, as I ensured that the data were accurate, consistent, and without corruption. Knowing this, the door was open for more data quality measures.

In addition to the data's integrity, I also evaluated the data's completeness, uniqueness, and timeliness. I decided what to do with missing values, determined the data grain, removed duplicates, and described the rate at which the data was collected. These steps were crucial to the accuracy of the analysis.

With clean datasets, I could integrate the two. First, I had to find common variables to map the datasets. This required data transformations for both sources. My goal was to integrate the datasets on the observations' year and state. However, the flu deaths were reported monthly for each state, and the census was collected annually for each county. I made the necessary aggregations to adjust the data: I found the sum of flu deaths by year and the population sum by state. Next, I reduced two common variables to one by concatenation. Additionally, the population age bins were smaller than the flu death age bins. So combined categories in the population data to match. Finally, I executed a VLOOKUP to integrate the data. I had to perform the data integration to analyze the relationship between the population data and flu deaths. See the final dataset [here](https://github.com/CBoyd424/Medical_Staffing_Agency_Excel_Project/raw/main/Final%20Data%20set_Medical%20staffing.xlsx).

![](https://user-images.githubusercontent.com/101165108/157825250-6a694f53-7acd-41e8-b8e0-c80ece33633f.png)

Once I had a uniform set of data to analyze, I began the visual analysis in Tableau. I made several visualizations before creating a final storyboard. This included composition charts, comparison charts, temporal visualizations with forecasting, histograms, box and whisker plots, scatterplots, bubble charts, and spatial analysis.

![](https://user-images.githubusercontent.com/101165108/157825414-3190cbfa-6edd-4a6f-9469-aa00a5a11d57.png)

Then I looked through my project brief and picked which visualizations best fit the questions that I needed to answer and then built dashboards and a storyboard in Tableau, and recorded a presentation for the stakeholders. 

See the final storybaord on Tableau Public [here](https://public.tableau.com/app/profile/cody.boyd6304/viz/Task2_9_16383387359130/Story1).

## **Conclusion**

I was able share insights from historical data with the staffing agency, making suggestions for their planning of the upcoming flu season.

The most challenging aspect of the project was transforming the data sets to prepare them for integration. It took great care to make sure the data sets were compatible with one another. Some of the steps were tedious, while others required clever methods to grow closer to uniformity. I had fun working through this stage of the process, and I was happy with the final dataset.

To improve upon this analysis, I would have included the vaccination dataset in my analysis. The assignment task asked that we choose two of the four datasets. Vaccination is significant variable in the fight against influenza, so it would be necessary to include in a more robust analysis. Also, the fourth dataset was very incomplete, but I think it would be important to look at the influenza sick cases in hospitals as well, and not just flu deaths. 

If I were to be working for this company in real life, I would be sure to speak with my direct report, the data engineering team, and the clients to make sure I have all the data I need for a proper analysis, and to get the complete data sets with no missing and nulled out values. 

See the final audio visual presentation for Stakeholders on Youtube [here](https://youtu.be/5daKwLwzHaM).
