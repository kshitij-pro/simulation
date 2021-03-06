## Problem Statement

Consider an (M, L) inventory system in which procurement quantity Q is given by

![](https://github.com/kshitij-pro/simulation/blob/ab6d669c4ff6cf0b8eee88174e3dcf2ca718309b/Screenshot%202021-08-13%20161453.png)

where I is the level of inventory on hand plus order at the end of the month, M is the maximum inventory level, and L is the reorder point. M and L are under management control, so the pair (M,L)	is called inventory policy. Under certain conditions, the analytical solution of such a model is possible, but not always. Use simulation to investigate an (M, L) inventory system with the following properties: The inventory status is checked at the end of the month. Backordering is allowed at a cost of $4 per item short per month. When an order arrives, it will be used to relieve the backorder. The lead time is given by a uniform distribution on the interval [0.25, 1.25] months. Let the beginning inventory stand at 50 units, with no orders outstanding. Let the holding cost be $1 per month in inventory per month. Assume that the inventory position is reviewed each month. If an order is placed its cost is $60 + $5Q, where $60 is the ordering cost and $5 is the cost of each item.

The time between demands is exponentially distributed with a mean of 1/15 month. The sizes of the demand follow this distribution:

![](https://github.com/kshitij-pro/simulation/blob/cffe2cb0edff76044f2e9587bfa6b437e87197d5/Screenshot%202021-08-13%20161517.png)

Now, the items are perishable, with a selling price given by the following data:

![](https://github.com/kshitij-pro/simulation/blob/2579c4d4341003baa41e0db70a72eba79478c6a6/Screenshot%202021-08-13%20161536.png)

Thus, any item that has been on the shelf for more than 2 months cannot be sold. The age is measured at the time the demand occurs. If an item is outdated, it is discarded, and the next time is brought forward. Simulate the system for 100 months.

(a)	Make ten independent replications for the (M, L ) = (50, 30) policy, and estimate long-run mean monthly cost and profit with a 90% confidence interval.

(b)	Using results of part(a), estimate the total number of replications needed to estimate mean monthly cost within $5. Run the model the required number of replications and construct the CI.

![](https://github.com/kshitij-pro/simulation/blob/2794e457bd502ccb657b5bba371a30384c0667cf/Screenshot%202021-08-13%20162233.png)

Option B: Keep Factor1 at Level 1, and Factory 5 at Level 2.  Compare the performances of systems across the design points of F2, F3 and F4 (total 8 combinations). Also, find the minimum mean monthly profit combination of M and L such that CSL is >= 95%

## Results

(a)	Make ten independent replications for the (M, L ) = (50, 30) policy, and estimate long-run mean monthly cost and profit with a 90% confidence interval.

1.	mean of 90% CI for mean_monthly_cost 235.26 90% CI half width for mean_monthly_cost 5.14

2.	mean of 90% CI for monthly_profit 12.7 90% CI half width for monthly_profit 4.35

These 2 CI???s were build using 10 replications and 100 months simulation run.

Warm up period was assumed to be zero as it was not mentioned in question.

(b)	Using results of part(a), estimate the total number of replications needed to estimate mean monthly cost within $5.Run the model the required number of replications and construct the CI.

Using R_required =

R*(current_half_width)^2/(required_half_width)^2

required_half_width = 5

current_half_width = 5.14
 
R_required = 11

After running simulation again for 11 replications-

NEW HALF WIDTH FOR 90% CI OF MONTHLY COST =  3.71

C). Comparing Alternatives

Option B Topic 2

Keep F1 fixed to level 1 and F5 to level 2.

Main and interaction effect of F2, F3, and F4 on mean_monthly_profit-

![](https://github.com/kshitij-pro/simulation/blob/2fdb3ee1da96e976443470c1c1c18e44fb00d13d/Screenshot%202021-08-13%20163000.png)

Simulation optimization--
 
Find the maximum mean monthly profit combination of M and L such that CSL is >= 95%
 
For this first we build the response surface for monthly_profit with F3 and F4.

![](https://github.com/kshitij-pro/simulation/blob/388fb2eabe5785ad6e6689e82b685c2559e12024/Screenshot%202021-08-13%20163017.png)

e3_bar = -66.32

e4_bar = -8.03

e34_bar = -0.35

e3_bar = -66.32 means that when M is switched from 50(low) to 100(high) on average profit is reduced by 66.32 So low value of M is preferred for good profit.

Similarly, e4_bar = -8.03 means that if L is switched from 30(low) to 40(high) then on average monthly profit is reduced by 8.03. So low value of L is preferred for good profit.

Low value of e34_bar indicates that there combined effect on monthly_profit is negligible so the response surface is more or less a plane.

In the similar manner we also calculated effect on cycle service level (csl) by F3 and F4

![](https://github.com/kshitij-pro/simulation/blob/96bc2a8d8642141c95b4174d6917ac168462727e/Screenshot%202021-08-13%20163408.png)

Clearly switching F3 from 50 to 100 increases cls by 0.22 on average but F4 has no. effect as the CI contains zero.

So, there is a tradeoff between the mean_monthly_profit and CSL. If we decrease M and L then there is positive change in mean_monthly_profit and negative change in csl. So according to OptionB we need to find minimum value of M and L so that profit is max. and csl >= 0.95

M* = 108

L*=80

Csl* = 0.953

Mean_monthly_profit* = -Rs. 130.22
