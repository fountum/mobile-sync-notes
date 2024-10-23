# Basic Concepts
## Population, Sampling Frame, Sample
**Population** is the group of people or things you want to study. 
**Sampling Frame** are the people from the population you can get data on.
  - **Errors of Inclusion and Exclusion**
    - Inclusion: Data *not in* population *in* sampling frame
    - Exclusion: Data *in* populatin *not in* sampling frame
**Sample** is a subset of the sampling frame that you select for you study.  
  - **Sampling Error**: sample is not representative of population due to being smaller than it
    - Increase sample size or make sample proportional to population to reduce

**Non-sampling errors**: human or machine errors.

## Variable, Measurement, Data Set  
```
Data set of sample = {
    Variable = measurement  
    Variable = measurement  
    Variable = measurement  
}
```
**(Random) Variable** is an attribute of the populatoin that can be observed or measured  
    - Age, Hair colour, Weight, Horsepower, Fuel Effciency, Cost, etc.  
**Measurement/Observation** is the value of a variable
**Data set** is a set of measurements for each thing/individual in a sample or population

## Types of Variables
**Qualitative**: Descriptive qualities (labels) of something
  - **Nomial**: observations have no value
    - can't be ranked against each other
  - **Ordinal**: observations have a natural ranking
    - ex. star ratings  
    - Difference from one ordinal observation to next could vastly different things
      - `1 star -> 2 stars` means something different from `4 stars -> 5 stars`
**Quantitative**: Numbers
  - **Interval**: measurement has no "real" 0
    -  Celcius, Farenheit, and Kelvin are all measurements of temperature that have differen't meanings for 0 degrees
    -  Difference between interval measurements are the same regardless of which value you start at
       -  +20 deg C is the same increase at 0 deg and 100 deg
 - **Ratio**: measurement scale has a real zero
   - 0 grams and 0 pounds are the same thing
  
## Sampling Methods
### Random sampling/Probability sampling
Every individual has an **equal chance of being chosen**  
**Simple random sample**
    - pick people randomly until you meet your sample size  
**Systemic sampling**
  - place the things/people of the sampling frame in a sequence
  - randomly choose a starting point
  - increment by a step size and choose the thing/person you land on
    - step size = population size/sample size
- stop when you return to the starting point  
**Stratified sampling**
  - sample is categorized by relevant characteristics
    - ex. gender
  - things/people from sample are chosen randomly but *proportionally to group sizes*
    -  If the groups have a 3:4 ratio, the sample should match the same ratio  
**Cluster sampling**
  - split the sampling frame into random groups of equal size
  - choose groups randomly to fill sample size  
### Non-random sampling
Every individual **does not have and equal chance of being chosen**  
**convience sampling**  
  - picking those who are physically convient to reach out to
    - man on the street interviews  
**purposive sampling**  
  - Choosing people who have expertise or knowledge on the topic  
**snowball sampling**
  - Asking people to reach out to others to build your sampling set
  - pyramid scheme  
**quota sampling**
  - Divide sampling frame into groups based on a characteristic
  - set a 'quota' for how many people/things from each group you need
    - should be proportional to the group sizes
  - use convience sampling to fill the quotas
    - this differs from stratified sampling, where they are chosen *randomly*  

# Graphical Summaries
## Frequency Distributions
For categorical variables and drawing [Histograms](#histograms)  
Measurements are grouped into **classes**, intervals of equal size, or **class width**  
  - **Lower/Higher Class limit**: the lower and upper bound of a class
  - **Class width**: Higher class-lower class  
The amount of times a value in the class occurs in the data set is the **frequency**  
  - **Frequency**: raw count of occurances of a class
  - **Relative frequency**: frequency/sum of all frequencies
  - **Cumulative frequency/relative frequency**: sum of frequency/cumulative of current and previous classes  
Observing frequency distributions  
  - **Modal Class**: class with highest frequency 
    - Remember what *mode* means
  - **Class Mark**: mean of frequencies
  - **Level of Precision**: Minimum increment between measurements of a variable
    - If you're measuring age, your level of precision is years
    - If you're measuring height, your minimum increment can be 16ths of an inch or 1 millimeter
  - **Class Boundaries**: mid point between two adjacent classes
    - take the average of respective lower and higher class limit
    - *No values should have this measurement* 
## Histograms
A visual representation of [frequency distributions](#frequency-distributions). Basically fancy bar graphs for numerical variables.  
  - X-axis/Labels are replaced with **values, not classes!**
  - 1 bar represents a class
    -  Vertical borders are the **class boundaries**
    -  Width spans is the **class width**, or occupies the interval of the class on the x-axis
  - Instead of spacing out bars, they are adjacent to each other and share borders  
## Percentiles and Quartiles
A **percentile** is a point/value in the data splits it into to halves.  
  - The dividing point/value is known as the *kth percentile*. (P~k~)
    - sort values in ascending order
    - i (index) = k (as decimal)*number of values
    - if whole
      - find that index in the values
      - kth percentile = average of ith value and the i+1th value
    - if not whole
      - round index
      - that term is equal to P~k~
  - The *lower k%* has values *less than* the kth percentile 
  - The *upper `100-k`%* has values *more than* the kth percentile  
  
A **quartile** are percentiles in 25% increments. Used for **box plots**   
  - (0%, 25%, 50%, 75%, 100%) = (Q~0~, Q~1~, Q~2~, Q~3~, Q~4~)
    - Q~2~ is equal to the median of data set
  - **Range** = max (Q~4~) - min (Q~0~)
  - **interquartile range (IQR)**: Q~3~ - Q~1~   

The **five-number summary** for a set of data consists of:    
  - max (Q~4~) & min (Q~0~)
  - Q~1~, Q~2~, Q~3~  

### Outliers  
Extreme values of a dataset. Only to be deleted if the measurement is correct. Values outside of this range is considered extremely small or large:  
  - Upper limit = Q~3~ + 1.5(IQR)
  - Lower limit = Q~1~ - 1.5(IQR)  

## Categorical Graphs  
**Bar Chart**  
  - Labels vs. Occurance Count
**Pie Charts**  
  - Bar chart alternative


