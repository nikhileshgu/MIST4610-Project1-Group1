# MIST4610-Project1-Group1

## Team Name and Members:
Group 1
  1. Ayush Vashishtha (https://github.com/avash1015/MIST4610-Project1-Group1)
  2. 
  3.
  4.
  5.

## Scenario Description:
Our movie rental company database demonstrates the management and business operations that include inventory, transactions, membership, customer service, and revenue generation provide a realistic way that a business runs on a day-to-day basis. It improves operational efficiency, improves the accuracy of data with up-to-date tables, and provides insight for the decision making process. The rental data tracking allows for transaction history analysis, the employee management system provides performance evaluation and productivity analysis. The customer management aspect allows us to see the activity status of customers as well as creating personalized services. 

We selected this scenario because it is not your traditional grocery store or shopping mall. It gives us a bit of a “throwback” if you will. This was one of the many options that ChatGPT gave us after prompting it to give us an idea that would meet the guidelines of this project. After coming up with an effective data model idea, we decided that this would be the best database to go with. 

## Data Model:
The data model shows a movie rental store that displays different operational data such as movies, actors, rentals, members, and employee details. 

The Movies entity is the one of the central entities as it contains the movie name, genre, language, main actor, and release date. Each of these attributes connect to the other entities and are a crucial part to the data model. This connects to the Actors entity which creates a many-to-many relationship through Actors_in_Movies which features actors in multiple movies, and movies with multiple actors. 

The Rentals (rental transactions) entity tracks all the checkouts, capturing the rental price, checkout date, return date, and associated Member and Employee that is involved in the transaction. The Members entity has details of the customer who rented the movies with their contact information, status, and membership join date. 

The movie rentals are tracked through the Movies_CheckedOut table which creates a many-to-many relationship between the Movies and Rentals entities. This ensures that a rental transaction can include multiple movies and each movie can be a part of a different rental transaction. 

Lastly, the Employees entity handles the staff members that are responsible for rental transactions. This table includes their first name, last name, and position. Each employee is linked to different rental transactions through a one-to-many relationship. This simply means that the one employee can handle multiple rentals, but each rental is processed by one employee. 

This data model shows how our movie rental business can efficiently track movie availability, customer transactions, and employee involvement to create an organized and profitable rental business. 

<img width="700" alt="Screenshot 2025-03-11 at 11 03 36 AM" src="https://github.com/user-attachments/assets/bf40f307-79b0-4c14-b7b3-603657cc967c" />


## Data Dictionary:
<img width="700" alt="Screenshot 2025-03-11 at 11 07 48 AM" src="https://github.com/user-attachments/assets/ec527fc3-66dc-4030-bf60-efec7895ae1f" />
<img width="700" alt="Screenshot 2025-03-11 at 11 10 44 AM" src="https://github.com/user-attachments/assets/965bcfe4-94f4-4cc9-8eef-0028cd2837a9" />
<img width="700" alt="Screenshot 2025-03-11 at 11 10 02 AM" src="https://github.com/user-attachments/assets/44f278d3-9229-450d-8d4d-e8257e636709" />



## Ten Queries:
Query #1- Avg Rental Price by Genre
This query provides the AVG rental price by Genre. We do this by joining our movies table to our weak entity, which is movies_checkedout, then finally joining our weak entity to rentals (rental transactions). We use group by movie genre so we can take the avg rental price of each genre.

<img width="463" alt="Screenshot 2025-03-14 at 10 13 55 AM" src="https://github.com/user-attachments/assets/8688dcfb-652c-4532-817d-d8f6b8f066a9" />

<img width="232" alt="Screenshot 2025-03-14 at 10 15 50 AM" src="https://github.com/user-attachments/assets/64a22373-6f62-4054-b718-9ae3a558c91f" />

The average rental transaction price by genre considers the frequency and price of specific  appearing in rental transactions. The manager can tailor marketing campaigns to specific genres. For example, they might want to look into why Thriller or War's average rental transaction price of a genre were higher. By analyzing the average rental transaction price by genre, the manager can fine-tune their pricing to maximize revenue. They might identify genres where they are underpricing or overpricing compared to market trends.



## Database Information:
