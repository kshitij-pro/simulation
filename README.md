# simulation

Consider an (M, L) inventory system in which procurement quantity Q is given by

where I is the level of inventory on hand plus order at the end of the month, M is the maximum inventory level, and L is the reorder point. M and L are under management control, so the pair (M,L)	is called inventory policy. Under certain conditions, the analytical solution of such a model is possible, but not always. Use simulation to investigate an (M, L) inventory system with the following properties: The inventory status is checked at the end of the month. Backordering is allowed at a cost of $4 per item short per month. When an order arrives, it will be used to relieve the backorder. The lead time is given by a uniform distribution on the interval [0.25, 1.25] months. Let the beginning inventory stand at 50 units, with no orders outstanding. Let the holding cost be $1 per month in inventory per month. Assume that the inventory position is reviewed each month. If an order is placed its cost is $60 + $5Q, where $60 is the ordering cost and $5 is the cost of each item.

The time between demands is exponentially distributed with a mean of 1/15 month. The sizes of the demand follow this distribution:


Now, the items are perishable, with a selling price given by the following data:


Thus, any item that has been on the shelf for more than 2 months cannot be sold. The age is measured at the time the demand occurs. If an item is outdated, it is discarded, and the next time is brought forward. Simulate the system for 100 months.

(a)	Make ten independent replications for the (M, L ) = (50, 30) policy, and estimate long-run mean monthly cost and profit with a 90% confidence interval.

(b)	Using results of part(a), estimate the total number of replications needed to estimate mean monthly cost within $5. Run the model the required number of replications and construct the CI.


