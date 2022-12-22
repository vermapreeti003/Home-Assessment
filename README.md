# Home-Assessment
## OVERVIEW
The Toronto Parking Authority is a local Board of the City of Toronto which owns and operates the system of Municipal off-street parking lots ('Green P') and the on-street metered parking. Approximately 2.8 million parking tickets are issued annually across the City of Toronto. The Issued Parking Tickets dataset contains non-identifiable information relating to each parking ticket issued for each calendar year. The tickets are issued by Toronto Police Services (TPS) personnel as well as persons certified and authorized to issue tickets by TPS.
In this assessment, we are given different datasets related to cityofToronto parking infraction types. We are having diferent datasets as csv and geojson files.

## AIM
 The main aim is to determine the top20 infraction types most common location of city of Tronto where parkng law is voialted.
## Analysis
Using the ETL process,

Extract
 * extracted the PArking tags from 2016-2020 from Toronto open data catalogue
 * extracted green p parking data from toronto parking authority open data catalogue

Transform
 * Parking_tags

   * Using python panadas library to load and read  25 csv files.
   * using pd.concat to combine te csv files into one dataframe.
   * stored the location2 column and infraction code and infraction description for top 20 locations in        parking_top20.csv file.

 * Green P Parking
   * Used python json library to load and read json file.
   * used a for loop for collecting parking_id, address and rate and stored in the corresponding list.
   * stored address by selecting address column in a list.

Load
 * loaded both the dataframes as combined with the most common infraction types with the location2 and addresss coulmn.


## Assessment Questions
1. 	What is the most common location for each of the top 20 infraction types?

Ans: 
* I generated a jupyter notebook for this question. In that I have imported all the libraries which are required for the course.
* Combined all the csv files from the open source data of parking_tags for year 2016-2020 using glob.
* concatinated all the files to read as a single dataframe.
* Lookout for the datatypes and changed the date_of _infraction column to datetime.
* Used count to determine how many of the infraction_codes has been voilated on each location.
* Calculated the maximum of the count for each infraction type for common location.
*  Created a dataframe with the top 20 location with common infraction types.
* Saved the result as a parkimg_top20.csv file.
* With the help of google API i was trying to get the latitude and longitude of the location column to get the latitude and longitude of the address.
* To generate a map for the top 20 common location we can use marker_layer for the locations with latitude and longitude and plot the masp for each type using   gmaps library of python.

* Rather than producing a series of line charts, I wanted to give users the ability to explore the top grossing parking spots in Toronto. In my mind, one of     the most important attributes of a parking ticket is location. As a result, I chose to create a map-based visualization with other attributes, such as         infractio description and infraction type, coded by size and colour respectively.

* I chose to encode the parking spot's revenue with the circle's size. Big circles immediately pop out to viewers, which is what the visualization is intended   to do. User's can quickly identify the top grossing spots without much effort. This ensures that a location with 2x the revenue of another has a circle area   that is 2x as well. 

* Users should be able to immediately see that the bulk of the top grossing locations are in downtown Toronto, as one might expect. On top of seeing trends by   area, users can quickly find the highest grossing spots and ticket types based on the size and colour of each circle.
                       
                     

2.	Are there alternative parking options available near the common infraction locations?

Ans:
 * In this by generating a Green P Parking jupyter notebook. I was able to load and read geoJSON files for parking issue in 2019.
 * I appended the data concatenate it and upload it as dataframe.
 * In the file we are having address for differnet parking locations. changed those addresses to upper case.
 * Created a list for common address to match up with the top 20 lcation infraction types we created in the previous question. 
 * we get 33 common locations with the infraction. created a dataframe for it.
 * With the help of googlemaps API we can get the map with the closest common location of infraction. 

3.	Are there any socio-demographic trends of note in the areas with more infractions?

Ans:
 * As we can see in the neighbourhood profiles, we can see different attributes based on the demographic data.
 * If we look clearly in the dataset the characteristics shows that the private dwellings occupied by usual residents is more in the common infraction locations.
 * 25% sample data for the year 2016 shows 25561210 total mobility rate for the trends.
 * Since the evaluation of people's behaviour or cultural norms over time also one of the key factor of socio trends.
 * With the age group between 45 to 54 years holds more tickets then others above and below this age.
 * Based on these demographic trends, there are five key implications for the future:
   Continued population growth;
   Population growth driven by immigration;
   Concentration of population growth in the largest urban areas;
   Rapid increase in the number and proportion of seniors; and
   A period of slower growth among the core-age population.
 * As seen in the two graphs below data according to age group for 2016 and according to the sex which is more dominating in it. 
 
![ss2](https://user-images.githubusercontent.com/111541268/209160058-6ca1723d-a1f0-4bb2-abd2-b153f11803c8.png)



![ss3](https://user-images.githubusercontent.com/111541268/209160119-f943b985-d594-4b35-b0cf-cace924d747c.png)



https://public.tableau.com/app/profile/preeti.verma/viz/Book11_16715683182600/Dashboard1?publish=yes

### Results 
  We got the top20 common locations for the parking tags for the year 2016-2020 with "2075 Bayview Ave" as most common location with infraction type 3.0 and description "park on private property".
  

![ss1](https://user-images.githubusercontent.com/111541268/209160145-5ebb61a1-b4be-41af-8c6f-a4a93c80e352.png)



### Summary
 
 * It was a great dataset to work on as it revolve around our day to day life as we go out and look for parking in different areas of Toronto.
 * Many challenges I faced in doing the analysis which involves combining larger csv files together. Mapping with API was interesting thing i am looking forward to learn more and work more on that.
 * Its always good to analysis your mistakes and overcome them and plan to move forward for the solution.
 * We can compare fine counts with the parking capacity to avoid overcrowding and suggest other parking options for drivers.
 *	Research Green P’s new parking payment app and the potential impact it has on the number and types of fines issued.
 
 



