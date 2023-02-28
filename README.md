# Cherry Blossom Peak Bloom Prediction
Predicting the Bloom Date from the Temperature Trajectory

Growing degree days are a popular method for predicting the bloom date of plants such as cherry trees. Typically, researchers predict a plant will bloom when the sum of the daily temperatures exceeds some threshold (see of example, Penn State University). Variations include squaring the temperature or only including temperatures within a predetermined window, such as between 0 and 40 degrees Celsius.

The problem with this approach is that sums may discard valuable information that can help predict plant blooms. For example, two plants might each experience a total of 1000 growing degree days during a month. But the plant that experiences consistent temperatures each day might bloom later than the one that experiences low temperatures first and then drastically temperature later.

My entry addresses this problem by using the temperature trajectory (summarized using linear regression) to predict the boom date. Specifically, I modeled the cumulative daily temperature (75 days after Jan 1, roughly March 16th) using linear regression and then used the regression line as a trajectory to get a predicted cumulative sum at 100 days. This trajectory target was then used to predict the bloom date.

For example, Figure 1 shows my approach for predicting the bloom date of the cherry trees in 
Kyoto for 2023. The x-axis shows the number of days since January 1, 2023, and the y-axis shows the cumulative sum of the daily temperature. The black dots denote the observed temperature, and the blue dots denote the temperature forecast on AccuWeather.com (accessed on February 26, 2023). The red line is the linear regression line, approximating the temperature trajectory. 

 

The slope of the red line is compared to previous records. In this case, previous years with similar slopes had moderately early bloom dates of around the 30th of March. Thus, my approach predicts the Kyoto cherry trees will reach peak bloom around the 30th of March.

When I applied my method to the Washington D.C. data, I found that large slopes corresponded to early bloom dates of around the 21st of March, while small trajectory targets corresponded to late bloom dates of around the 10th of April.

Slopes in the middle were less predictive of bloom dates. To deal with this reduced predicting ability, I considered the change of mean temperatures from January to March and identified 3 distinct groups, and then fit a linear regression model to each group separately. I found the predictiveness of my method increased this way and was consistent across all locations. 

To summarize, my entry aims to solve a problem that arises in using growing degree days by taking into consideration the trajectory of the temperature. My approach keeps the simplicity of traditional analyses using growing degree days, but it can distinguish between plants that experience temperatures at different rates. A more predictive method could be achieved by combining a traditional growing degree day analysis with my trajectory approach. However, this approach would be harder to interpret as we are no longer working with a single number as the threshold.

 
References

Curtis, Zachary & Clark, Brittany. Understanding Growing Degree Days. Penn State University. https://extension.psu.edu/understanding-growing-degree-days. Accessed February 15th, 2023
