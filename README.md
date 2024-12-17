
# Life Expectancy Analysis Report using python script

## Obejective:
- Life expectancy is influenced by a variety of factors, including population, disease prevalence, GDP, and income levels. Here's a brief overview of how each of these factors can impact life expectancy

## Dataset:
- <a href="https://github.com/jagrutibhagwat29/Life-Expectancy-Analysis-using-Python/blob/main/Life%20Expectancy%20Data.csv">Dataset</a>

## How to call data in to python script:
- Import pandas as pd
- Dataset=pd.read_csv(“dataset location in your system/Life Expectancy Data.csv”
  
## Process:
-	Data Sourcing followed by data cleansing and then data manipulation in query editor.
-	Data transformation for visualisation as follows
  
-	![life expectancy image](https://github.com/user-attachments/assets/d5b18f36-4e4f-4057-bc2a-2d2207e20df8)
  
- ![python image](https://github.com/user-attachments/assets/b4320805-ddc1-4ad1-adc2-0c9a8714cfce)

- Find the outliers using the boxplot method for mileage based on the cylinder type and select Python script visual from visuals. Select : “Life Expectancy”,”Adult Mortality”,”under-five-death columns, then write the below code and click on Run.
- import matplotlib.pyplot as plt
  plt.figure(figsize=(20, 20))
  dataset.plot(kind = "box", layout = (2,2))
  plt.show()

- For 2nd visual create a scatter plot for top 10 GDP against their population. Create a new page and select Python script visual from 
  visuals. Select GDP, and Population column, then write the below code and click on Run. 
  - import matplotlib.pyplot as plt
    plt.figure(figsize=(20, 20))
    topGDP = dataset['GDP'].nlargest(n=10)
    GDPvalue = dataset.groupby("Population")["GDP"].sum().nlargest(10).index
    plt.scatter(GDPvalue,topGDP,s=600,c='Red')
    plt.yticks(fontsize=30)
    plt.xticks(fontsize=30)
    plt.show()
  
-	For 3rd visual print bar plot for average life expectancy for each country for which select Python script visual from visuals, select “country”, “GDP”, ”Life Expetancy” columns, then write the below code and finally click on Run (triangle button on the corner of the script view). 
- import matplotlib.pyplot as plt 
  plt.rc('xtick', labelsize=20) 
  data = dataset.groupby(["Country"])["Life expectancy "].mean() 
  plt.figure(figsize=(15, 40)) 
  cols = dataset["Country"].unique() # creating the bar plot 
  plt.barh(cols,data, color ='maroon',height = 0.6,align='center') 
  plt.show()

-	For 4th visual create a correlation plot for all numeric fields and select Python script visual from visuals. Select the asked columns, then write the below code and click on Run. 
- import seaborn as sns
 import matplotlib.pyplot as plt
 hm = sns.heatmap(dataset.corr(),annot = True)
 plt.show()




## Insights/Conclusion:

- At 9832, 2000 had the highest Under-five deaths and was 69.96% higher than 2015, which had the lowest Under-five deaths at 5785.  
- Under-five deaths and total Infant deaths are positively correlated with each other.  2000 accounted for 7.96% of Under-five deaths .
-  Across all 16 Year, Under-five deaths ranged from 5785 to 9832, Infant deaths ranged from 4356 to 6870, and Adult Mortality ranged from 27210 to 34086.  
- Percentage expenditure and Income composition of resources diverged the most when the Year was 2008, when Percentage expenditure were 2,00,420.18 higher than Income composition of resources.

