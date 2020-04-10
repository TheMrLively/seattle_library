# Love in the Time of Covid-19

First things first, I have an admission, I love the Seattle Public Library. 

On Thursday, March 12, it was announced that the Seattle Public Library would be closing the next day, Friday, March 13, due to COVID-19 for the foreseeable future.   Then, it was announced that Seattle Public Schools would be closed through April 27th.  

WOW, things just got real really fast.  No school for the kids and no library.  We rely on the library and visit 2-3 times per week as a family.   We needed to get to the library fast.  The thought of not enough books and audiobooks to entertain the kids for the 6 weeks was panic inducing.   The scene at the Douglass Truth library was just like a Costco toilet paper aisle.  There were lines 5-6 people deep at the self-checkout, large parts of shelves in the children’s section were empty, social distancing had gone awry.   This was hoarding Seattle style.   How would we survive an extended library closure?  But wait? A light in the darkness.  The Seattle Public Library allows cardholders to check materials digitally!  
 
**Would the library see a huge uptick in the amount of materials checkout digitally?**  

Fortunately, I would not have to wonder in vain.  Every month the Seattle Public Library uploads monthly checkout information to the [Seattle Open Data Portal](https://data.seattle.gov/Community/Checkouts-by-Title/tmmm-ytt6).  The portal provides a straightforward API run by Socrata as well as starter code to run the API in python.  

A project was born and taking a skeptical stance, I devised a null hypothesis.

**There is no difference in the amount of checkouts between March 2020 and other months.** 

My initial thought was to look at the amount of digital checkouts over the past 5-10 years and find the mean and then see if the March 2020 amount was significantly different.  I chose an alpha of .05 as the p-value needed to reject the null hypothesis.   

## Change of Course
First of all, I needed to get a better sense of what a digital checkout was.  From taking a quick look at some sample data, I determined that digital checkouts were divided into 4 main categories. 
- Overdrive - ebook and audiobook service
- Freegal - music streaming and download service
- Hoopla - video streaming service
- Zinio - online magazine service

I was excited.  Ideas abounded.  Could the library meet my streaming needs?  Should I cancel my Netflix?  So many areas to go, but wait...checkouts data on  Freegal, Hoopla, and Zinio were only documented in this data set between 2016-2018.  I would have to focus on [OverDrive](https://www.spl.org/books-and-media/books-and-ebooks/overdrive).  

## Change of Course 2
I looked at some data from every March since 2006 thinking that would provide an apples to apples comparison, and  this set provided some insights but I thought I would look at the more recent data to get a better flavor of what has been happening more recently.   I landed on the digital checkout data from every month since January 2016.  This provided me with 50 months to review and test the March 2020 checkouts against.    


![Plot 1](https://github.com/TheMrLively/seattle_library/blob/master/images/monthly_ckouts.png)

In looking at the data, and plotting it over time, I could see that the mean checkouts would not be a good figure to use as a test statistic.   Of course, Seattleites have been gradually increasing our level of digital checkouts as devices, wifi, applications get better.  This would mean that the rate of change would probably make a lot more sense to look at.  I would need to change my null hypothesis. 

![Plot 2](https://github.com/TheMrLively/seattle_library/blob/master/images/monthly_ckouts_rates.png)

A New Null Hypothesis:   

**There is no difference in the rate of change of digital checkouts between March 2020 and other months.**


These two plots demonstrated that the amount of checkouts has been rising at a fairly consistent rate since 2016 also that there are some predictable times of the year when the checkouts rise and fall.   For example, the rate seems to drop every year in February which makes sense becuase February tends to has 2-3 fewer days per months than other months and even more during a leap year.  

I wondered how these rates are distributed.  So I looked at jitter plot of the rates of change.   The most of the rates appeared to fall between -.025 to .075 with outliers on either end and appeared to approximate a normal distribution. 

![Plot 3](https://github.com/TheMrLively/seattle_library/blob/master/images/ckouts_rates_jitter.png)


Before moving forward, I took another look and plotted the rates into a histogram and to see how it fell under a normal distribution with our mean and standard deviation.  

#### Mean Rate of Change in Checkouts = .015
#### Standard Deviation of Rate of Change = .053
#### Rate of Change in March 2020 = .067

![Plot 4](https://github.com/TheMrLively/seattle_library/blob/master/images/ckouts_rates_hist.png)

The histogram under the normal distribution plot seems to fit so I moved forward with normal distribution to test the null hypothesis.  


![Plot 5](https://github.com/TheMrLively/seattle_library/blob/master/images/monthly_ckouts_pval.png) 

Because the p-value of the March 2020 rate of change is .165, we failed to reject the null hypothesis.  There is not a significant difference in the rate of change in March.   



## Primary Conclusions
March did not have a significant increase in the rate of change in March 2020.  As the library is closed for longer, it is possible the rate of change will grow.  As evidenced by my experience in the Douglass Truth library, people checked out a lot of books on March 13th, and may just be starting to need new materials to read.  I know that I have not personally switched to checking books out online from the library yet, but I can imagine a time when I will. 

The continued rate of growth for online checkouts speaks to the success of the Seattle Public library to continue to build the capacity to allow this rate of ongoing growth.   I know that even in 100 Years of Solitude, the Seattle Public Library has my back.  

## Further Explorations

- March 2020 was the first month that Digital OverDrive checkouts exceed Physical checkouts. This took place because library locations were only open for the first 13 days of the month.   

### Future Questions?
- What does the streaming look like Freegal, Zinio, Hoopla? - Could welook at 2017-2018 and try to project growth to today to get a truer sense of the online digital checkouts.  

  
