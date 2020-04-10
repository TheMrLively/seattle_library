# Love in the Time of Covid-19

First things first, I have an admission, I love the Seattle Public Library. 

On Thursday, March 12, it was announced that the Seattle Public Library would be closing the next day, Friday, March 13, due to COV-19 for the foreseeable future.   Then, it was announced that Seattle Public Schools would be closed through April 27th.  
OK, things just got real.  No school and no library.  We rely on the library and visit 2-3 times per week as a family.   We needed to get to the library fast.  The thought of not enough books and audiobooks to entertain the kids for the 6 weeks was panic inducing.   The scene at the Douglass Truth library was just like a Costco toilet paper aisle.   There were lines 5-6 people deep at the self-checkout, large parts of shelves in the children’s section were empty, social distancing had gone awry.   This was hoarding Seattle style.   How would we survive an extended library closure?  But wait? A light in the darkness.  The Seattle Public Library allows cardholders to check materials digitally!  
Using Seattle Public Library data from the 
 
**Would the library see a huge uptick in the amount of materials checkout digitally?**  

Fortunately, I would not have to wonder in vain.  Every month the Seattle Public Library uploads monthly checkout information to the [Seattle Open Data Portal](https://data.seattle.gov/Community/Checkouts-by-Title/tmmm-ytt6).  The portal provides a straightforward API run by Socrata as well as starter code to run the API in python.  

A project was born and taking a skeptical stance, I devised a null hypothesis.

**There is no difference in the amount of checkouts between March 2020 and other months.** 

My initial thought was to look at the amount of digital checkouts over the past 5-10 years and find the mean and then see if the March 2020 amount was significantly different.  I chose an alpha of .05 as the p-value needed to reject the null hypothesis.   

## Change of Course
First of all, I needed to get a better sense of what digital checkout was.  From taking a quick look at some sample data, I determined that digital checkouts were divided into 4 main categories. 
- Overdrive - ebook and audiobook service
- Freegal - music streaming and download service
- Hoopla - video streaming service
- Zinio - online magazine service

I was excited.  Ideas abounded.  Could the library meet my streaming needs?  Should I cancel my Netflix?  So many areas to go, but wait...checkouts data on  Freegal, Hoopla, and Zinio were only documented in this data set between 2016-2018.  I would have to focus on OverDrive.   

## Change of Course 2
I looked at some data from every March since 2006 thinking that would provide an apples to apples comparison, and  this set provided some insights but I thought I would look at the more recent data to get a better flavor of what has been happening more recently.   I landed on the checkout data from every month since January 2016.  This provided me with 50 months to review and test the March 2020 checkouts against.    


Plot One isert 

In looking at the data, and plotting it over time, I could see that the mean checkouts would not be a good figure to use as a test statistic.   Of course, Seattleites have been gradually increasing our level of digital checkouts as devices, wifi, applications get better.  This would mean that the rate of change would probably make a lot more sense to look at.  I would need to change my null hypothesis. 



Plot two insert


Null Hypothesis Part II:   

**There is no difference in the rate of change of digital checkouts between March 2020 and other months.**


These two plots demonstrated that the amount of checkouts has been rising at a fairly consistent rate since 2016 also that there are some predictable times of the year when the checkouts rise and fall.   For example, what happens in February every year? More on that later.   


I wondered how these rates are distributed.  So I looked at jitter plot of the rates of change.   The most of the rates appeared to fall between -.025 to .075 with outliers on either end and appeared to approximate a normal distribution. 

Plot 3 

Before moving forwardI figured I took another look and plottec the rates into a histogram and to see how it fell under a normal distribution with our sample mean and standard deviation.  

Plot 4

Now we will use a normal distribution with our test statistics to test our hypothesis.  
Include test stats. 


Plot 5 

Because the p-value of the March 2020 rate of change is .165, we fail to reject the null hypothesis.  There is not a significant difference in the rate of change in March.   



## Primary Conclusions
As the library is closed for longer, it is possible the rate of change will grow.  As evidenced by my experience in the Douglass Truth library, people checked out a lot of books on March 13th, and may just be starting to need new materials to read.   Also, the continued rate of growth speaks to the success of the Seattle Public library to continue to build the capacity to allow this rate of ongoing growth.   

## Further Explorations



  
