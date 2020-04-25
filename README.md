# HelpMeDoc
An Android application that enables users to search the most nearby doctor and sends an intimation to the doctor about the current state of emergency.
HELP-ME DOC APP
 
 
Abstract-  
In the current scenario of patient emergency, many applications of patient health monitoring and appointment scheduling has been developed but many times in the wake of emergency, people tend to blank out or are unaware of nearby emergency services, so we have designed an application that enables users to search the most nearby doctor and sends an intimation to the doctor about the current state of emergency.
 
Introduction-
 
Motivation (Need of project)-
 
Nowadays, there are many inventions of technology, websites and mobile applications        that are developed to solve real-life problems people we have once faced.
There are a very few mobile apps available to help the needy in case of emergencies, panic situations and accidents.
The process of ﬁnding a Doctor in case of emergency   is not easy as it is not always necessary to find the Doctor  
The consequences will be time-consuming and a waste of money if they had to drive all away to the wrong hospital. 
Also there are no existing provisions that help us with what and who exactly we need at the time of medical emergencies.
That is the idea to create a mobile application for ﬁnding a doctor in case of emergency.
This can improve the efficiency of the existing systems with respect to assigning Doctors and managing medical emergencies.
 
 
 
 
 
 
 
 
 
 
 
 
Problem definition-
 
Here, we have created a mobile application for ﬁnding a nearest Doctor.
Also, if the user is in any kind of emergency like accident, cardiac arrest, shock, etc., the user/any other person nearby can use this  app to connect with the Doctor and provide the doctor the user's current location. 
As soon as the user reports a casualty, a  Doctor within a nearby radius will be scanned.
As soon as scanning completes the route is established.
The nearest Doctor as soon as he logs in the app, will  be notified about the emergency and patient’s location(route) and can reach the spot  as soon as possible.
 
Scope-
 
The scope for the development of this mobile application is focusing on helping the normal as well as handicapped people to get instant medical remedies, such as immediate search for the nearest Doctor.
 
Features/Benefits-
 
Instant medical help in a few clicks.
Saves time.
More efficient than traditional systems.
Helps Doctor to reach the patient with a real time route.
 
Objectives-
 
To provide instant medical facilities to the patient.
To save time for both Patient and Doctor.
To improve existing provisions of medical services.
To save as many lives as possible.
 
 
 
 
 
 
 
Implementation
System Architecture
 

 
 

 
 
 
The above designed architecture shows that the doctor and the patient login on the application during initial setup.
Whenever a user requests help, the application searches for nearby doctors using the radius++1 logic and as soon as the doctor receives the request, he/she will accept it and the till, the patient is brought down to the doctor, the preparations are made and the history of the patient is verified by the doctor.
 
 
APIs used  (and Hardware Requirements if any)
 
Two APIs have been used for this app which are:
Google Direction API
Maps SDK for Android
 
		Google Direction API
This project allows you to calculate the direction between two locations and display the route on a Google Map using the Google Directions API.
 		Sample snippet for router function
Routing routing = new Routing.Builder()
                    .travelMode(/* Travel Mode */)
                    .withListener(/* Listener that delivers routing results.*/)
                    .waypoints(/*waypoints*/)
                    .key(/*api key for quota management*/)
                    .build();
    	routing.execute();
There are many parameters in the routing function, some of them are defined below:
 
mode (defaults to driving) — Specifies the mode of transport to use when calculating directions. Valid values and other request details are specified in Travel Modes.
 
