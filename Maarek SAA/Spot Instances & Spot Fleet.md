#spot_instances #spot_fleet

- EC2 Spot Instances Requests
	- Can get a discount of up to 90% compared to On-demand
	- Define max spot price and get the instances while current spot price < max
		- The hourly spot price varies based on offer and capacity
		- If the current spot price > your max price you can choose to stop or terminate your instance with a 2 minutes grace period.
	- Other strategy: Spot Block
		- "block" spot instance during a specified time frame (1 to 6 hours) without interruptions 
		- In rare situations, the instance may be reclaimed
	- Used for batch jobs, data analysis, or workloads taht are resilient to failures
	- Not great for critical jobs or databases
- You can only cancel Spot Instance requests that are open, active, or disabled.
- Cancelling a Spot Request does not terminate instances
- You must first cancel a Spot Request, and then terminate the associated Spot Instances
- Spot Fleets
	- set of spot instances + (optional) On-demand instances
	- The Spot Fleet will try to meet the target capacity with price constraints
		- Define possible launch pools: instance type, OS, Availability Zone
		- Can have multiple launch pools, so that the fleet can choose
		- Spot Fleet stops launching instances when reaching capacity or max cost
	- Strategies to allocate Spot Instances
		- lowestPrice
		- diversified
		- capcacityOptimized
		- priceCapcacityOptimized (recommended)
	- Spot Fleets allow us to automatically request Spot Instances with the lowest price

