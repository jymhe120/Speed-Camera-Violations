# Speed_Camera_Violations
This is a revised version of MSIS2629 Data Visualization class project on Chicago Speed Camera Violations. 

## Chicago Automated Speed Enforcement Program（ASE）
According to the [Chicago Data Portal](https://data.cityofchicago.org/Transportation/Speed-Camera-Violations/gncf-3xbx), the dataset shows the daily volume of speed violations that have occurred in Children's Safety Zones for each camera from July 1, 2014, until present minus 14 days. The recent 14 days data are not shown due to revised data submission to the City of Chicago. The violations are collected by camera and radar system and are subjected to reviews by two City contractors. The data reflects an accurate view of the Automated Speed Enforcement Program violations in Children's Safety Zones. 

The Chicago Mayor Rahm Emanuel is a big advocate on pedestrian safety. He launched the Automated Speed Enforcement program in August 2013. The intention is to protect children and other pedestrians by reminding drivers to slow down and obey speed laws, especially in school and park zones. Quoted in [City of Chicago transportation department](https://www.chicago.gov/city/en/depts/cdot/supp_info/children_s_safetyzoneporgramautomaticspeedenforcement.html):
> The safety zone is designated as 1/8th of a mile boundary around any Chicago parks or schools. The City ordinance establishing the Children’s Safety Zone program substantially narrows the hours and locations of automated speed enforcement that are allowed under state law, and provides for the following:

> * The enforcement hours will be limited from 7 a.m. to 7 p.m. in safety zones around schools on school days (Monday through Friday)
>  * 7 a.m. to 4 p.m.: 20 miles per hour (mph) speed limit when children are present; and the posted speed limit when no children are present
>  * 7 a.m. to 7 p.m.: The posted speed limit
> * The enforcement hours around parks will be limited to only those hours parks are open (typically *6 a.m. to 11 p.m., 7 days a week) with a 30 mph speed limit
> * Only warnings will be issued for the first 30 days after cameras are newly-established in a safety zone
> * The first time a vehicle owner is eligible to receive an actual ticket, they will instead receive a warning notice
> * Fines for violations are $35 for vehicles traveling 6-10 mph over the posted speed limit while in a safety zone, and $100 for vehicles traveling 11 or more mph over the posted speed limit.  
> Further, the City is capping the locations where speed cameras can be installed to 20% of the 1,500 safety zone locations allowed by state law (approximately 300). 

> Camera locations are chosen based on available data regarding traffic, speeding, and crashes.  The City has established six geographical regions wherein no fewer than 10% of speed enforcement safety zones will be located in each region.





## Enhanced Visualizations and the Making-Of
### [Visualization Tableau Link](https://public.tableau.com/profile/maria7939#!/vizhome/FinalVersion3VizforMayor/Dshbd-VioDistributiondailyweekofdaycommunities)


After having a thorough understanding of the dataset and the ASE program, I started my visualization by playing with different intervals of time and examined the violations overtime by year, by month, and by day of the week. I found the violation by day of the week quite interesting. It looks like a smile curve with high ends on the weekend and a dip on the weekdays. 

The [original graph](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/Violations%20by%20Day%20of%20Week.png) was a bit too large and not very efficient at displaying the trend. Therefore, I enhanced the changing the y-axis variable to an average number of violations per camera to eliminate the effect of additional camera on the number of speed violations. After adding an average line of all the speed violations per camera per day, I set the average line as the x-axis. To do so, I subtracted the average number from the average number of violations per camera per day and got positive and negative numbers on both sides of y-axis. The negative numbers might confuse the audience, so I eliminated the gridlines and the major markers for the y-axis and added labels for each day of the week. Since the average line is the axis, so the audience can now directly interpret the bar above the axis as violation day above average and below as violation day below average. I also added a short text below the title explaining what the x-axis means.

I suspect that the speed violations jump on weekends and dip on weekdays because people assume that speed cameras are not turned on on the weekend. In fact, the speed cameras are in operation in the park zone 7 days a week during the park's opening hours. I suggest Mayor Emanuel raise the safety awareness of the drivers by adding signage and raising weekend fines as there are more kids out playing on the weekends than on the weekdays. 

![Viz 1: Violations by day of week](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/P_Spd%20vio%20by%20day%20of%20wk.png)


From data exploration, I found that the number of violations is decreasing over the years. I decided to take a look at the daily violations of overtime and found a similar trend. The daily violation over time is quite noisy with all the dips and spikes. Therefore, I smoothed the line using the moving average and set the calculation type to the previous 7 days since we discovered a robust weekly trend in the graph above. I also added a trend line to stress the downward trend and to make the message clear: The Automated Speed Enforcement program (ASE) is a success and should be continued. The speed violations in the Children's Safety Zone decrease steadily over time. 

The [original image](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/Daily%20Violations%20Overtime.png) was clear. However, I found the daily spikes and dips are quite noisy for the audience to care. I took a second look at all the dips and found all of them are in the middle of October and April next year, which signifies seasonality. Therefore, I changed y-axis to the average number of violations per camera and x-axis to the month of violation date and confirmed my finding. The violations increase in summer and decrease in winter. The downward trendline shows the speed violations decrease over time. To make this message more clear for the viewer, I turned up the opacity of the solid line so that the trendline is more obvious. I also labeled the spikes and dips months. April 2019 was filtered because the calendar month was not complete. With the date range slider, the audience has the freedom to play with the data. 

![Viz 2: Daily Violations Overtime](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/P_spd%20vio%20overtime.png)


After confirming the success of the ASE program, I would like to offer some suggestions to improve the program. I merged the [Census Data - Selected socioeconomic indicators in Chicago, 2008 – 2012](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2) dataset with the current one using community area number and community areas as keys. I was able to plot the number of speed violations on a map showing the median income per capita of each community area. The color indicates the income level of the area and the size of the circle suggests the scale of speed violations. It seems that most of the violations take place in Chicago's low-income communities. This is potentially problematic as a low-income household cannot afford to pay the fine and thus cause adverse publicity for the mayor. I advise Mayor Emanuel to allow budget plan or installment for the violators and to offer appeals for first-time violators.

I am not satisfied with the [original visualization](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/Violation%20distribution%20across%2077%20communities%20.png) as it was too cluttered and not clear where were the speed violations took place. After exploring the map feature of Tableau, I added the base, land cover, street and highway and the US Household Median Income data layer to the graph. I organized the Median household income data layer by zip code and took out the median per capita field from the merged dataset so that similar information was not displayed twice. I changed the legend title from violations to total violations. Again, I tuned down the background layer of the map to make the blue circles of total violations pop. The graph now is more aesthetically pleasing to the eye. With the street layer, I also discovered that all the violations are close to the major highways. Hence, I suggest Mayor Emanuel add speed bumps and signages near those communities to remind drivers to slow down. 

![Viz 3: Violation Distribution across 77 Communities ](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/P_Spd%20vio%20distribution%20across%2077%20communities.png)


