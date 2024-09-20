# Datasheet Template

Delve into the world of food delivery with the Zomato Delivery Dataset. This dataset provides a comprehensive view of delivery operations, including delivery person details, order timestamps, weather conditions, and more. Explore patterns, optimize delivery routes, and enhance customer satisfaction with insights from this dataset.

## Motivation

The data was created/collated by Saurabh Badole from Zomatos operational systems. 
The data set was created in order to try and gain insights into the predictability of delivery times based on such factors as mode of transport, weather, timeframe and distance.
The Zomato Delivery Data was sourced directly from Zomato's delivery operations, capturing real-world delivery transactions and operational parameters and was made publicily available on Kaggle.
 
## Composition

The data is made up of a single .csv file with the following 

ID: Unique identifier for each delivery.
Delivery_person_ID: Unique identifier for each delivery person.
Delivery_person_Age: Age of the delivery person.
Delivery_person_Ratings: Ratings assigned to the delivery person.
Restaurant_latitude: Latitude of the restaurant.
Restaurant_longitude: Longitude of the restaurant.
Delivery_location_latitude: Latitude of the delivery location.
Delivery_location_longitude: Longitude of the delivery location.
Order_Date: Date of the order.
Time_Ordered: Time the order was placed.
Time_Order_picked: Time the order was picked up for delivery.
Weather_conditions: Weather conditions at the time of delivery.
Road_traffic_density: Density of road traffic during delivery.
Vehicle_condition: Condition of the delivery vehicle.
Type_of_order: Type of order (e.g., dine-in, takeaway, delivery).
Type_of_vehicle: Type of vehicle used for delivery.
Multiple_deliveries: Indicator of whether multiple deliveries were made in the same trip.
Festival: Indicator of whether the delivery coincided with a festival.
City: City where the delivery took place.
Time_taken (min): Time taken for delivery in minutes.

There are 45584 rows of data in the .csv file.

The data is complete as supplied i.e. there is no known missing data and the scope of the collection is not documented on Kaggle.

There is nothing that could be considered confidential for two reasons
1. The ID's of the delivery person are unique but do not hold the persons name.
2. The data was made publicly available via Kaggle directly from Zomato.

## Collection process

The data was collected directly from Zomatos delivery operations systems.
The data set has a smaple date range within it for February, March and April of 2022.
There are no details as to whether this is a subset of data of a larger set or the data in its entirity.

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. 
- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)?

There was no apparent cleaning of the data in the data set. For processing purposes data was removed largly due to invalid entries, NaN values and logically out of range values (e.g -ve longitudinal coordinates)
 
## Uses

The dataset was created to allow for multiple purposes. 

This project is using the dataset to predict the delivery times for shipments as a direct analagus to the data I will be using from my employee but that I am not allowed to make public.

Other purposes include but certainly not limited to
1. Travel times by vehcile type for vehcile utilisation
2. Weather impact analysis
3. Distance modelling for deliveries

The nature of the data is such that it does not contain data that may be used in damaging way. There is no personal information available. There is no apparent bias for persons nationality or gender and no financial data.

The data set is defined and if the data meets the needs for the exercises required then there are no barriers to its use. As there is no bias due to the points mentioned above I would say there is no  task for which the data cannot be used.

## Distribution

The data has been distributed via Kaggle. There is no evidence that it has been made available elsewhere.
- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?
No license for use is documented in Kaggle. There are no IP notices for the data. There are no terms of use documented in Kaggle. 

## Maintenance

The data was made available on Kaggle and there are no updates to it since posting, meaning the data is unsupported and no further changes/updates will be made.


