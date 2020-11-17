## Pod Analyzer(PANAL)
This is a project I undertook at Amazon. Project is done on Microsoft Excel.  The objective of this project was to pull together data from multiple sources to be filtered for relevancy.  I also wrote a handbook/training 
manual for the role, which was written to be usable by inexperienced computer users and greatly improved training for the department.
#### Task: 
Orders are assigned a shipment ID and an individual item with corresponding inventory bin ID.  Bins are located in pods
that are driven by robots to workstations to be picked.

Due to trash/fallen items on the robotics floor, pods may become obstructed. Pods may also be taken off the robotics floor for maintenance. Items may still be ordered from
retricted (offline/obstructed) pods, but must be picked by physically finding and retrieving that item or an identical item.
Orders located in restricted pods must be discovered and picked before assigned shipment time.

Original process involved searching for restriction info individually by bin ID, requiring user to go one-by-one down a list of thousands of items to discover issues.  Inventory is located on all four floors of a 855,000sqft. warehouse, so retrieval is time-consuming.
##### Challenges:
1. Restricted pods are listed only by pod ID, orders only give bin ID, with 80-85 bins per pod.
2. A separate app 'Adjacent Bins' can be used to convert bin IDs to pod IDs, but shipment IDs or item IDs won't correlate.
3. Restricted pod reports are floor-specific, with four individual floors.

##### Solution:
1. Excel workbook pulls data from each 'restricted pod report' webpage, then references info on a central 'Pod Analyzer' wooksheet. 
2. Bin IDs can be copied and pasted en-mass to 'Adjacent Bins' app to find pod IDs.
3. Pod IDs are copied and pasted to 'Pod Analyzer' worksheet.  Conditional formatting highlights all restricted pods containing orders.
4. User can reverse the process using the IDs for pods containing orders to find any necessary info.

##### Outcome:
Using this tool, issues can be found much earlier, retrieval routes can be optimized, and missed shipments can be avoided.
At peak order volume of ~300,000 items/shift, this function can be performed by one person, where it used to require 2-4.

## Pallet Analyzer:
This workbook also contains a tool to organize orders for items in palletized inventory by shipment time. 
Pallet areas are located on all four floors and pickers must be reassigned when they run out of work.
Since inventory is not moved by robotic drives, but rather picked by physically travelling to the item location, pick rates are much lower.
Labor should be allocated to floors containing upcoming shipments when shipment times are close, and to floors with the most orders when possible.
This workbook provides visual, up-to-date, and simple ways to view order volume by floor and see where the most time-sensitive work is located on the 'Pallet Analyzer' sheet.
This worksheet makes great use of COUNTIF based on a string search, MAX to locate 'total' values on a variable-size table, and SUMIFS to filter by keyword.

## Sheet descriptions:
- Floor sheets display raw data pulled from individual restricted pod reports and are usually hidden for users
- 'Pod Analyzer' is a tool for correlating a given list of pod ID to restricted pods 
- 'Pallet Analyzer' is a tool for sorting all orders in palletized inventory by floor location and shipment time
- 'CE links' provides hyperlinks (deactivated in this copy) to useful internal webpages and apps
- "1100", "1200", "1300", etc. are shipment times.  These sheets display order information for each shipment and are usually hidden for users
- 'Pallet backlog' provides unintuitive data on orders that are available to pick.  Data is simplified on 'Pallet Analyzer'.  Sheet is usually hidden for users
