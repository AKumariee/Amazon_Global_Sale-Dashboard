
# Amazon Global sale dashboard
Objective: Profitable Products, Loss Products and Profitable customers

Steps:
1. Connecting Database
2. Data Cleaning - Power Query
3. Analyzing table relations
4. Developing Visualization models
5. Creating a report and pin to dashboard
_______________________________________________________________________________
**Download the Project file**
Data link: https://docs.google.com/spreadsheets/d/1Zk7O-NUWbASBKE949knkmFvMh--4U4GR/edit?gid=1634348971#gid=1634348971

**Load data into Power BI Desktop**
Open Power BI Desktop-->Home-->Get data-->Import data from Excel-->choose the relevant document or sheet to load
In Navigator page - tick the checkbox you want to display then click on Load button

**Data Cleaning and Transformation**
Using Power Quey Editor
Power Bi Desktop--> Transform data(in Queries) --> Power Query Editor

__Problem statement__: In People it is showing Column1 and column2 as header  instead Person and region.
Screenshot: 
![Image description](/Images/people_header.PNG)


In returns it is showing column1,column2 and column3 as header instead of return
Screenshot: 
![Image description](/Images/return_header.PNG)


__Solution__: In Transformation section --> Use First Row as Header

Navigate to Power Bi Desktop by clicking on close and apply

***Analyzing columns or attributes***
 1. Between order date and ship date , delivery date is missing
 2. Postal code having null values

Steps to generating attribute"delivery date"
* From the Home tab on the ribbon, select Transform data, and then select Transform data from the menu. 
Power Query editor will appear-->(Ribbon)Add Column-->Custom Column.
* Custom column window will appear then
fill the details as follow:
New Column Name:delivery date
Custom Column Formula:***[Order Date]-[Ship Date]***
* insert order date and ship date from "Available columns" list on the right 

__Problem Statement__: Delivery date formate is differing and negative value
 ![Image description](/Images/delivery_date.PNG)

__Solution__: Home-->Data Type(in ribbon)--> whole Number : It will give number of days then,
Right Click on column-->Transform-->Absolute Value : It will give positive value

[Note:Delivery date name is changed later on as delivery days since we are extracting days not date.]

***Cleaning Data from Order date and extracting year***
* Open Power query Editor by clicking Transform data in BI Desktop-->Add Column-->Custom Column(from ribbon)-->custom column window appears then,
* Fill the details as follow:
New Column Name:year
Custom Column Formula:***Date.year(Order Date) 
* Insert order date from "Available Columns"
list on the right.

 ![Image description](/Images/year.PNG)

***Adding Conditional column in Return:***
In Power Query Editor-->in Returns Queries-->click on Add Column-->Conditiona Column(on ribbon)
* Conditional column window will appear then fill the details of if else statement as follow:
![Image description](/Images/return1.PNG)

**Developing visualization model**
***Making slicer***
on the right side, in Vizualization pane look for slicer icon, as shown below(marked with red boundaries):
![Image description](/Images/slicer.PNG)

Add year from data section to field by dragging in order to build visualization as shown below:
![Image description](/Images/add_year.PNG)
It will show years in slicer like this:
![Image description](/Images/year_in_slicer.PNG)

formatting slicer visual:
first click or select the slicer page in power query home window then go to-->on the right side, in Vizualization pane --> Go to format your visuals then-->slicer setting
![Image description](/Images/slicer_styling.PNG)

To format the page styling or inserting images first select the page on home then-->on the right side, in Vizualization pane-->click on format your report page
Multiple options will arrise like Page information,Canvas setting,Canvas background,wallpaper etc. from these option we could format our page as we want
for example:by inserting wallpapers slicer visual after formatting:
![Image description](/Images/formatted_slicer.PNG)

***Making Cards***

