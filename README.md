# Speed_Camera_Violations
This is a MSIS2629 Data Visualization class project on Chicago Speed Camera Violations. 

## Chicago Automated Speed Enforcement Program（ASE）
According to the [Chicago Data Portal](https://data.cityofchicago.org/Transportation/Speed-Camera-Violations/gncf-3xbx), the dataset shows the daily volume of speed violations that have occurred in Children's Safety Zones for each camera from July 1, 2014 until present minus 14 days. The recent 14 days data are not shown due to revised data submission to City of Chicago. The violations are collected by camera and radar system and are subjected to reviews by two City contractors. The data reflects an accurate view of the Automated Speed Enforcement Program violations in Children's Safety Zones. 

The Chicago Mayor Rahm Emanuel is a big advocate on pedestrian safety. He launched the Automated Speed Enforcement praogram on August 2013. The intention is to protect children and other pedestrians by reminding drviers to slow down and obey speed laws, especially in school and park zones. Quoted on [City of Chicago transportation department](https://www.chicago.gov/city/en/depts/cdot/supp_info/children_s_safetyzoneporgramautomaticspeedenforcement.html):
> The safety zone are desingated as 1/8th of a mile boundary around any Chicago parks or schools. The City ordinance establishing the Children’s Safety Zone program substantially narrows the hours and locations of automated speed enforcement that are allowed under state law, and provides for the following:

> * The enforcement hours will be limited from 7 a.m. to 7 p.m. in safety zones around schools on chool days (Monday through Friday)
>  * 7 a.m. to 4 p.m.: 20 miles per hour (mph) speed limit when children are present; and the posted speed limit when no children are present
>  * 7 a.m. to 7 p.m.: The posted speed limit
> * The enforcement hours around parks will be limited to only those hours parks are open (typically *6 a.m. to 11 p.m., 7 days a week) with a 30 mph speed limit
> * Only warnings will be issued for the first 30 days after a cameras are newly-established in a safety zone
> * The first time a vehicle owner is eligible to receive an actual ticket, they will instead receive a warning notice
> * Fines for violations are $35 for vehicles traveling 6-10 mph over the posted speed limit while in a safety zone, and $100 for vehicles traveling 11 or more mph over the posted speed limit.  
> Further, the City is capping the locations where speed cameras can be installed to 20% of the 1,500 safety zone locations allowed by state law (approximately 300). 

> Camera locations are chosen based on available data regarding traffic, speeding, and crashes.  The City has established six geographical regions wherein no fewer than 10% of speed enforcement safety zones will be located in each region.




## Visulizations and the Making-Of
[Visuliazations Tableau Link](https://public.tableau.com/profile/maria7939#!/vizhome/Version13VizforMayor/Sheet2)


![Viz 1: Violations by Weekday](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/Violations%20by%20Weekdays.png)



From the data exploration, I found that the number of violations are decreasing over the years. I decided to take a look at the daily violations overtime and found corresponding trend. The daily violation over time is quite noisy with all the dips and spikes. Therefore, I smoothed the line using the moving average and set the caluculation type to previous 7 days since we discovered a strong weekly trend in the graph above. I also added a trend line to stress the downward trend and to make the message clear: The Automated Speed Enforcement program (ASE) is a success. The speed violations in the Children's Safety Zone decrease steadily overtime. 

![Viz 2: Daily Violations Overtime](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/Daily%20Violations%20Overtime.png)



![Viz 2: Violaition Distribution across 77 Communities ](https://github.com/jymhe120/Speed_Camera_Violations/blob/master/Violation%20Distribution%20across%2077%20Communities.png)
I merged the [Census Data - Selected socioeconomic indicators in Chicago, 2008 – 2012](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)


## Future Feeatures/enhancements Roadmap


