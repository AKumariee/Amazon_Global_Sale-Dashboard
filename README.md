
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
![Image description](/Images/formatted_slicer.PNG)   OR
![Image description](/Images/wallpaper.PNG)

***Making Cards***
I am giving an example to show method of creating card then after practicing I am making the required card for my page.
Suppose,a particular year of sales is shown as single number using card. It could be done as follow:
 Visualization-->click on card icon as shown:
 ![Image description](/Images/card.PNG)
 An Visual will be pop up on report and the relevant field like year have to fill using Data section as shown below:
 ![Image description](/Images/card_1.PNG)
 
 Format of the card (eg. text,labels,colour and more)could be change by going in visual section in right pan:
 visual-->format section-->in Visual section-->callout value
 change font, size and colour.
 Choose General-->expand Effects-->then expand Background.
 ![Image description](/Images/card_background.PNG)
 ![Image description](/Images/card_naming_visual.PNG)

 I made four cards here to show: 1.) Sales Projection, 2.) Quantity, 3.) KPI Ratings and 4.) Return 
 According to above method of creating card for year I'm going to make these cards.
 ***sales Projection Card making:***
 In the Year card I changed the field name from first year to slaes as follow:
 In visual section on right side of visualization pan--> in down side there is field dropdown menu. Search for sales on Data pan right most side, drag sales into field dropdown section. The total sum of sales will be visible on the card.
 ![Image description](/Images/sales_card.PNG)

 Title of card is changed to Sales Projection:
 go to format visual section on rigt visualization pan-->then General and from General section we can change title, effects, colour, size, font etc.
 ![Image description](/Images/sales_projection.PNG)
 ***Product Unit/Quantity making***
 select order quantity from data pan on right side-->it will show the ordered quantity. It will first show the text. to change it to numerical value click on  the same pan where field name has been added,in a drop down menue click count(distinct). Then it will show numerical value of product quantity.Change the name of card to Product Quantity from Visual section 

 ***KPI making***
 select Sum of Quantity from Data pan on right side and check drop down for count(distinctive)

 ***Return making***
 Select ship date from Data pan on right side and count check. 

 ***Adding logo of Amazon:***
 on top,ribbon-->click on Insert then-->click on image
 and from local computer choose a logo which is predownloaded according to our my choice, and insert that image. To format it go on visualization pan on right-->visual or general to change aspect ratio, colour of background and effects like shadow , roundness of corner.

**Chart Making** 

***Pie Chart***

To create new pie chart go to visual section on right visualization pan and click on pie chart icon as shown:
![Image description](/Images/pie_chart_icon.PNG)
In this way I have to adjust the colour and background styling of pie chart according to page theme. To save time I simply copied one of the card on page paste it on page and then select pie chart icon. It will generate pie chart according to page theme.
![Image description](/Images/pie_chart.PNG)
title name is segment and value is sale, select these from data section on right pan. The pie chart will be then created and to format the colour, font, styling go to general and explor effects, properties etc.
![Image description](/Images/pie_chart_segment.PNG)

***Donut chart***
To create new donut chart go to visual section on right visualization pan and click on donut chart icon. As previously discussed, to save effort and time,copy one of the card on page paste it and then select donut chart icon. It will generate donut chart according to page theme.
fill the field as: Legend - Market, Value- sum of sale.
Change the title to Sales by Market from visual section.
![Image description](/Images/donut_chart.PNG)

***Stack column chart***
To create slack column chart go to visual section on right visualization pan and click on slaclk column chart chart icon.
then below visualization pan, fill the details of x-axis and y-axis with customer name and profit. change the title as profit by customer name using general section on visualization pan.
following is the result:
![Image description](/Images/stack_column.PNG)

I want to show top 10 customer name so expand Filter section on right pan-->>click on customer name and expand it-->in filter type select Top N-->in show item select Top and 10 in numerical section as following:
![Image description](/Images/stack_filter.PNG).

***cluster chart making***
Least 5 profit by product name:
select cluster bar chart icon from visualization pan, fill the details in the field section below visualization pan as:
Y-axis:Product name, X-axis:profit
title: Least 5 profit by products from general section change formats of chart like colour of bars, font size and colours.Explor general section for more formatting.
 since I need least 5 profit according to product, I need filter.
 Expand filter pan on right-->click on customer name and expand it-->in filter type select Top N-->in show item select Bottom and 5 in numerical section as following:
![Image description](/Images/loss_by_product.PNG)
 drag profit from Data pan on right to By value in filter section and click apply filter.

 Top 5 profits by product name:
 select cluster bar chart icon from visualization pan, fill the details in the field section below visualization pan as:
 Y-axis:Product name, X-axis:profit
 title: Top 5 profit by products -->from general section change formats of chart like colour of bars, font size and colours.Explor general section for more formatting.
 since I need Top 5 profit according to product, I need filter.
 Expand filter pan on right-->click on customer name and expand it-->in filter type select Top N-->in show item select Top and 5 in numerical section as following:
![Image description](/Images/cluster_profit_chart.PNG)
 drag profit from Data pan on right to By value in filter section and click apply filter.

**Map creating** 
Click on map icon in visualization pan on right side.
below visualization pan, fill details of location-Region(drag and drop from Data pan on rightmost side).
![Image description](/Images/map_disabled.PNG)

It will show no map as it is disabled in my file. According to instructions appears on pop up on page enable it and then it will show global map.
![Image description](/Images/map_scratch.PNG)

Formatting map:

Fill the details in Bubble size in visual section, just below visualization pan. Drag Sales from Data pan to this Bubble size. It will show the regions on global map with bubble.
Go to Format your visual section on right side of visualization pan-->visual
* click on map setting to change the style accordingly as here in Dark,
* click on Bubble-->adjust the size.
Go to Format visual-->General-->
* click on Title to change title name and colour of text and other formats
* Effect--> change background colour,visual border and shadow

final dashboard visual:
![Image description](/Images/final_look.PNG)

Changing complete theme of dashboard:
duplicate the existing dashboard and make changes in duplicate copy.
![Image description](/Images/dashboard_2.PNG)
_____________________________________________________________________


