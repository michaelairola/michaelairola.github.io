---
title: 
tags: data-analysis data COVID-19 death life-expectancy 
chart: true
---

Ever heard of the [Trolley problems](https://en.wikipedia.org/wiki/Trolley_problem)? They are a series of thought experiments involving ethical dillemmas. The most basic version of the problem goes as such:

> ***There is a runaway trolley barrelling down the railway tracks. Ahead on the tracks, there are ten people tied up and unable to move. The trolley is headed straight for them. Conveniently, you are standing some distance off in the train yard, next to a lever. If you pull the lever, the trolley will switch to a different set of tracks, and will avoid the ten people. However, you notice there is one person tied up and unable to move on this side of the tracks. Do you pull the lever?***

Philosophers love this hypothetical scenario. Choosing who lives and dies seems to be a difficult problem for humans to solve; We are not God and we are terrible at playing the part<sup>1</sup>. This problem forces us to compare **qualities of life**, which turns out to be a hard thing for humans to do without going insane.

For the sake of our sanity then, we need a way to assess the quality of a single life. For now, because we have no information on who these people are or what their quality of life is, let's assume that all lives are equal. Given this assumption (and the assumption that 10 is greater than 1), the life-optimal choice would be to pull the lever, right? 

This is a fair way to approach this problem, and barring any other significant information, it would be the best data-driven solution anyone could come up with. 

This begs the question, is there any significant information that could help us qualify life? Well, it would be nice if we could measure expected value from a life. Turns out, there are many actuarial tables online that try to do just that - like this one [here](https://www.ssa.gov/oact/STATS/table4c6.html) that charts expected years of life to gender and age.

So let's factor this into our trolley problem! Let's say that the ten people on the tracks are each 90-years-old, and the one person on the other track is a 2-month-old baby. 

For those of you who love formulas, here's an equation to get you going (if you don't love formulas, you can just ignore this. All it does is add up all expected years of life for a group of people). If $$f(a)$$ is the number of people as a function of age, and $$E(a)$$ is life expectancy as a function of age, we can determine the total life-years of a group of people by evaluating

$$\sum_{a=0}^{Max Age} f(a) * E(a) $$ 

Using this formula, and the average of male and female life expectancies given from [this](https://www.ssa.gov/oact/STATS/table4c6.html) chart, we can solve for the second trolley problem! Since $$f(90) = 10$$ and $$E(90) = 4.415$$, expected life-years for the group of ten would be $$4.415 * 10 = 44.15$$ life-years. On the other side of the tracks, $$E(0) = 78.465$$ life-years. In other words, the group of ten is worth around 44 years of life, whereas the baby is worth about 78. 

Now obviously, framing quality of life as a function of life-years isn't a perfect measurement<sup>2</sup>. This is simply the continuation of ideas expressed earlier; Instead of assuming every **life** lived is equivalent, we are now assuming that every **year** lived is equivalent. Ethically, it's hard to decide to kill 10 old people to save a baby, but logistically this decision has pretty good standing. 

This thought experiment got me thinking about COVID-19's death count. Although there are plenty of dashboards and metric counts online about COVID-19, I couldn't find any that measured life-years as a function of age. So I decided to do a little snooping around, and found some good insights in the [CDC's Public Use dataset](https://data.cdc.gov/Case-Surveillance/COVID-19-Case-Surveillance-Public-Use-Data/vbim-akqf). If you haven't checked out the CDC's resources on this subject, I would suggest you follow the link. Very neat interface for creating your own queries and data filters<sup>3</sup>.

Here is a chart plotting age groups as a relationship to Covid-19 deaths.
```chart
{
  "type": "bar",
  "data": {
    "labels": ["0-9", "10-19", "20-29", "30-39", "40-49", "50-59", "60-69", "70-79", "80+"],
    "datasets": [
      { 
        "label": "Death Count",
        "data": [ 71, 134, 847, 2259, 5384, 13942, 29887, 45325, 85182 ],
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Covid Deaths by Age Group, U.S."
    }
  }
}
```
As you can see, this disease is disproportionally killing off the elderly. It makes sense why young people tend to be less covid-concious. 

However, this is slightly confusing to me when I think about the people I know under the age of 80 that are terrified of COVID-19. What is also confusing is how little my 90-year-old grandma cares about COVID-19 precautions and shelter in place ordinances<sup>4</sup>.  

Lets take a look at the relationship between age groups and life-years lost...
```chart
{
  "type": "bar",
  "data": {
    "labels": ["0-9", "10-19", "20-29", "30-39", "40-49", "50-59", "60-69", "70-79", "80+"],
    "datasets": [
      { 
        "label": "Life Years Lost",
        "data": [ 8209, 13451, 75822.9, 169952.1, 322639.2, 623627, 920959.2, 841076.5, 752032.5 ] ,
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Life-Years lost from COVID-19 by Age Group, U.S."
    }
  }
}
```
Wow, this makes a little more sense! Elderly populations are still losing a considerable amount of years of life, however it appears that the largest loss of life-years is occurring to people in the age range of 60-69 years olds. That is smack-dab in the middle of the Baby Boom era! No wonder politicians are pandering so extremely for safety precautions from COVID-19, a large portion of their demographic is losing more life-years than any other group.

Are there any other ways to categorize the impact COVID-19 has had on our Society? Im glad you asked! One way is to compare the total deaths in 2020 to previous year death counts. This metric is called ***excess deaths***.

A recent [CDC study](https://www.cdc.gov/mmwr/volumes/69/wr/mm6942e2.htm) found excess deaths in 2020 to be estimated at around 299 thousand. If we subtract the studies claimed COVID-19 death count (213 thousand), we get around 86 thousand excess deaths that were not directly linked to COVID-19.

You read that correctly. ***That's 86,000 excess deaths this year, not directly tied to COVID-19!*** Sure, some of these deaths could be mis-reported COVID-19 cases, but how many? I'd say maybe thousands of mis-reported COVID-19 deaths as an upper bound. ***1 or 2 thousand is nowhere near 86 thousand***. Those numbers aren't even in the same ballpark. 

Excess deaths includes all externalities brought on by 2020. So yes, this includes shelter-in-place ordinances, travel restrictions and essential-only-work orders as a conglomeration of factors that may have contributed to this large number of excess deaths. 

To understand the root causes of the excess deaths, it would be nice to see it's relationship with age. I decided to look into the CDC's [Weekly Deaths By Jurisdiction and age group](https://data.cdc.gov/NCHS/Weekly-counts-of-deaths-by-jurisdiction-and-age-gr/y5bj-9g5w) dataset. In order to find the average death counts by age, I took the average death counts of the past 4 years (2015 - 2019) per age group. This was then subtracted from the death counts by age group in 2020 to get a solid estimate of excess deaths<sup>5</sup>.

Here's what the relationship between age group and excess deaths looks like:
```chart
{
  "type": "bar",
  "data": {
    "labels": [ "0-24", "25-44", "45-64", "65-74", "75-84", "85+" ],
    "datasets": [
      { 
        "label": "Death Count over Average Per Year U.S.",
        "data": [ -2485.6, 59897.4, 112962.6, 199670.2, 216060.6, 174333.4 ],
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Predicted Excess Deaths in 2020, U.S."
    }
  }
}
```
This brings up some interesting findings. First thing I notice, is that excess deaths for the 0-24 age group are actually negative! How can this be? I have few guesses:

1. This age group tends to be the most risk-loving group. Since both the public and private sectors of society have been implementing pandemic-halting strategies, there are way less chances to be risky. A [UC Davis study](https://www.ucdavis.edu/news/california-covid-19-traffic-report-finds-silver-lining/) found that fatal car accidents in 2020 have decreased by half, and just by looking at differences in car insurance prices with age groups, we can assume pretty safely that a lot of car accidents occur from these risk-loving teenagers. 

2. A large portion of this age group is in some sort of educational system. It may be possible that school environments (i.e. competition from classmates, bullying, etc.) contribute to far more suicides per year than its zoom-oriented counter part. 

For either of these assumptions, more data needs to be analyzed. Suicide rates and car accident fatality rates for 0-26 year olds would be helpful to look at. It would also be nice to know how affective zoom-learning is at improving the health of our youth, and whether that improved bump is worth the (eleged) lack of knowledge gained.

The most interesting thing I see from this chart though, is the skew towards younger ages compared to the initial COVID-19 death chart. It appears that there are a lot of excess deaths that are not in the same age group as the COVID-19 deaths. 

This fact becomes even more apparent when we look at the relationship between age groups and excessive life-years lost (yes thats right, I created my own metric, excessive life-years lost: the average years of life lost from 2015-2019 subtracted from the total years of life lost in 2020).
```chart
{
  "type": "bar",
  "data": {
    "labels": [ "0-24", "25-44", "45-64", "65-74", "75-84", "85+" ],
    "datasets": [
      { 
        "label": "Life Years over Average Per Year U.S.",
        "data": [ -164298.16, 2675916.345, 3027397.68, 3005036.51, 1847318.13, 889100.34 ],
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Predicted Life-Years Lost excess in 2020, U.S."
    }
  }
}
```
This chart is wild. Why are there so many excess life-years lost for ages 25-64? They have a relatively small share of the life-years lost from COVID-19. 

I really only have one guess for this; Pandemic-halting ordinances have contributed to a stagnating economy and a lack of social outlets for these demographics, increasing total amount of suicides and overdoses. Look [here](https://www.ama-assn.org/system/files/2020-12/issue-brief-increases-in-opioid-related-overdose.pdf), [here](https://www.ehstoday.com/health/media-gallery/21121766/cdc-reports-lower-drug-overdose-rates-while-suicides-climb-photo-gallery), [here](https://www.liebertpub.com/doi/10.1089/POP.2020.0230), and [here](https://www.cdc.gov/coronavirus/2019-ncov/cdcresponse/accomplishments/excess-death-data.html) for some interesting reads.

Regardless of reason, there were still ***86 thousand*** excess deaths this year not directly tied to COVID-19, and most of these deaths skew young. How many life-years were lost because of pandemic-halting ordinances? Was it worth it? It's really hard to tell. But judging by these numbers, It's a lot closer than most people would believe. 

### **superscripts:** ###
1. Many people answer the trolley problem by refusing to pull the lever regardless of the two choices given. In this school of thought, doing nothing keeps your hands clean, whereas pulling the lever kills whomever is on the receiving side of the tracks. To avoid this anti-interventionist loophole, assume that doing nothing is a choice; In other words, your hands are always going to be dirty and our goal is to find the least-dirty solution.
2. What if we knew without a doubt that the baby was going to be a terrible, terrible human being? The quality of that life would be irredemable and should definitely be run over by a trolley, no questions asked. Yes, I am totally advocating for killing baby hitler here. It sounds bad, but this isn't an article about ethics. Let's just agree to avoid this rabbit-hole for the time being.
3. As a small caveat, the CDC uses death certificates for measuring deaths within the U.S. which take at least a few weeks or so to be submitted and verified. Because of this, the datasets are typically a little behind other datasets (As of the 8th of December 2020, the CDC's estimate of total deaths in the U.S. is around 183 thousand, where as something like the New York Times database suggests the amount of deaths to be around 286 thousand). Obviously, the numbers are a little off, however for the purposes of this article the proportions of age-demographic vs. deaths should be the same for all datasets, and I encourage anyone out there willing to do so to replicate these metrics elsewhere.
4. The last time I went to visit my 90-year-old grandma, she said the following: "I only have a couple more years of life; I'd rather not spend it sheltering alone in my home." Good point grandma.
5. The study referenced above calculating excess death used a much fancier method for determining excess death - a Poisson regression model using spline terms to account for seasonal patterns. Admittedly, I come from a Mathematics background, not a statistics background, so I chose to use a more rudimentary formula to calculate excess death, giving slightly different total numbers (I am also not sure if I used the same dataset as the previously discussed study, so there are many differences). However, the skew towards younger ages is still the same, and that's primarily what I wanted to show.
