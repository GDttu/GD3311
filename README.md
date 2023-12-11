# Redistricting in Maine
IE 3311 Final Project
By: Gabriel Dougherty

## Executive Summary

There is no doubt that the state of Maine has struggled with maintaining a consistent spread of districts. This is mainly due to the majority of the population being focused around the large cities of the Southern region. Out of the 16 total counties, the densely populated district contains eight of them yet only spans around ten percent of Maine’s total area. As a result of this, the northern district has almost ten times the total area compared to the southern. The lack of consistency in shape and size also causes the county map to seem very cluttered, which can therefore lead to confusion when put under analysis. Because of the large difference in available land, rural lifestyles are a lot more common in the northern district while the south is more urban focused. Issues arise around this due to the historically continuous political stereotypes found when compared to lifestyles. As seen in figure 1, the majority of the densely populated counties are blue while the spacious, rural areas are mostly red. Fortunately, the layout of the counties is focused around each major city and then extended based upon the surrounding area’s population. This should allow for the redistricting process to be extremely simple to execute as the county lines will remain intact as per the constitution.

![Figure 1](readme_images/.png?raw=true)

## Criteria

Redistricting in any state can be very difficult to smoothly implement among multiple large areas of residents. For this reason, there are federal criteria in place to help ensure that the process is as least invasive to everyone involved as possible. These criteria include requiring all districts to be nearly equal in population and not discriminated by race. Other principles can also be adopted by states, but some choose to only use the required. Compactness and contiguity are the most commonly adopted criteria as they are the perfect baseline for a district. Compactness has the layout of the district use as little distance between buildings as possible and contiguity connects these all together to form a structural community. Prohibitions have also made their way into these criteria in order to maintain balance. These prohibitions include preventing favoritism by banning the drawing of district lines based on political or socio-economic data.
There are many other different forms of criteria that can be considered when a state wants to begin a redistricting project, however the examples listed above are pertinent to Maine. Section 2 of Article IV, part first of the Constitution of the State of Maine, states, “the commission shall ensure that each congressional district is formed of compact and contiguous territory...”. From this, it is obvious that Maine is only concerned with keeping their districts close together and connected as the rest of section two is dedicated to establishing a time frame for the redistricting plan. There is no information currently available on how these criteria are enforced, however there is currently a republican introduced bill hoping to have district maps be drawn from Census data rather than the ACS estimations.

## Problem Statement

Due to the inconveniently shaped counties and population bias of the south, Maine could benefit from a balancing of district sizes. As the southeast is approached, the districts tighten in proportion to the increase in population. As seen in figures 2 and 3, district one consists of only counties under 1,000 mi^2, all of which just happen to be the most densely populated. The “clump” of counties along the Gulf of Maine could be fit multiple times into the northern district, this can cause issues as the physical size of each district is significantly impacted by the population size of each county. In order to combat this, multiple strategies can be used to test different methods of redistricting until a desired result is found. The goal of these strategies is to determine a new optimal district planning solution by maximizing the total square mileage of each district while keeping the populations within the set boundaries.

![Figure 1](readme_images/.png?raw=true)

## Optimization Model in Words

*	1 function used to minimize the amount of space each district takes up based on the population and size of each county.
* 16 variables so that each county may have its own associated population and size data.
* 2 constraints, one for ensuring all counties are included, and one for maximum population deviation.

These functions use the population and current area of a selected district to determine by how much its area should be increased or reduced by. These functions will be constrained by a maximum population of 681,179 per district (determined by dividing the total population by the number of districts) along with a total square mileage of 1927.29 mi^2 per county within each district. Each district’s population will be determined by the sum of all of the relevant counties’ populations. Once the new district’s populations are established, the validity of the plan can be determined ensuring there is a population deviation of less than 1% between the two districts.

## Experiments

Specifications

* Memory: 32 GB DDR5 4800 MHz
* Processor: i7-12700H 4.7 GHz
* Optimizer: Gurobi Version 11.0.0

Experiment 1:

![Figure 1](readme_images/.png?raw=true)

![Figure 1](readme_images/.png?raw=true)

The results of this experiment were determined by using a Wiliams-based model edited to remove the maximum population deviation constraint which causes the focus to shift from population based to area based. This experiment successfully divided the districts evenly by their counties’ total area seen by the almost 50% split in colors. However, the population deviation between these two districts came out to around 2.14%, making this solution not ideal.

Experiment 2:

![Figure 1](readme_images/.png?raw=true)

![Figure 1](readme_images/.png?raw=true)

The results of this experiment were determined by using a Wiliams-based model. This experiment resulted in a less desired division of land due to the blue district being concentrated to the southwest of Maine. However, because the population density for these southern counties is so high, the best possible population deviation of 0.41% is able to be achieved.

## Evaluation

![Figure 1](readme_images/.png?raw=true)

![Figure 1](readme_images/.png?raw=true)

The solution that is being proposed takes aspects from both experiments one and two. This redistricting plan uses the map that offered the best population deviation along with the formula that offered the shortest paths between counties to Experiment one seemed to have a more superior method to determine the shortest paths between counties as the connections have less significant jumps and extensions from the center. When comparing the land distributions, experiment two’s plan is not as ideal as the first due to district one incorporating more of the densely populated areas. However, the population deviation is almost four times better than that of experiment one making this a more optimal solution.

## Conclusion

In conclusion, Maine could benefit from a new district map as the current one suffers from a significant political division. After conducting experiments using different optimization methods in order to find the most optimal redistricting plan, the presented solution was determined to be better than the current one in place. The distance between county centers is as short as it can be while also ensuring the calculated population deviation is at or below the 1% limit. The repository titled, “Linear-size-formulations-for-connected-planar-graph-partitioning-and-political-districting,” was heavily referenced and used to determine the data for the displayed experiments and plans. The lack of any form of code in this report is a result of this, poor preparation, and time management issues.