waypoints — Specifies an array of intermediate locations to include along the route between the origin and destination points as pass through or stopover locations. Waypoints alter a route by directing it through the specified location(s). The API supports waypoints for these travel modes: driving, walking and bicycling; not transit. You can specify waypoints using the following values:
Latitude/longitude coordinates (lat/lng): an explicit value pair. (-34.92788%2C138.60008 comma, no space)
Place ID: The unique value specific to a location. This value is only available only if the request includes an API key or Google Maps Platform Premium Plan client ID (ChIJGwVKWe5w44kRcr4b9E25-Go.
Address string (Charlestown, Boston,MA)
Encoded polyline that can be specified by a set of any of the above. (enc:lexeF{~wsZejrPjtye@:)
 
alternatives — If set to true, specifies that the Directions service may provide more than one route alternative in the response. Note that providing route alternatives may increase the response time from the server. This is only available for requests without intermediate waypoints.
 
avoid — Indicates that the calculated route(s) should avoid the indicated features. This parameter supports the following arguments:
tolls indicates that the calculated route should avoid toll roads/bridges.
highways indicates that the calculated route should avoid highways.
ferries indicates that the calculated route should avoid ferries.
indoor indicates that the calculated route should avoid indoor steps for walking and transit directions. Only requests that include an API key or a Google Maps Platform Premium Plan client ID will receive indoor steps by default.
Travel Modes
When you calculate directions, you may specify the transportation mode to use. By default, directions are calculated as driving directions. The following travel modes are supported:
driving (default) indicates standard driving directions using the road network.
walking requests walking directions via pedestrian paths & sidewalks (where available).
bicycling requests bicycling directions via bicycle paths & preferred streets (where available).
transit requests directions via public transit routes (where available). If you set the mode to transit, you can optionally specify either a departure_time or an arrival_time. If neither time is specified, the departure_time defaults to now (that is, the departure time defaults to the current time). You can also optionally include a transit_mode and/or a transit_routing_preference.
 
You access the Directions API through an HTTP interface, with requests constructed as a URL string, using text strings or latitude/longitude coordinates to identify the locations, along with your API key.
The Directions API is a service that calculates directions between locations using an HTTP request.
This video illustrates the use of the Directions API to help people find their way. The video includes advice on proxying the web service via your server when you're using the API in a mobile app, to protect your API key.
With the Directions API, you can:
●    Search for directions for several modes of transportation, including transit, driving, walking or cycling.
●    Return multi-part directions using a series of waypoints.
●     Specify origins, destinations, and waypoints as text strings (e.g. "Chicago, IL" or "Darwin, NT, Australia"), or as latitude/longitude coordinates, or as place IDs.
The API returns the most efficient routes when calculating directions. Travel time is the primary factor optimized, but the API may also take into account other factors such as distance, number of turns and many more when deciding which route is the most efficient.
Maps SDK for Android
With the Maps SDK for Android, you can add maps based on Google Maps data to your application. The API automatically handles access to Google Maps servers, data downloading, map display, and response to map gestures. You can also use API calls to add markers, polygons, and overlays to a basic map, and to change the user's view of a particular map area. These objects provide additional information for map locations, and allow user interaction with the map. The API allows you to add these graphics to a map:
Icons anchored to specific positions on the map (Markers).
Sets of line segments (Polylines).
Enclosed segments (Polygons).
Bitmap graphics anchored to specific positions on the map (Ground Overlays).
Sets of images which are displayed on top of the base map tiles (Tile Overlays).
 
Zoom Levels
The initial resolution at which to display the map is set by the zoom property, where zoom 0 corresponds to a map of the Earth fully zoomed out, and larger zoom levels zoom in at a higher resolution. Specify zoom level as an integer.
zoom: 8
Offering a map of the entire Earth as a single image would either require an immense map, or a small map with very low resolution. As a result, map images within Google Maps and the Maps JavaScript API are broken up into map "tiles" and "zoom levels." At low zoom levels, a small set of map tiles covers a wide area; at higher zoom levels, the tiles are of higher resolution and cover a smaller area. The following list shows the approximate level of detail you can expect to see at each zoom level:
1: World
5: Landmass/continent
10: City
15: Streets
20: Buildings
 
Working with Screenshots
 
Home Screen
 
			
Users role:
 
Login Screen
This is the login page where a user can only login if he/she has already been registered and fills in the correct credentials.
				
 
User’s Home screen
After successful login, the user is asked to give permission to access its current location. After providing the location, the user is located on the map.
 
			
 
 
User’s Profile Screen
A user has to enter his/her contact no, so the doctor can contact a user whenever required.
 
			
Locating the doctor
Here the doctor is searched and the nearest doctor is connected and details of the doctor appear on the users screen.
 
			
	
Doctors role:
 
Login Screen
This is the login page where a doctor can only login if he/she has already been registered and fills in the correct credentials.
 
			
 
Users Home screen
After successful login, a doctor is asked to give permission to access its current location. After providing the location, the doctor is located on the map.
						
 
Doctor’s Profile Screen
A doctor has to enter his/her contact no, so the user can contact a doctor whenever required.
	
					
 
 
Route to the user
Here the doctor is assigned with a patient and a complete route from doctor(source) to the user/patient(destination) along with its duration is displayed on the doctor's screen.
	
					
 
Result
 
 
 
 
 
 
 
 
 
 
 
Conclusion-
 
This application was initially developed and tested in Mumbai.
 
We have focused on helping the normal as well handicaped people with the aim of cutting down the time required to receive medical emergencies and saving as many lives as possible.
 
This application is easily accessible by the person in need or someone nearby who can help someone else.
 
It saves time and money both regarding medical treatment.
 
We have created this application with the help of the following-
 
Operating System- Windows.
 
Development Platform- Android Studio.
 
API’s used- Google Maps API.
 
Languages used- Java, Android UI, PHP for backend.
 
Server used- Xampp Server, Firebase.
 
Database used- Firebase.
 
 
References-
 
https://youtu.be/roDz8mMvbIg - Title- How to download and install android studio - 
Channel- Android Developer
 
https://youtu.be/DnpZ8FYfals -Title- Overview: How an Android Application works - 
Channel- Android Developer
 
https://youtu.be/EB0U7HcBVh8 - Title- Create user interface with java :How to develop interface of android application - Channel- Android Developer
 
https://youtu.be/DAcqmiPcXds - Title- Understanding Grid Layout in android studio - Channel- Android Developer
 
https://www.youtube.com/playlist?list=PLknSwrodgQ72X4sKpzf5vT8kY80HKcUSe - Title-The complete Android Application Development Course- Channel- Android Developer
 
Title- Head First Android Development: A Brain-Friendly Guide -
Book by- DAVID GRIFFITHS and Dawn Griffiths
 
 
 
 
Appendix:
 
User Manual 
 
 
1.0 General Information
General Information section explains in general terms the e-CHARAK application overview and the sections of the user manual. 
 
1.1 Application Overview
“e- CHARAK ” - e-Channel for Herbs, Aromatic, Raw material And Knowledge is a platform to enable information exchange between various stakeholders involved in the medicinal plants sector.
 
e-Charak has been jointly developed by the National Medicinal Plants Board (NMPB), Ministry of AYUSH, Government of India and Centre for Development of Advanced Computing (C-DAC).
 
1.2 Organization of the Manual
The user manual consists of the following four sections
1. General information
2. System Summary 
3. How to download the application 
4. Guest User - Privileges
5. Registered User - Privileges
 
General Information section explains in general terms the e-CHARAK application overview and the sections of the user manual. 
 
System Summary section explains about the hardware and software requirements for accessing e-CHARAK application and user access levels. 
 
How to download the application section explains the options available to download the e-CHARAK Android application on your mobile.
 
Using the Application section provides a detailed description of the functionalities of the e-CHARAK application 
 
2.0 System Summary
System Summary section explains about the hardware and software requirements for accessing e-CHARAK application and user access levels. 
 
3
 
 
 
 
2.1 Hardware and Software Requirements
Requires a smart phone with Android operating system (OS)
The minimum Android version should be 4.0.3 and up to avail all the features in the application. 
To download and use the functionalities of e-CHARAK mobile app, you require an Internet connection in your mobile.
 
2.2 User Access Levels
There are two types of roles in e-CHARAK application. 
1. Guest User
2. Registered User
 
1. Guest User
Guest user is one who access and uses the e-CHARAK application without registering in the application. 
 
2. Registered User
Registered user is one who registers himself/herself in the e-CHARAK application by filling the registration form. Registered user can post items, receive alerts from prospective buyers / sellers, communicate with members, etc.
 
 
4
 
 
 
 
3.0 How to download the application e-CHARAK application can be downloaded through the following ways
 Google Play Store
 e-CHARAK web Portal (www.e-charak.in )
 
3.1 Google Play Store
Open Play Store application on your mobile by clicking on
the Play Store icon as shown in the image below.
 
 
Click on the Google Play text at the top and enter the text "e-Charak" in the search bar. Click on the e-Charak application icon from the search result. Now below page will open which asks to install the application. Click on the "INSTALL" button to install the application. 
 
 
 
 
Programmers guide


