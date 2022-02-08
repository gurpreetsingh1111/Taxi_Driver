# Taxi_Driver
Project to find fraudulent taxi routes in GPS trajectories from Shenzhen, China.

We evaluated routes between the North train station and the airport in both directions.



Additionally, we evaluated routes between the west railway station and the North train station in both directions.



Problem Discription
Due to many taxi cabs now having an embedded Global Positioning System (GPS) we can collect massive amounts of taxi trajectories throughout urban environments. These GPS records provide an opportunity for us to uncover taxi driving fraud events. In this paper we describe a method of detecting anomalous taxi trajectories. Sometimes taxi drivers can purposefully take longer routes to the destination in an attempt to get a higher fare. This can be a problem for the passengers who are forced to pay higher fares as well as the taxi company who might lose customers to competitors if such fleecing is discovered.

Sample Data
Due to the sensitive nature of GPS data only a sample of GPS traces can be provided. The data comes from taxis operating in Shenzhen, China. For our project we focused on trajectories between the airport and train station. Our hypothesis was that tourists are the most likely victims of taxi fraud so we focused on areas likely to be visited by tourists.

Process
Create GPS traces that map the routes recommended by Google Maps








Filter GPS trajectories by longitude and latitude so that only routes between the aiport and train station or north and west train stations are left. You'll also have to worry about routes that have infrequent readings because it makes reconstructing their true route impossible.

Graph those routes using Matplotlib and compare them to Google Maps routes. All airport to train station routes All train to train routes

Sample:



Create a baseline method to evaluate fraud. Our baseline method labeled routes that had above average time and distance as fraud. Our method was limited by the amount of data we had so we couldn't determine if these anamolous trajectories were the result of things such as traffic. Additionally, we weren't able to access historical data to determine if the driver is familiar with that area.
-Airport to train station routes vs Google maps:





-Train to train station routes vs Google maps:





-Sample fraud based on baseline method (above average time and distance)





Map GPS trajectories to cells based on their coordinates. This turns a trajectory into a series of cells that were visted. We then compared how similar every trajectories cell path was to the cell path of a Google Maps route. If less than 80% of the cells were the same we labeled that route fraudulent.
