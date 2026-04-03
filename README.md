# Group 4 MIST 4610 Group Project 1
# Team Name: 
61608 Group 4
# Team Members:
1. Jacob Witucki [@JacobWitucki](https://github.com/JacobWitucki)
2. Ashleigh Serrafin [@AshleighSerafin](https://github.com/AshleighSerafin)
3. Bryce Riemersma [@Bryceriem](https://github.com/Bryceriem)
4. Lily Shaw  [@Lilyshaw714](https://github.com/Lilyshaw714)
5. Matt Miller  [@matthewroanmiller](https://github.com/matthewroanmiller)
6. Sheuti Alladi  [@salladi13](https://github.com/alladi13)
# Problem Description
The problem at hand is to model and build a strong database for the general workings of a drone delivery company located in a dense urban city. The model begins with the customer entity, this is where orders start. The customer entity is connected directly with orders which then moves into the rest of the model. The rest of our model is drone specific, centered around the entity, Drone Assignemnts. Drone assignments is seen as a central piece throughout the model, this entity explains which drones are on which routes. This entity has four relationships within the model; 1-M with Deliveries, 1-M with Routes, 1-M with Drones, and 1-M with Incidents. As a group we are interested in correctly modeling the business process and answering three main questions for business executives: What needs to be delivered? How will the delivery happen? When does a drone require maintenance? How do we manage battery levels and charging station efficiency? 
# Data Model
Explanation of Data Model:  

This data model represents a comprehensive drone delivery and operations management system designed to track the full lifecycle of a delivery, from customer order placement through drone execution, charging, maintenance, and safety monitoring. At the front of the process, **Customers** store contact and address information for individuals placing delivery requests, and each customer can create multiple **Orders**. Orders capture transactional details such as order date, status, and total amount, and they serve as containers for one or more **Packages**, which store physical shipment characteristics like weight, dimensions, priority level, and whether the package is fragile. This separation allows the system to handle complex orders containing multiple items with different delivery constraints.

Delivery planning and execution are handled through **Routes** and **Drone\_Assignments**. Routes define planned delivery paths, including start and end times, total distance, and current execution status. Drone assignments act as a critical linking entity that connects a specific drone, route, and package, allowing the system to schedule deliveries, record actual drop-off times, track assignment outcomes, and document failure reasons when deliveries do not succeed. This design supports flexible operational scenarios, such as a single drone delivering multiple packages or multiple drones operating along the same route.

The **Drones** entity represents the physical fleet, storing drone identifiers, models, operational status, maximum payload capacity, purchase dates, and accumulated flight hours. Drones are linked to multiple operational records, including assignments, incidents, maintenance activities, and charging sessions, which collectively provide a complete operational history for each unit. Maintenance activities are captured in **Maintenance\_Logs**, which record when maintenance occurred, what type of service was performed, the drone’s operating hours at the time, and technician notes. These logs are associated with **Technicians**, who are defined by their names and certification levels, supporting accountability and regulatory compliance.

Energy and infrastructure management are handled through **Charging\_Stations** and **Station\_Sessions**. Charging stations define the available charging infrastructure and power capacity, while station sessions record each charging event, including the drone involved, the station used, session timing, and energy consumed. This structure enables energy usage analysis, operational optimization, and sustainability reporting. Finally, operational risks and exceptions are captured in the **Incidents** table, which logs safety or performance issues related to specific drones and assignments, along with incident types, severity levels, timestamps, and descriptions. Together, these interconnected entities form a normalized, scalable schema that supports traceability, operational insight, and analytics across all aspects of a drone delivery system.
   
<img width="683" height="458" alt="Screenshot 2026-03-30 at 6 41 21 PM" src="https://github.com/user-attachments/assets/a52790be-6fde-48e5-9961-76eba6d918b0" />

# Data Dictionary:
<img width="662" height="518" alt="Screenshot 2026-04-02 at 6 22 03 PM" src="https://github.com/user-attachments/assets/884449ad-38c4-4131-b2bc-efef91f9e756" />
<img width="642" height="436" alt="Screenshot 2026-03-30 at 10 46 02 PM" src="https://github.com/user-attachments/assets/027a60b7-1810-403a-9515-01530ff27b02" />  
<img width="539" height="625" alt="Screenshot 2026-04-01 at 12 32 29 PM" src="https://github.com/user-attachments/assets/5642881a-b210-4cb1-a1bd-160fcdab1d75" />
<img width="585" height="558" alt="Screenshot 2026-04-01 at 12 32 45 PM" src="https://github.com/user-attachments/assets/58cdd6be-dcfe-4e77-8db9-e55d7961c030" />
<img width="658" height="622" alt="Screenshot 2026-04-01 at 12 27 23 PM" src="https://github.com/user-attachments/assets/21e53f51-2c05-40b3-b29d-be2221ac7b50" />
<img width="644" height="649" alt="Screenshot 2026-04-01 at 12 27 45 PM" src="https://github.com/user-attachments/assets/e602a978-d091-4f3e-91dd-61277f0381b5" />
<img width="504" height="601" alt="Screenshot 2026-04-01 at 12 28 11 PM" src="https://github.com/user-attachments/assets/171287c0-46b7-4837-8693-ec97689cd78f" />
<img width="653" height="359" alt="Screenshot 2026-04-01 at 12 28 25 PM" src="https://github.com/user-attachments/assets/8127f000-95db-4425-bc8a-dc9762d14432" />
<img width="648" height="414" alt="Screenshot 2026-04-01 at 12 29 47 PM" src="https://github.com/user-attachments/assets/581be807-1f84-4750-8830-5e6033ee3b8d" />
<img width="644" height="548" alt="Screenshot 2026-04-01 at 12 30 03 PM" src="https://github.com/user-attachments/assets/9fb2122a-fdb1-4f72-a662-291c2be790dc" />
<img width="586" height="279" alt="Screenshot 2026-04-01 at 12 33 30 PM" src="https://github.com/user-attachments/assets/6969aa1b-74fe-478f-bc34-5631e742bb8f" />


# Queries:  
<img width="759" height="465" alt="Screenshot 2026-04-02 at 6 27 49 PM" src="https://github.com/user-attachments/assets/bc368483-19dd-4f2f-85e2-b0b0a3f21511" />  

1. Query 1 lists the customer names with specific orders totaling over 100 and whose order status is shipped. This query is also ordered by customer ID and grouped by it to show how many orders meet the requirements for each customer. This allows the drone company to track high-value orders that have already been shipped, helping with financial statements and performance status. 
<img width="1220" height="652" alt="Screenshot 2026-04-02 at 6 21 13 PM" src="https://github.com/user-attachments/assets/f8bcf3f1-78e2-4b5a-aa2a-1cdc8de2c757" />
2. Query 2 lists the drone id, serial number, and number of incidents each DJI modeled drone. The query restricts the drones chosen by only giving the drones with 2 or less incidents. The drone company may use this information to track the performance of the specific model of drone in order to make decisions on future investments when it comes to expanding the fleet.  
<img width="1219" height="654" alt="Screenshot 2026-04-02 at 6 23 01 PM" src="https://github.com/user-attachments/assets/346cf7b1-705d-4335-ba71-257055d19404" />
3. Query 3 shows the performance and utilization of each drone model in the fleet. It lists the average total flight hours across all models, the average weight in kilograms of packages successfully delivered, and the total number of completed deliveries. Results are grouped by model so that the company can compare how different drone models are being utilized, which can inform future fleet expansion and procurement decisions.
<img width="1219" height="655" alt="Screenshot 2026-04-03 at 11 09 56 AM" src="https://github.com/user-attachments/assets/b43fb7cf-d98c-4856-a42c-846ad8e66241" />
4. Query 4 shows the drone ID, the serial number, and the number of times each drone was not in compliance with the logged maintenance every 50 hours rule. This information may be used for internal company audits.
<img width="1219" height="652" alt="Screenshot 2026-04-03 at 11 12 43 AM" src="https://github.com/user-attachments/assets/52e8f53c-e7f2-4176-81e2-c8d77bc0c9a5" />
5. Query 5 reports the energy consumption activity of each charging station that has served a Matrice, Zipline, or Wingcopter drone. It shows how many completed charging sessions each station has handled and the average energy drawn per session, filtering to only stations averaging more than 10 kilowatt-hours. Fleet managers can use this to identify which stations are handling the heaviest charging workloads, informing decisions about station placement, power capacity upgrades, and whether certain stations are being over-relied upon.
<img width="1219" height="652" alt="Screenshot 2026-04-03 at 11 15 04 AM" src="https://github.com/user-attachments/assets/dd0305d7-4b00-475d-89b4-27961d4f3d0b" />
6. Query 6 returns all completed routes over 15 kilometers that had no failed or cancelled assignments at any point during execution. The subquery pulls every route that experienced a failure or cancellation, and the outer query excludes them entirely, leaving only routes that ran cleanly end to end. Operations managers can use this to build a verified list of high-distance routes with a perfect execution record, which can inform route prioritization and serve as benchmarks when planning new delivery corridors.
<img width="1220" height="653" alt="Screenshot 2026-04-03 at 11 23 53 AM" src="https://github.com/user-attachments/assets/9b20f7f8-b975-40c0-9da1-7f2bf540d894" />
7. This query retrieves the customer ID, name, and email of customers who have placed at least one order but have never had an incident associated with any of their deliveries. This information is valuable for targeted marketing, such as loyalty rewards or promotions, because it shows customers who are likely very satisfied with the services.
<img width="1218" height="653" alt="Screenshot 2026-04-03 at 12 01 26 PM" src="https://github.com/user-attachments/assets/573d2ad6-74cb-415c-a867-39391f1d0ff1" />
8. This query retrieves all active level 3 certified technicians and summarizes their maintenance activity across all service types. For each technician, it returns the total number of services performed, the total hours logged, and the average hours spent per service. The results are ordered by total hours logged from highest to lowest. This is important because it allows management to identify which of their most qualified technicians are carrying the heaviest workload.
<img width="1221" height="651" alt="Screenshot 2026-04-03 at 12 05 14 PM" src="https://github.com/user-attachments/assets/23f76db7-a4fa-48a0-9ca2-343f2c4e6178" />
9. Query 9 shows which completed routes generated the most total revenue. It returns the route ID, the total number of shipped orders on that route, and the total revenue produced from those orders. The results are grouped by route and filtered to only include routes with more than $100 in total revenue. This is useful for showing the delivery routes that are the most profitable.
<img width="1219" height="656" alt="Screenshot 2026-04-03 at 12 07 56 PM" src="https://github.com/user-attachments/assets/dd765ff7-e3d7-49ed-a341-dbd308fbd367" />
10. Query 10 shows drones that have never been involved in any incidents. It returns the drone ID, model, and total flight hours for each of these drones. This is important because it shows which drones have a clean safety record, which can help with assigning future assignments.
<img width="1220" height="653" alt="Screenshot 2026-04-03 at 12 09 01 PM" src="https://github.com/user-attachments/assets/98927be2-5957-49c2-9b25-a6744595294d" />

# Database Information:  

Name of the database: ns_Sp26_61608_Group4 

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1();
