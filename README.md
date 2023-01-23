# House-pricing-on-recession-times
Final project of the Coursera course ¨Introduction to data science in Python¨. More info and details in my website portfolio:
https://joseanmarsol.com/portfolio/house-pricing-on-recession-times/

## Intro and scope
The real estate market is a volatile one, specially if we compare it to house renting or the aggregate income. 
Particularly impactful are the periods of recession and economical growth, of course. 
Besides, there are many other factors which affect the housing value, such as the offer and demand, the location of the property, public services in the area, etc. 
The project is the final assignment of the Coursera course ¨Introduction to data science in Python¨. In this project the analysis is focused on one of the aspects. 
Specifically it will base on if the town where the house is located is an university town or not. 
Therefore, the following hypothesis is presented to us: university towns have their mean housing prices less effected by recessions. 
The main task is to run a t-test to compare the ratio of the mean price of houses in university towns the quarter before the recession starts compared to the recession bottom.

## Data collection
Cousera directly provides the dataset, so it was not necessary to retrieve the data from anywhere. The dataset consists of the following files:

- From the Zillow research data site there is housing data for the United States. In particular the datafile for all homes at a city level, City_Zhvi_AllHomes.txt, has 
median home sale prices at a fine grained level.
- From the Wikipedia page on college towns is a list of university towns in the United States which has been copy and pasted into the file university_towns.txt.
- From Bureau of Economic Analysis, US Department of Commerce, the GDP over time of the United States in current dollars (use the chained value in 2009 dollars), 
in quarterly intervals, in the file gdplev.xls. For this assignment, only look at GDP data from the first quarter of 2000 onward.

## Data reading, cleaning and exploration
We define functions to get:
- List of University towns
- Quarters for recession´s start, end and bottom
- Convert housing data to quarters

## Hypothesis testing
In this final step we are asked to create new data showing the decline or growth of housing prices between the recession start and the recession bottom. 
Then we have to run a t-test comparing the university town values to the non-university towns values, and we have to return whether the alternative 
hypothesis (that the two groups are the same) is true or not as well as the p-value of the confidence.

As a result the function we create has to return the tuple (different, p, better) where different=True if the t-test is True at a p<0.01 (we reject the null hypothesis), 
or different=False if otherwise (we cannot reject the null hypothesis). The variable p should be equal to the exact p value returned from scipy.stats.ttest_ind(). 
The value for better should be either “university town” or “non-university town” depending on which has a lower mean price ratio (which is equivilent to 
a reduced market loss).
