# Coupon Acceptance Analysis

## Overview

This project explores the acceptance of different types of coupons among
drivers with different characteristics and under various conditions. This
analysis can help businesses target their marketing efforts and design
strategies to maximize the acceptance of their coupons, and increase sales.

## Dataset

The dataset contains multiple attributes, including:

### User attributes
* Gender: male, female
* Age: below 21, 21 to 25, 26 to 30, etc.
* Marital Status: single, married partner, unmarried partner, or widowed
* Number of children: 0, 1, or more than 1
* Education: high school, bachelors degree, associates degree, or graduate degree
* Occupation: architecture & engineering, business & financial, etc.
* Annual income: less than $12500, $12500 - $24999, $25000 - $37499, etc.
* Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
* Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
* Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
* Number of times that he/she eats at a restaurant with average expense less than $20 per person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
* Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8

## Contextual attributes
* Driving destination: home, work, or no urgent destination
* Location of user, coupon and destination: we provide a map to show the geographical location of the user, destination, and the venue, and we mark the distance between each two places with time of driving. The user can see whether the venue is in the same direction as the destination.
* Weather: sunny, rainy, or snowy
* Temperature: 30F, 55F, or 80F
* Time: 10AM, 2PM, or 6PM
* Passenger: alone, partner, kid(s), or friend(s)

## Coupon attributes
* Time before it expires: 2 hours or one day


Each entry represents a user's response to a coupon offer, capturing both the offer's context and the user's decision to accept or reject it. The dataset is included in the file `data/coupons.csv`

## Objectives

We will direct our efforts in analyzing and identifying the characteristics and
the contextual factors of individuals of those who are more likely to accept
__Bar__ and __Coffee House__ coupons. We will make use of the Python `Pandas`
library and the `Seaborn` visualization library for these efforts. Our analysis
will be defined and completed in a _Jupyter Notebook_.

## Findings
The core findings were discovered by Pandas code in the following module - `coupon_acceptance.ipynb`. The dataset is included in the file `data/coupons.csv`

The findings are described next.

### Overall - Across all coupon types
* Approximately 56.84% of the total observations, i.e. a little over a half, chose to accept the coupon, across all coupon categories
* The __Coffee House__ coupon type was offered most frequently to the respondents, while __Restaurant(20-50)__ was the least frequently used coupon

### Bar Coupons
* About 42% of the bar coupons were accepted
* Acceptance rate of bar coupons for those who go to a bar 3 or fewer times a month is ~37%
* Acceptance rate for those who go to a bar more than 3 times a month is significantly high at ~77%. This is prime category for targetting the coupon
* Drivers who go to a bar more than once a month and are over the age of 25 have an acceptance rate of ~77%
* Drivers drivers who go to bars more than once a month, and had passengers that were not a kid and had occupations other than farming, fishing, or forestry have a significantly higher rate of acceptance, than other bar goers. Some of it is easy to understand as someone who goes to bars often, and has no obligations of kids would have more opportunity to visit bars, and therefore would be more likely to accept coupons. The correlation with the occupation is a little hard to read though.
* Based on the analysis that we did. We can analyze the effectiveness of drivers accepting bar coupons based on different characteristics.

__Age and Marital Status__: Younger individuals or those listed as single may have a higher likelihood of accepting bar coupons, reflecting a potentially more active social life.

__Passenger Presence__: Drivers who are not alone, especially those with friends, might be more inclined to accept bar coupons. This makes sense because drinking is a social activity in large part and often an occassion for bonding. These circumstances would also imply that you would choose to avail of the coupons to get discounts.

__Frequency of Visiting Bars__: Individuals who already frequent bars are likely to accept more bar coupons. This seems like an obvious conclusion as the more you visit bars, the more you would prefer to avail of discounts.

__Impact of Occupation__: The analysis that required _including_ `Farming Fishing & Forestry` occupation was interesting because it showed a very low acceptance rate. Even though it was coupled with a couple of other criterion (viz. `Passanger` type and `Bar` visit frequency), it suggests that people working in these occupations that are remote are less likely to avail of these discounts. Its perhaps in the nature of these occupations that does not allow people more opportunity to visit bars in the first place, so the prospect of discounts might not be that interesting to them.


### Coffee House Coupons

* That's an acceptance rate of ~50% for the Coffee House coupon. This can be considered a moderately successful coupon type till now. Further data analysis would actually really help in targetting this coupon more narrowly to increase its acceptance type. 
* There seems to be a strong preference among the age group 21 - 31. This could be a good target demographic for more promotions. This age group is younger and would love to spend their discretionary income eating out so that makes sense.
* There is no strong correlation between coupon consumption between women and men. There's no point in gender-based targeted promotions so efforts would be better directed at other characteristics like age group
* Single and Married Partners have a high acceptance count
* The distribution by income presents a really inconclusive picture - there seems to be wide dispersion between income brackets that consume coupons in the same amounts. Its actually surprising to see a high count amount the high income earners! Proving that it would be ok to target all income brackets for this coupon type
* Finally, it seems it would not be very effective to target people either driving to work or driving home from work for these coupons. Since its hard, if not impossible to identify who is headed where, perhaps we can use the time of the day as a proxy for concluding that. We can leave out people driving the morning times of, say 8 - 9 AM, and then evening times of 5 - 6 PM for these coupons as these are likely to be drivers commuting to and from work, respectively.

## Future Work

Some possibilities for more analysis and inferences from the same `coupons.csv` dataset include:

* Examine how contextual factors like weather, temperature and time of day influence coupon acceptance rates. For instance, are coffee house coupons more likely to be accepted on cold, rainy days? 
* Examine the coupon types that we did not cover in this analysis, viz. `Restaurant(<20)`, `Carry out & Takeaway` and `Restaurant(20-50)`
