# Airbnb-Price-Prediction

In this project, our goal is to make a prediction of Airbnb listing prices in one of the most popular tourism and business places in the world --- New York City. The result of the prediction will provide a point of reference to the people who are preparing a NYC journey about the accommodation listing price in NYC, which could help them have a general idea about their accommodation budget.

## Data Cleaning

To start with it, we used panda libraries to help us clean up the data. First we import the ‘listings_new.csv’ file, remove all the empty and NA rows in the csv file. In order to run model effectively in the following procedures, we changed ‘f’ and ’t’ in columns ’host_is_superhost’, 'host_has_profile_pic' , ’host_identity_verified' and 'instant_bookable' to ‘0’ and ‘1’. ‘f’s were changed to 0 and ’t’s were changed to ‘1’. Whether an accommodation has a shared bathroom or not will be one of the reasons that affects the renting price, this point has to be defined in the data cleaning process. If it has a shared bathroom, respond ‘1’, otherwise, respond ‘0’. Furthermore, we changed the accommodation price into integer. Moreover, we removed outliers in data by using IQR, and we found that the upper bound price is 291.5.  Therefore, we removed the rows which have prices that exceed the upper bound (291.5) interval. Finally, we categorized ‘room type’ and ‘neighbourhood’ into numbers and converted price to log price as the label which is what we are trying to predict in the later machine learning section. 

## Data Visualization

We continued our project with Data Visualization. In this part, we made 10 graphs to serve our goal in order to show the relationship between Airbnb price and factors that we have in our data. First of all, we made counts of Airbnb in neighborhoods with room type categories which include four different room types, they are entire home/apt, private room, shared room, and hotel room. We believe in most cases, room types affect the price of Airbnb in the largest proportion. The second graph is density and distribution of prices for each neighborhood group, which will show the relationship between price and room types clearer. In the third graph, we counted for room types, which shows percentages for different room types. In the fourth graph, we made a map of the listings in the five boroughs, which will make it easier to analyze the relationship between location (Latitude and Longitude) and price. The last six graphs are six scatter diagrams to show the relationship of price versus bedrooms, review scores location, beds, review scores cleanliness, review scores rating, and bathroom which serve our goal that analyze how those factors affect price, and predict for Airbnb price by giving those information.

## Natural Language Processing

Following with NLP, there are several text variables in original dataset but we only consider two of them. We studied the ‘description’ variable for data description and ‘amenities’ variable for prediction. The core packages we used in natural language processing are nltk and re. For the ‘description’ variable, we first removed punctuations, digits and special characters, then got rid of the stopwords which don’t have practical meaning. After normalization and tokenization, we could get top 30 frequent unigrams, bigrams and trigrams. Unigrams are single words like ‘apartment’ and ‘room’. Bigrams are words in pairs with high frequency like ‘guest access’ and’ living room’. Trigrams are high frequent phrases with three words like ‘queen size bed’. For ‘amenities’ variables, we first turned the string variables to list variables. Then we did some modifications for some wrong values, such as ‘breakfas’ and ‘elevato’. Considering all the accommodation information, there are 85 different amenities and the amenities with high frequent occurrence are wifi, heating, essentials and  so on. However, what affects accommodation price level is the occurrence of infrequent amenities, so we picked six infrequent amenities (pool, baby monitor, baby bath, lake access, beach front and piano) and added them in feature variables for later classification. Specifically, if an accommodation has a piano, then we define the ‘piano’ variable as ‘1’, otherwise it would be ‘0’.

## Machine Learning 

We used scikit-learn library for our machine learning section. We split the data randomly into training and testing sets. Then we spot checked some most common algorithms including Gaussian Naive Bayes, Support Vector Machine, K-Nearest Neighbors, Decision Tree, Random Forest, Logistic regression, Linear Discriminant and Gradient Boosting and find the best model for future prediction. Once we determined the best model for our prediction, we can make predictions on the validation dataset and further evaluate our predictions. We also included a user interface to demonstrate how our model can be used as an application to provide a recommended price range for a particular airbnb listing.
For the user interface, users can use the data description file to enter their choice one by one and click the calculate button to get the recommended price range. Please check the data description file for more details.
