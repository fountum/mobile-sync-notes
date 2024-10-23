- [Basic Concepts](#basic-concepts)
  - [Population, Sampling Frame, Sample](#population-sampling-frame-sample)
  - [Variable, Measurement, Data Set](#variable-measurement-data-set)
  - [Types of Variables](#types-of-variables)
  - [Sampling Methods](#sampling-methods)
    - [Random sampling/Probability sampling](#random-samplingprobability-sampling)
    - [Non-random sampling](#non-random-sampling)
- [Graphical Summaries](#graphical-summaries)
  - [Frequency Distributions](#frequency-distributions)
  - [Histograms](#histograms)
  - [Percentiles and Quartiles](#percentiles-and-quartiles)
    - [Outliers](#outliers)
  - [Categorical Graphs](#categorical-graphs)
- [Numerical Summaries of Data](#numerical-summaries-of-data)
  - [Measures of averages](#measures-of-averages)
    - [Sensitivity to Extreme Values](#sensitivity-to-extreme-values)
  - [Measures of Spread](#measures-of-spread)
  - [Skewness](#skewness)
    - [Calculating skewness](#calculating-skewness)
- [Probability and Counting](#probability-and-counting)
  - [Concepts](#concepts)
  - [Classical vs Relative Frequency Approach](#classical-vs-relative-frequency-approach)
    - [Classical Approach](#classical-approach)
    - [Relative Approach](#relative-approach)
  - [Counting](#counting)
    - [Fundamental Counting Rule](#fundamental-counting-rule)
    - [The mysterious method](#the-mysterious-method)
    - [Permutations](#permutations)
    - [Combinations](#combinations)
- [Probability Laws and Conditional Proability](#probability-laws-and-conditional-proability)
  - [Probability Laws](#probability-laws)
    - [Complementary Rule](#complementary-rule)
    - [Addition Rule (Union/OR)](#addition-rule-unionor)
    - [Conditional Probability](#conditional-probability)
      - [Independent Events](#independent-events)
    - [Multiplication Rule (Intersection/AND)](#multiplication-rule-intersectionand)
    - [Mutually Exclusive](#mutually-exclusive)
- [Normal Distributions](#normal-distributions)
  - [THE KEY IDEA](#the-key-idea)
  - [Nomrla Distributions](#nomrla-distributions)
  - [Standard Normal Distribution](#standard-normal-distribution)
  - [Non-Standard Normal Distributions](#non-standard-normal-distributions)
  - [Unusual Values in Normal Distributions](#unusual-values-in-normal-distributions)

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
  - **Simple random sample**
    - pick people randomly until you meet your sample size  
  - **Systematic sampling**
    - place the things/people of the sampling frame in a sequence
    - randomly choose a starting point
    - increment by a step size and choose the thing/person you land on
    - step size = population size/sample size
    - stop when you return to the starting point  
  - **Stratified sampling**
    - sample is categorized by relevant characteristics
      - ex. gender
    - things/people from sample are chosen randomly but *proportionally to group sizes*
      -  If the groups have a 3:4 ratio, the sample should match the same ratio  
  - **Cluster sampling**
    - split the sampling frame into random groups of equal size
    - choose groups randomly to fill sample size  
### Non-random sampling
Every individual **does not have and equal chance of being chosen**  
  - **convience sampling**  
    - picking those who are physically convient to reach out to
    - man on the street interviews  
  - **purposive sampling**  
    - Choosing people who have expertise or knowledge on the topic  
  - **snowball sampling**
    - Asking people to reach out to others to build your sampling set
    - pyramid scheme  
  - **quota sampling**
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
  - **Bar Chart**  
    - Labels vs. Occurance Count
  - **Pie Charts**  
    - Bar chart alternative

# Numerical Summaries of Data
## Measures of averages

| Type | Sample Symbol | Population Symbol | what? |
| ---- | ------------- | ----------------- | ----- |
| Mean | x̄             | µ                 | Arithmatic average of X |
| Median | x̃           |                   | Value in center of *sorted data set*. If no value exists in the center, get the mean of the 2 adjacent values.|
| Mode |               |                   | Value that occurs most frequently in data set|

### Sensitivity to Extreme Values
If a data set X contains extreme values, what measure of average is the most stable?  
  - Mean is the most affected by extreme values. An intreme value can cause the mean to fluctuate by many factors.  
    - extremely large values move the mean to the *right of the median*
    - extremely small values move the mean to the *left of the median*
  - Median and mode are more stable  

## Measures of Spread
1. Range
   - Range of all values in data set
   - Max value - min value
   - *sensitive to extreme values*
2. Inter-quartile Range
   - Range of inner 50% of values
   - IQR = Q3 - Q1
3. Standard Deviation
   - Measures the spread of data in intervals
   - s, n - 1 for sample
   - σ, N for population
4. Variance
   - Square of standard deviation
  
## Skewness
Where the data leans towards relative to the median  
| mean and median | skewness | 
| --------------- | -------- |  
| x̄ < x̃ | left |   
| x̄ = x̃ | no skew |  
| x̄ > x̃ | right |   

### Calculating skewness
Sk = 3(mean-median)/standard deviation  
| Sk | skewness | 
| -- | -------- |  
| Sk < -1 | left |   
| 1 > Sk > -1 | no significant skew |  
| Sk > 1 | right |   

# Probability and Counting
## Concepts
   - **Random Experiement**: experiment where outcomes cannot be controlled
   - **Outcome**: one specific result of an random experiement
   - **Sample Space**: all possible outcomes of a random experiement
   - **Event**: subset of sample space, one or more outcomes
     - Event A occured if the outcome of the experiement is A
   - **Probability**: chance event A happens, P(A)

## Classical vs Relative Frequency Approach
Two different ways of calculating the probability of event A (P(A)).

### Classical Approach
A theoretical method. `P(A) = outcomes in event A/total number of outcomes`

### Relative Approach
A practical method. Not equal to the classical approach, but gets closer to it with more trials.  
Perform the experiement for a number of trials and record:  
1. Total number of trials
2. Number of times event A occurs
`P(A) = Number of times event A occurs/Total number of trials`

## Counting
### Fundamental Counting Rule
**Order matters, with replacement**  
If you are picking one item for `n` options, you can multiply each number of options.  

### The mysterious method
**Order doesn't matter, with replacement**  
From `n` items, take `r`,   
$\frac{(r+n-1)!}{r!(n-1)!}$  
One give away is when `r` is larger than `n` (CN)  

### Permutations
**Order matters, no replacement**  
From `n` items, *pick* `r`,  
$nPr = \frac{n!}{(n-r)!}$  

### Combinations
**Order doesn't matter, no replacement**  
From `n` items, *choose* `r`,  
$nCr = \frac{nPr}{r!} = \frac{n!}{r!(n-r)!}$

# Probability Laws and Conditional Proability
## Probability Laws
### Complementary Rule
$P(A) = 1-P(\bar A)$

Best use case for the complementary rule is for "at least one" problems.  
Example:  
$P(At least one pair of students have the same birthday) = 1-P(no students have the same birthday)$

### Addition Rule (Union/OR)
For the probability of event A *or* event B occuring (inclusive):  
$P(A \cup B) = P(A) + P(B) - P(A \cap B)$

### Conditional Probability
The probability that event B happens given that event A has occured:  
$P(B | A) = \frac{P(A \cap B)}{P{A}}$

This implies that the event B is dependant on event A. However, this isn't always the case.  

#### Independent Events
If $P(B | A) = {P{B}}$, then event A and B are independent from each other.

### Multiplication Rule (Intersection/AND)
For the probability of event A *and* event B occuring:  
$P(A \cap B) = P(A) * P(B | A)$

If events A and B are independent:  
$P(A \cap B) = P(A) * {P{B}}$

### Mutually Exclusive
Events A and B are considered to be mutually exclusive if they **cannot happen at the same time**. On a diagram, there would be no overlap between set A and B.
$P(A \cap B) = 0$

# Normal Distributions
## THE KEY IDEA
X <=> Z <=> P  
Use $x=\frac{Z-x\bar}{\sigma}$ to go from `x` and `z`
Use The Table™ to go from `z` and `p`

## Nomrla Distributions
Bell curves.  
Distributions are written as:  
$variable ~ N(x\bar, varience)$

## Standard Normal Distribution
$Z ~ N(0, 1)$  

## Non-Standard Normal Distributions  
$X ~ N(x\bar, varience)$  
Convert to Z using $x=\frac{Z-x\bar}{\sigma}$

## Unusual Values in Normal Distributions
A value is considered unusual if $Z > 2 or Z < -2$


