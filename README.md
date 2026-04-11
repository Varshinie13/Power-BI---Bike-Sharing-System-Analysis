Bike-Share System Analytics

Project Overview & Data Modeling

The goal of this project is to monitor a large-scale bike-sharing network. To handle 2,857 rows efficiently, the data was organized into a Star Schema to ensure fast filtering and accurate calculations.
Data Modelling Strategy
•	Fact Table: Centralized station records (Occupancy, Bikes, Status).
•	Calculated Measures: Developed using DAX to move away from static data to dynamic insights.
•	Relationships: Linked Station Category and Day Type to the main fact table using *:* (Many-to-Many) relationships.

Tools Used:

Power BI : ETL process, Data Modelling, Create Calculated Columns, DAX Function
Power Query Editor: Data Cleaning, Remove Null Values, Handle Missing Data.

Dashboard Overview

The "Bike-Share System Analysis Dashboard," provides a comprehensive view of operational health, station capacity, and availability across various station categories and day types (Weekday vs. Weekend).
1. High-Level KPIs 
•	Avg Availability %: 0.34% (This indicates extremely low real-time availability across the network).
•	Bike Churn: 54 (The frequency of bike rotations).
•	Total Available: 32K (Total bikes currently in the system).
•	Empty Stations: 705 (A significant number of stations currently have no bikes).
•	Bikes Lost: 4K (A notable loss metric that may require operational investigation).
________________________________________
2. Key Visualizations & Findings
Station Health & Status:
•	Status of Bike Stand: A donut chart shows that 92.78% of stands are OPEN, while 7.22% are CLOSED.
•	Station Health by Name: Most stations are categorized as "Healthy" (approx. 2.01K), but a significant portion (0.71K) are in a "Critical" state, likely meaning they are either completely full or completely empty.
Occupancy and Availability
•	Available Bikes vs. Available Bike Stands: 
o	The gauge shows a value of 6.88 against a max of 11.25. This suggests that, on average, stations are just over half-full.
•	Occupancy % by Name: 
o	The top stations (PATI..., NOV...) are hitting occupancy rates of 34% to 36%. This confirms that even the "busiest" stations aren't nearing 100% capacity, correlating with the high number of empty stations seen in the KPIs.
•	Category vs. Occupancy by Days: 
o	Medium Stations have the highest occupancy rate (1.79).
o	Large/High-Capacity stations have a much lower occupancy rate (0.72).
•	Infrastructure Distribution:
o	Available Bike Stands by Station Category: A Treemap shows that Large Stations (High Capacity) hold the vast majority of the system's docking capacity (represented by the large blue block), while Medium and Small stations make up a much smaller fraction.

Summary of Key Findings

•	Operational Imbalance: With 705 empty stations and 4K bikes lost, there is a major distribution issue. The system has 32K bikes, but they are not where the users need them, or they are out of service.
•	Underutilization of High-Capacity Hubs: The Treemap shows Large Stations have the most stands, yet the "Category vs. Occupancy" table shows they have the lowest occupancy (0.72). Users seem to prefer Medium Stations (1.79 occupancy).
•	Low Availability: An average availability of 0.34% is a critical pain point. This suggests that while there are many stands, the "ready-to-use" bike percentage is nearly zero, or the data is filtered to a specific high-demand moment.
•	Weekday vs. Weekend Stability: The bar chart for "Available Bikes by Bonus Eligibility" shows relatively stable patterns between weekdays and weekends, suggesting the current system load doesn't fluctuate wildly based on the day of the week.


Conclusion
The analysis reveals a system suffering from a severe distribution imbalance. Despite having a functional infrastructure with over 90% of stands open, the system is failing its primary objective of reliability, evidenced by the 705 empty stations and a critically low 0.34% availability rate.
The data suggests that the current logistics strategy is reactive rather than proactive. Large-capacity hubs are being underutilized while smaller stations are over-leveraged, and the loss of 4,000 bikes has created a fleet deficit that further exacerbates the "critical" health status of the network. To restore operational viability, the system must prioritize aggressive manual rebalancing and asset recovery to ensure bikes are available where demand is highest.
Strategic Recommendation
To improve the system's health, management should focus on dynamic rebalancing—moving bikes from the underutilized "Large Stations" to the "Medium Stations" and empty zones. Additionally, investigating the 4K lost bikes is essential to restoring the fleet to a level that can support the current number of docking stands.

