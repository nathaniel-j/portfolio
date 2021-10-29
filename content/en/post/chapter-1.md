---
date: 
description: "Austin New Housing Supply"
featured_image: ""
tags: ["portfolio project"]
title: "Exploring the effects of Covid on Austin's housing supply"
---

# Exploring the effects of construction delays from Covid on the Austin housing market
_This project was put together from the [Issued Construction](https://data.austintexas.gov/Building-and-Development/Issued-Construction-Permits/3syk-w9eu) Permits dataset assembled and maintained by the City of Austin._

![building](/images/apt%20construction.jpeg)

#### When my current apartment lease was up for renewal this October, the market seemed to have changed dramatically from a year ago when buildings were offering large lease signing incentives in order to fill units. At the same time, I noticed an abundance of new construction going on around the city, so I was curious if the market mechanisms that normally keep housing supply in line with demand had been supressed by building delays from supply shortages and personnel regulations during peak Covid pandemic. Further, I wondered when could we expect the supply to get back on track. 

---

### Question 1: Has new construction been delayed during the Covid pandemic?
---

To visualize the aggregated build times for new housing, I used a simple chart showing the number of housing units applied for each year, compared to the number of housing units that are finalized each year. This chart also allows for annual new housing comparison between years, clearly showing huge booms in 1983, 2008, and right now, with busts bottoming out in 1990 and 2010. 

![first_chart](/images/housing_graph_1.png)

### Question 1 Results: There is a large delay in new construction reaching the market during the Covid pandemic.
---

While it is normal to see a large difference between the issued and completed permits, (especially when demand spikes like in 1983) we expect there to be a spike in completion that follows (like in 1984). However, in 2019, when the issued permitted units spiked to a new city record, the completed units for the next year hardly go up at all. This massive gap between supply and demand also seems to line up directly with the onset of delays related to the Covid pandemic. 

---

### Question 2: When will the new housing supply in Austin catch up with demand?
---

Here is the distribution of expected completion times for projects currently in progress based on a k nearest neighbors model. This model helped avoid extreme completion times that were predicted with scalar regression models and shows what we would expect to have seen without Covid delays.

![second_chart](/images/projection_lengths.png)

This projection line only serves to estimate the completion dates of projects currently under way, and does not serve as an estimate for housing projects that will be completed in 2022 and beyond. To estimate construction for those years would involve making predictions for the units permitted in the future, which very quickly becomes wild speculation and is outside the scope of this project. This is why the line for expected housing units takes a significant drop after 2021. 

![third_chart](/images/austin_housing_predictions.png)

The previous projection line serves as a good baseline for comparison of actual housing completion as these projects get finished, however, it does not provide an adjusted estimate for when housing supply will catch up to demand. To provide a best-fit estimation for the projected completion adjustment, I added between 3 and 24 months to the projections, and found that adding a delay of 10 months does an acceptable job of both reflecting the measured truths for 2019 and 2020, and providing a realistic looking expectation for 2021. 

![fourth_chart](/images/ten_month_projections.png)

### Question 2 Results: New housing supply for Austin could catch up with demand by 2022.
---

There are far too many variables at play here to be able to make a definitive prediction about the new housing supply returning to normal cycles, but using a few reasonable assumptions, we are able to make a estimation that the Austin new housing supply could get back on track by next year. It will be interesting to track how this model stacks up in real time, and try to understand where it has succeeded and where my assumptions went wrong. 

---

### Summary And Next Steps:
---

In sum, I imported the dataset from the Austin city data API, worked with the data using Python inside a Jupyter Notebook, visualized the data, and built a predictive model to provide context for my conclusions and provide insight for the market direction. I found that 1) There is a large gap between Austin's new housing supply and demand that has emerged during the Covid pandemic, and 2) It is possible that the gap will close by the end of 2022. 

Here are a few possible extensions of this project, and other considerations that I came across, that I would like to look into in the future:

- In the course of this project I found numerous errors and issues with this dataset, ranging from permits that were finished before they started, to a duplex that was listed as having 1200 housing units. I already have a notebook underway examining those issues and their impacts on this project and other reporting efforts that use this dataset. 
- I did not account for the demolition of housing units and how that effected the annual net totals. For example tearing down a house to subdivide and build two houses has a very different effect than tearing down a house to build an apartment building. Where is the most demolition occurring? Has demolition increased over time? Does demolition contribute to overall densification?
- I would like to build a more sophisticated model for the Covid delay that takes into account longer delays associated with larger projects and much shorter delays for single family housing. 
- How does Austin's new construction relate with its household growth and population growth? 
- How does new construction affect real estate or rental pricing?
- What does Austin's housing stock to flow ratio look like over time and how does Austin's building cycle compare to other metropolitan areas?
- I would like to write a script to automate updates for this chart to see how my predictions hold up over time. 

---

click [here](https://github.com/nathaniel-j/Austin-Building-Boom/blob/main/austin_housing_II.ipynb) to see the full project on Github.

---

