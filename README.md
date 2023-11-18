![alt text](https://github.com/GMT-352/midterm-project---ecosnap-api-eslemsahin/blob/main/readme%20images/Ads%C4%B1z.png)

# GMT352 / GEOGRAPHIC INFORMATION SYSTEMS

## 21967756 ESLEM ŞAHİN

# FINAL PROJECT, SPRING 2022/23 

------

## Part 1 : Update of The Database / Demonstration of a New Road 

- **Frontend**: React , **Backend**: Node.js , **Database**: PostgreSQL , **Software**: QGIS

This part includes the addition of road data to create the route where the distance between Hacettepe University Tunçalp Özgen Congress Center and Faculty of Sports Sciences will be shown in the shortest way by updating the database via the " Harita Hacettepe " project.

------

The steps of obtaining this data are listed below.

- First, open source data of the Map Hacettepe project is obtained.
This is available from the github page   
([Reference][1] ). 

- Then, the source of the data is imported by creating a database named "hacettepecampus" from PostgreSql.

- There are 6 table data in Postgresql and the data of the node and road tables are needed for route formation.

- To use these tables in QGIS software, a connection is created with Postgresql.

<img src="./Update of the database/Postgis_conection.jpeg" alt="alt yazý" width= "300" >  |  <img src="./Update of the database/connection2.png" alt="alt yazý" width= "228" > 

- In the created link, Open Street Map, node and rode data are opened as a layer.

<img src="./Update of the database/Postgresql_and_qgis_layer_data.jpeg" alt="alt yazý" width= "700" > 

- By looking at the added nodes and lines, the missing road data is scanned and it is seen that the road connection between the congress center and sports sciences is missing and the map is not in Hacettepe.

<img src="./Update of the database/New_path_areas_for_update.jpeg" alt="alt yazý" width= "500" > 

- In order to obtain this path without data, firstly, a new path route is obtained by snapping ("You can see the "snapping_tool.png" in the files.) the starting and ending nodes and drawing a line with the snapping feature of QGIS, which captures and connects the points at the connect of nodes and lines.

<img src="./Update of the database/new_roads_snapping.jpeg" alt="alt yazý" width= "460" > 

- An id is determined for this obtained route, necessary features such as start and end nodes, road type, road name, distance are defined and saved in the database for updating.

<img src="./Update of the database/data_output.jpg" alt="alt yazý" width= "730" > 

- Then, a query is performed to check whether the new path has been added to the updated database.

  * This query finds a row with a value of '678' in the 'id' column in the 'beytepe_roads_rev2' table and sorts the results in ascending or descending order by the 'gid' column.

```
select * from public.beytepe_roads_rev2
where id = '678'
order by gid asc

```

<img src="./Update of the database/Path_control_query.jpeg" alt="alt yazý" width= "730" > 


- The table information of the added data is output to the screen.


<img src="./Update of the database/Data_updates_control.jpeg" alt="alt yazý" width= "720" > 

- Then, in order for the updated and added road data to create a route on the map hacettepe, access to the server and website is provided from the terminal in Visual Studio Code, and the new database is loaded with "npm install" and the website is called with the "npm run start" command.

- Finally, the usability of the added route is checked.

- Below you can see the route before the new road data was added and the new route after it was added.

### **Before New Route** 

<img src="./Update of the database/Distance_from_congress_and_sports_sciences.jpeg" alt="alt yazý" width= "700" > 

### **After New Route** 

<img src="./Update of the database/Update_new_roads_after.jpg" alt="alt yazý" width= "700" > 

- In addition, the road route between Sports Sciences and the Tunçalp Özgen Congress Center will present the same route, since the road data is determined as bidirectional while recording.

<img src="./Update of the database/New_roads_update_2.jpeg" alt="alt yazý" width= "700" > 


## Part 2 : Smart Campus / City 

### **Article Research** 

* Essay : **An IoT Raspberry Pi-based parking management system for smart campus**  ( [Article][2] )

  ** Author : Waheb A. Jabbar, Chong Wen Wei, Nur Atiqah Ainaa M. Azmi, Nur Aiman Haironnazli

  ** State : Faculty of Electrical and Electronics Engineering Technology, Universiti Malaysia Pahang, 26600 Pekan, Pahang, Malaysia

  ** Release Date : Received 17 September 2020, Revised 12 February 2021, Accepted 5 March 2021, Available online 31 March 2021, Version of Record 13 April 2021.


Smart parking systems are a smart solution developed to solve the parking problem in cities, increase usage, reduce costs and alleviate traffic congestion. As vehicular traffic on university campuses increases, parking spaces fill up more frequently, making it a daily challenge for students and staff. Drivers are late for work or lessons because it takes time and energy to find an empty parking space. This causes a waste of time and energy. In this context, an IoT-based parking management system will be able to provide effective parking management in smart campuses by integrating with devices such as Raspberry Pi in accordance with the features and infrastructure of the university campus. Locating parking spaces on the university campus in real time provides convenience for staff, students, administration and visitors, while also helping to save time, reduce pollution and use resources efficiently. Using IoT networks, data about campus parking areas are shared over the internet, providing support to drivers and security management. Also, multiple sensors should be used in this project for parking monitoring and these sensors should be combined for different metrics such as distance, coordinates and visibility. In this context, three different types of sensors such as ultrasonic sensors, GPS and Raspberry Pi camera are available options to provide additional system functionality for video streaming.
Throughout this study, an IoT Raspberry Pi-based parking lot management system (IoT-PiPMS) for smart campus or similar environments was developed as a solution to monitor and manage parking garage spaces in real time. The use of ultrasound sensor and Raspberry Pi Camera in the proposed system increases the detection accuracy and provides the simplicity of the microcontroller system. It also makes it easy to find a parking spot, thanks to its Wi-Fi coverage and GPS support. Also in this project, three algorithms are developed that collect the necessary measurements from the sensors to detect the occupancy of the parking spaces.
As a result, Raspberry Pi 4 B+ based IoT based smart parking system project is designed using ultrasonic sensors, Pi camera, GPS module, LEDs and Blynk IoT platform. The system has been tested and successfully used in a smart campus environment or similar open parking lots. The use of multiple sensors enabled the vehicle presence to be detected reliably and made it easy to follow through a user-friendly GUI interface for the staff/students/visitors parking lot.


### **Maps for Article Research**

- Since there is no open access to the data source used for trial purposes in the article, the information about the parking areas within the scope of the smart campus was studied and mapped on the Beytepe Campus of Hacettepe University.

  * The content of the map; Information is obtained in the form of staff-student separation of parking areas, parking areas that provide GPS data, and areas that do not.
   * The purpose of this map has been created so that people who are on the Beytepe campus and looking for a place for a car park do not have car parking problems.
   * The occupancy and emptiness of the parking area, which is found according to the GPS data, is followed in advance.
   * In case of seeing or noticing a occupied parking lot, you can examine the nearest parking area and save time and practicality.
   * The user performs the parking operation by examining the closest common area to the workplace or the private areas reserved for him/her.

<img src="./smart campus map/Smart Campus Maps.png" alt="alt yazý" width= "770" >


[1]: https://github.com/banbar/harita.hacettepe.edu.tr
[2]: https://www.sciencedirect.com/science/article/abs/pii/S2542660521000317
