# Marathon Times: An Exploratory Analysis
### Samantha Post, Sebastian Bucarion, Yiwen Yin

## Executive Summary
tbd

## Motivation
Our project sought to analyze the progression of marathon race times of elite racers through recent history by observing the development of the world’s most elite marathons – the World Marathon Majors and the Olympic marathon race. We wanted to find out how marathon times have changed through history and what factors may be contributing to these changes. This was a topic of interest for further study because as the world becomes more technologically advanced and complex, running is one of the few things that remains one of the most fundamental and basic activities in our world. This is not to say humans have not found ways to improve upon the sport – through its long history since the first ever organized marathon at the 1896 Athens Olympics to present day worldwide road races, runners have continued to set and break records, pushing the limits of our physical abilities, and continue to strive for groundbreaking race times, with an official sub 2-hour marathon record waiting to be reached. How exactly have marathon times progressed throughout history and what patterns can we deduce to help us understand where marathon times are headed? This is the question that drove us to research this topic. 

## Justification
In the midst of a world experiencing political instability, economic growth, and public health crises, running may seem like a minor subject of little relevance. However, it is a sport that brings the world together, foregoes our differences, and lets the most basic abilities of humans and their perseverance speak for themselves. All around the world from New York to Berlin to London, runners join together for one of the longest and most popular road races. It’s a sport that anyone of all skill levels can start and it is a race that any runner can train for. The democratic nature of running therefore provides relevance of this study to all – how have humans capitalized on our running capabilities and what does the future of running look like? For elite runners, our research can provide a greater clarity of what past marathon time progression means for the future of marathon racing. Even for amateur runners, patterns found in our data can provide a better guideline of how they might expect their marathon times to progress, vary, or differ from others. Can we deduce how factors like gender, age, or even temperature affect each person’s abilities to run? Though our analysis is focused on marathons, we hope our findings will inform runners of all abilities and contribute to an ever-growing knowledge of the sport. 

## Aim
The aim of our project was an exploratory analysis to find factors that can influence race times. We wanted to find trends in the race time data across multiple venues to give us a large amount of data points and a wide array of influential factors. Once we finished the analysis we wanted to see if race times can be determined by factors outside of the runners. Thus, letting us see if specific races or runners will always perform better due to certain factors.

