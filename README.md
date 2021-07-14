# Nearest neighbour analysis of social services in Singapore

The jupyter notebook in this repository outlines the code used for doing a nearest neighbour analysis on the location of social services in Singapore.

<b> Main parts of the jupyter notebook: </b>
<ol>
	<li> Plotting of locations on a map to visualise using the folium library </li>
	<li> Geocoding using Google Maps API </li>
	<li> Nearest neighbour analysis using Shapely </li>
</ol>

<h2>1. Plotting the location of social services on Singapore for visualisation</h2>
The dataset used in this analysis is information of all social service agencies in Singapore registered under the National Council of Social Service. 
The original data is retrieved from 
<br>
ncss.gov.sg/social-service-agencies/membership/list-of-ncss-members
<br>
A geocoding was done to the location of these social services to retrieve it's geometry, which included their latitude and longitude. 
With the latitude and longitude, we can make use of the folium library to do a geospatial visualisation using the folium library

<h2>2. Geocoding the user's location</h2>
The user would input their location if they want to find out the nearest social service from their current location. We would need the latitude and longitude, hence a geocoding on the user's locaiton is necessary.
In this case, I've made use of the Google Maps Geocoding API to get the accurate latitude and longitude of the user. 
I've also plotted the user's location on the same map with the location of social service agencies for visualisation.
<br>

<h2>3. Nearest neighbour analysis using Shapely</h2>
With the latitude and longitude of social services and the user, we are ready to do the nearest neighbour analysis. We first create a unary union from Points in the social services geodataframe. 
Then, we can use the <code>nearest_points()</code> function in the Shapely library to find out the geometry of the location of the nearest social service agency.
Lastly, we locate the details of the social service agency by comparing the geometry in the social service geodataframe. 
And.. voila! We get the name (details) of the nearest social service agency from a user's location in Singapore.
