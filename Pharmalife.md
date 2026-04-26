# PharmaLife Dashboard

Pharmalife is a medical product distributor for around 10 medical pharmacies in Nepal. It's major business is medical reselling through its counters attached to hospitals through out the country.

## Current Scenerio

Major business: Medical Product Reselling
First level customers: Various Pharmacies through out the country, pharmacies are owned by their respective hospitals. PharmaLife bills to those pharmacies and delivers products. 

Second Level Customers: PharmaLife wants to extend its business towards direct B2C product selling, take orders from users directly and deliver products to customers from the nearest pharmacies which have affiliation with PharmaLife and bills are maintained at the pharmacies it gets delivered from. 

Main leverage they want to tap in: 
To increase and extend the business, PharmaLife is tryiing to orchestrate the data available to it. All the sales data from each counter has customers details, contact info, medicine list, and the cycle they took the medicine for. 
After a certain time, the same customer can be needing same set of medicine or a particular medicine for another cycle. 
What if we track them all, push it into a common database, create a team that follows it and make sure to follow up with the patients about their needs when the cycle is about end and new is about to begin. 
the follow up shall be manual for now - it can be automated through email, whatsapp or sms later and maybe get a dedicated mobile app for these and notify customer through the app in near future.
So the main idea is to orchestrate customers from all the counters, keep track of all their medical cycle and follow up them for new cycle. 
More of customer retention. Capitalization of customer details and their medical cycle info. 

So for this extension, 
We're planning a platform where 
Admin can:

Upload a central Master Item
Follow Up goals
Create Counters and Add individual Master Item List for that counter

Counter Dashboard:
Upload Sales Data (Everyday) 
Upload Stock data (Everyday)
Dashboard with Current Orders to fulfill - Accept/Decline

CSR Team
Optionally Create patients and add medicines/prescription (for online orders)

We do not care about other complexity this whole situation holds of un-unified data 
But we want to give solution with whatever they has right now. 
List of things they have right now:

- master item list (warehouse item list)
- Counter item list (item list of each counter)
- Aggregated Customers List to follow up (centralized and provided by admin as of now)
- Sales data from each counter - Everyday
- Stock Data from each counter - Everyday
Sales and Stock can run independently - The uploaded data would be the source of truth - sales and stocks shall not be checked and balanced.

## Problem Statement
- not all the medical counters ie, pharmacies do not use same platforms to maintain the stocks and billings
Master item list the pharma life maintains at warehouse is not identical to the counter item list 
They are coded with different names and unique identifier.    
We as a solution provider we are not resolving the item unification or centralizing the item list or main data 
But We're building a platform for a CSR team who can track the customers and the medical bills from different counters centrally. 
With different set of medical list its hard to track the medicine and map it to the list we have at the warehouse, ie, master item list 


## Solution Requirement:

Feature List: 
1. 3 levels of stakeholders/Users for the platform.
   Admin can:
   - Upload Master Item List 
   - Set goal/target for follow up 
   - Create Counters 
   - Upload Item list for each Counters 
   - progress Metrics in single Dashboard ( All meaningful infos, regarding CSR performance and sales patters ) 

  CSR Admin can:

  - Create CSR Users and Manage CSR users 
  - Set goal/target for each CSR user 
  - Suggest me more features for this user
  - Dashboard for details about CSR user performance
   
  - For online orders: [whole flow]
    Creates User [In app]
    Add user details [In app]
    Add medicine details [In app]
    CSR Sees Counters with availablity with listed items [In app]
    Selects "Ask Counter for Availability" [In app]
    Counter User gets and order - Accepts or Declines [In app]
    CSR gets notified and assigns the order to particular counter [In app]
    Counter dispatches medicine with the bill [Not in app]
    CSR sends respective counter QR and makes sure it is received [Not In app] 
    CSR then selects if any of these medicine should be notified for follow up [In app]
    if yes, it gets scheduled as a follow Up ticket

  Counter User:
  - Dashboard for Upload Notification
  - Upload sales data everyday
  - Upload stock upload everyday 
  - Daily Sales and Stock Uploader
  - Dashboard for Order Notification 
  -- Accept/Decline for each Notification
  -- Select or Accept for only available medicine list 

## Internal Design Thought process:

Admin: 
Master Item lists and Counter Item lists can be in excel this wont be much of a problem cause its not that changing
Related and meaningful metrics in dashboard shall be brainstromed and discussed


Counter User:
Uploading excel or csv from 8-10 different counters shall be huge and might have scalability issuses uploading.
Also, parsing and making it viewable to CSR shall be bottleneck technically
Also, We try to create user profile and attach prescription/medicine to their history and create follow up ticket for CSR by platform itself on the basis of sales data upload. 
How shall we parse and process that into our database so that we can use them to attach to users and make it meaningful in further use inside the platform

Also, these sales numbers and records are huge! 
We shall create a set of followup tickets by setting up some rules to make it practical and not overwhelming
cause we're talking about 20-30 thousands of sales each counter   - need suggestions

CSR:

CSR gets a ticketing board for everyday - with customer to follow up as ticktes with details. 
Need to make this efficient flow 

CSR needs to start the order and should be able to follow it through within the app. 