## Data
The data we collected is marathon times spanning multiple decades and covering multiple locations. The data is split into two groups, city-based data and the Olympics data. The Olympics data was collected from olympicgamesmarathon.com/results.php which displays marathon times for every year with all the runners who ran it and their time.  The city-based data was collected from marathonguide.com and bmw-berlin-marathon.com. Marathon Guide provides access to hundreds of marathons across the world every year and for us, it provided four out of the five marathon majors data. The second website is the official site for the Berlin marathon which provided us with all the data for Berlin. Within the city-based data we have the Berlin, London, Boston, Chicago, and NYC marathons. The raw data for the Olympics included the position, the name of the runner, the nationality of the runner, and the finishing time. When collecting the data, we grouped it by year and only kept the top one hundred runners for each year. After cleaning the data, we kept only the position and time of the runner. While the Olympics data was clean and easy to prepare, our city-based data was inconsistent across years and variables. With the city-based data we collected the top one hundred runners and their times for the past twenty-one years. However, each city had certain variables that other cities did not. So, because of this variables are limited to one race each. So, we cannot say for certain that a specific variable is a clear indicator of influencing a marathon. Aside from that, the variables for each city are temperature (Boston), age (Chicago), ethnicity (Berlin), gender (London), and nationality (NYC). So, for the Olympics data we have twenty-six years worth of time series data. For the city data we have twenty years of time series data and a specific categorical variable for each race. This leaves us with about 2600 data points for the Olympics data and 2000 data points for each city. For our descriptive statistics shown below, we tracked the standard deviation, average, slowest, and fastest time for each city. This gave us a high-level overview of the marathons and allowed us to start comparing marathon performances. So, for example we see London has the lowest standard deviation which can indicate that runners have more consistent times at this event compared to others. We then performed more in-depth analysis which is expanded on in the Analysis section.
![pivot table appendix](https://github.com/yiwenyin/assets/blob/main/ds5.png)


## Methodology
The first step of analyzing the data was to import the data. Our team used Python and Excel for collecting the data. 

For the city-based data, we used online databases to collect and download the data. We then converted the data into Excel files., so we only needed to download it. The Olympics data was displayed on a website, so we used a Python web scraper to collect the data and input the relevant fields into Excel. 

Once all the data was in the correct place we were able to analyze the data in different ways. As mentioned before, we had categorical and time series data. So, we used different methods of analysis for each. For the time series analysis, we first plotted each dataset to visualize how marathon times have changed throughout our chosen decades. We then used a library in R to help create time series models and forecast future results of the marathon times over the next few decades. We were additionally able to use our forecasting model to find turning points in our data and create trend estimates, bounded by confidence intervals. With our categorical data we used different statistical measures to compare the city-based races. We used Excel for analyzing the city-based race times because we could easily find metrics like averages and apply that to all the datasets. Then using similar statistics, we could compare how averages change year over year or city by city. This allowed us to compare different races to see what factors could influence the race. To analyze our chosen covariates for each city, we used a combination of Excel and R to visualize the relationships these covariates had with race times and to determine the statistical significance of the relationship, when applicable.


## Results
Upon synthesis of all our data, we were able to draw the average fastest marathon finishing times in each year of the Olympics and then in each year of the World Marathon Majors, later extrapolating said findings per city for additional analysis. 

![Olympics finishing times](https://github.com/yiwenyin/assets/blob/main/ds1.png)
![WMM finishing times](https://github.com/yiwenyin/assets/blob/main/ds2.png)

To further understand these yearly average race times and identify/dismiss possible patterns, we can look at a linear model with the data from both the Olympics and World Major Marathons for comparison.

![combined marathon times graph](https://github.com/yiwenyin/assets/blob/main/Screen%20Shot%202022-01-13%20at%207.36.27%20PM.png)

It is important to note that the World Marathon Majors data plotted above only starts in 2001 and doesn’t date back to 1908 as does our Olympic data due to accessibility limitations. To optimize the digestibility of the above chart for enhanced comparison, we chose to keep the scales consistent across the two variables, thus explaining the size of the World Marathon Major. Amplified versions of the two data groups will be analyzed in further detail below. By means of this graph, however, we are able to definitively say that race finishing times have substantially decreased at a rather steady rate from 1908 until around 1976, after which the finishing times started to plateau. Due to the limitations of our data accessibility, our Majors data only starting in 2001, and the Olympics occurring only once every four years opposed to the majors that occur yearly we are unable to draw any concrete conclusions as the two groups of data relate to each other and pertain to changes over time. In the years that the two groups of data do overlap, however, we can conclude that the average race finishing times at the World Marathon Majors are consistently faster than those at the Olympics, as per the linear model.

Looking closer at the Olympic data on an individual level, as per the trend and progression model below, we can see that the averaged finishing times appear to be following a similar trend to that of the fastest finishing times.

![olympic times plot](https://github.com/yiwenyin/assets/blob/main/ds15.png)

It is important to note that for optimized digestibility of this line graph, we imputed missing years of data using averages of other years. 

To better understand the trend said data follows, we can use outlier analysis for stationary time series analysis to identify large jumps and advancements in marathon times.

![outlier analysis](https://github.com/yiwenyin/assets/blob/main/ds14.png)

This turning points graph further highlights the substantial jumps in our data around 1950 and 1960, with time improvement trends appearing flatline onwards from 1960. 

To analyze this nonstationarity, we employed a time series model, using an AutoRegressive Integrated Moving Average (ARIMA) model, as plotted below.

![full arima model no forecast](https://github.com/yiwenyin/assets/blob/main/ds13.png)

Our output (referenced below) prompted an ARIMA of (0,1,1) which further solidifies our conclusion that there is in fact a pattern over time amongst our Olympic Marathon data. 

![arima output](https://github.com/yiwenyin/assets/blob/main/ds23.png)

When conducting the same process for our World Marathon Major data, however, we were prompted with an output, shown below, that showed an ARIMA of (0,1,0), meaning that there was no conclusive pattern in this data over time. 

![inconclusive arima output](https://github.com/yiwenyin/assets/blob/main/ds22.png)

Below is said inconclusivity plotted for further clarity on the meaning of our output.

![unsuccessful arima city](https://github.com/yiwenyin/assets/blob/main/ds11.png)

Because the blue line (our original data) mirrors the black line (the time series model) exactly, just in a delayed fashion, we can see that the model is unable to derive any time series patterns or trends.

Thus, it is only our Olympic marathon data and not our World Marathon Majors data for which we were able to create a graph of turning points and subsequently a forecast model. 

The forecast we conducted via said ARIMA model projects marathon finishing time progressions over the next 40 years, bounded by 80% and 95% confidence intervals, shown below. Our calculated ARIMA model uses a moving average component of time series analysis, and creates a smoothed out trend of our Olympic times data. While the time series model follows our raw data quite closely, it avoids extremes and therefore extracts the trend of Olympic marathon time progression, which shows a clear downward movement. This trend is extended into the future of race times, given by the forecasted progression.

![full model arima forecast](https://github.com/yiwenyin/assets/blob/main/ds12.png)

We subsequently compared our full ARIMA model against a training set model to measure the accuracy of both our model and our forecast, as per the graph below.

![time series train model](https://github.com/yiwenyin/assets/blob/main/ds10.png)

Because the two models produce similar coefficient values, we can appropriately use the training model as a proxy for the full model’s accuracy. 

Additionally, both our true data and full model fall within the 80% confidence interval for our training model’s forecast, and thus we can conclude two measures of accuracy for our models. Firstly, with our true data falling in our confidence bounded forecast, we can conclude that we have created a realistic model that captures the true trend in marathon time progression, given by the raw data that was not used in the training model for use as our holdout data. Secondly, as the forecast includes our full time series model and fits our point forecast of the training model very closely, we can conclude that our full model does not overfit our data and does in fact create a realistic representation of the time series trend of the full data. This allows us greater confidence in using our full time series model to analyze trend progression. In this case, we choose to use our full time series model, given its proven accuracy following the above discussed comparison to the training model, since it captures the trends of most recent marathon times and therefore provides a more accurate representation of the data. 

For the full model point and intervals table of these forecasted values, along with the training model point and intervals table, see below for the full and training forecast values, respectively.

_Full Model Forecast Values_
![full model values](https://github.com/yiwenyin/assets/blob/main/ds21.png)

_Training Model Forecast Values_
![test forecastt values](https://github.com/yiwenyin/assets/blob/main/ds20.png)

_Note: the training model is far more optimistic in predicting faster times. Why? The model is not able to extract trends from more recent years, which as we saw earlier, show a flatter trend. This allows us greater confidence in our full ARIMA model._

Unfortunately, we were unable to draw a conclusive output for the World Marathon Majors. This may be due to the fact that the city races vary within too small a range of time, within about 500 seconds. However, we are ultimately unsure of the reasons behind why our ARIMA model was unsuccessful and would require further exploration of the data and greater training in understanding the mechanics behind time series models.  

Despite our inability to create a time series model to capture the World Marathon Majors trends, our city-level data still offers contextualization for our Olympic data and model, shown below. Due to the annual nature of the World Marathon Majors, our city-level data is able to provide us with reasonable variation of race times for elite runners. We can overlay our Olympic models and forecast with the World Marathon Majors to provide a better understanding of how our forecast may fit into other marathon race times data. We can see that the forecast closely represents where both our Olympic and World Marathon Majors races may be headed. We can additionally use this forecast to predict the first official marathon finishing time of under two hours.

![city with olympic forecast](https://github.com/yiwenyin/assets/blob/main/ds9.png)

Looking closer at our World Marathon Majors data and the respective cities for which we were able to gather data, we can identify various city-level conclusions.

![world map times](https://github.com/yiwenyin/assets/blob/main/ds8.png)

Overlaying the linear progression models of each city, as seen below, we get an even better look at this. Interesting points of note include the Berlin Marathon having runners be consistently the fastest finishers relative to the other four cities, whereas we can also conclude that Boston Marathon runners vary the most in their finishing times. In any comparative model as so, especially when looking at as many data points as we did, it is important that we understand the possibility of outliers and the ultimate distribution of each Marathon city’s race time data. 

![city plot](https://github.com/yiwenyin/assets/blob/main/ds7.png)

The boxplot chart below provides a friendlier visualization of how our city race times vary, as explained above. It is simpler to see here that Berlin runners are consistently running the fastest times, while Boston has the greatest range and variation of race times.

![boxplots](https://github.com/yiwenyin/assets/blob/main/ds6.png)

As mentioned in earlier sections, on a city-specific level, we attempted to find explanatory covariates to further our understanding of why the data is how it is.





## Conclusion
tbd

## Appendix

[Code appendix](https://github.com/yiwenyin/assets/blob/main/DS105%20code%20appendix.pdf) 

## Image repository

![test screenshot](https://github.com/yiwenyin/assets/blob/main/Screen%20Shot%202022-01-13%20at%202.32.16%20PM.png)


![boxplots](https://github.com/yiwenyin/assets/blob/main/ds6.png)
![chicago](https://github.com/yiwenyin/assets/blob/main/ds16.png)
![London](https://github.com/yiwenyin/assets/blob/main/ds17.png)
![NYC](https://github.com/yiwenyin/assets/blob/main/ds18.png)
![Boston](https://github.com/yiwenyin/assets/blob/main/ds19.png)
![berlin](https://github.com/yiwenyin/assets/blob/main/ds24.png)


### END OF CONTENT -------------------
## Reference for GitHub code formatting below

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/yiwenyin/Marathon-Project/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/yiwenyin/Marathon-Project/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
