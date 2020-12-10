# Airbnb-Price-Prediction

Data Cleaning

We used panda libraries to help us clean up the data. First we import the ‘listings_new.csv’ file, remove all the empty and NA rows in the csv file. In order to run model effectively in later work, we changed ‘f’ and ’t’ in columns ’host_is_superhost’, 'host_has_profile_pic' , ’host_identity_verified' and 'instant_bookable' to ‘0’ and ‘1’. ‘F’s were changed to 0 and ’t’s were changed to ‘1’. Whether an accommodation has a shared bathroom or not will be one of the reasons that affects the renting price, this point has to be defined in the data cleaning process. If it has a shared bathroom, respond ‘1’, otherwise, respond ‘0’. Furthermore, we changed the accommodation price into integer. Moreover, we removed outliers in data by using IQR, and we found that the upper bound price is 291.5.  Therefore, we removed the rows which have prices that exceed the upper bound (291.5) interval. Finally, in order to have normally distributed data, we added log price to column ‘price’. 

Data Visualization

For Data Visualization part, we used data after data cleaning. In this part, we made 11 graphs to serve our goal that in order to show the relationship between Airbnb price and factors that we have in our data. First of all, we made counts of Airbnb in neighborhoods with room type category which include four different room types, they are entire home/apt, private room, shared room, and hotel room. We believe in most case, room types affect price of Airbnb in largest proportion. The second graph is density and distribution of prices for each neighborhood group, which will show the relationship between price and room types clearer. In the third graph, we count for room types, which shows percentage for different room types. In fourth and fifth graph, we made a map of Airbnb. In this graph, we split New York City into five boroughs, which will make us easier to analyze the relationship between location (Latitude and Longitude) and price. For the last five graphs, we made five scatter diagrams to show the relationship of price versus bedrooms, review scores location, beds, review scores cleanliness, and review scores rating, which serve our goal that analyze how those factors affect price, and predict for Airbnb price by giving those information.
