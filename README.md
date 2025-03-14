# MIST4610-Project1-Group1

## Team Name and Members:
Group 1
  1. Vashishtha, Ayush [@avash1015](https://github.com/avash1015)
  2. Challa, Amruta [@amrutac921](https://github.com/amrutac921)
  3. Machado Mota, Felipe [@FelipeMachadoMota](https://github.com/FelipeMachadoMota)
  4. Gujjula, Nikhilesh [@nikhileshgu](https://github.com/nikhileshgu)
  5. Mai, Elvis [@elviskietmai](https://github.com/elviskietmai)

 

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

The average rental transaction price by genre considers the frequency and prices of movies and their genres appearing in rental transactions. Although the store sets the prices, higher average rental transaction prices mean that more movies of that genre are being rented out more frequently and are driving more revenue. Managers would use look at this data and could see that Thriller and War genres are successful, suggesting that they are popular and are priced well. 

--

Query #2 Members who rented more movies than the avg number of rentals + their total rental transactions 

This query is focused on members and the movies they have rented. We join rentals and members through member_id.
Now, we are focusing on the higher value customers that rent out multiple movies over the course of their membership. This shows us the top members by their rental frequency in descending order. 

<img width="532" alt="Screenshot 2025-03-14 at 1 15 10 PM" src="https://github.com/user-attachments/assets/cc64fbec-f4ee-46bc-9416-38e339f7e902" />

<img width="326" alt="Screenshot 2025-03-14 at 1 15 38 PM" src="https://github.com/user-attachments/assets/3298da14-3b06-4fcc-be9f-8837fefc42a7" />


It identifies all the high value customers so we can potentially offer them special deals to encourage them to buy more. For example, we might offer Emily Johnson a special 15% off your next purchase order. 

--

Query #3- Finding who rented out movies based on a specific actor
This query finds the members who rented out movies with a specific actor in it. In this case, we specified the search to Angelina Jolie. 

<img width="335" alt="Screenshot 2025-03-14 at 1 18 47 PM" src="https://github.com/user-attachments/assets/81535eb0-9d38-4a1c-9fef-2e4949ebfb70" />

This allows us to make personalized recommendations to specific customers and show them more movies by that actor, have insight on the customer preferences of different members based on people who are attracted to purchasing movies by a specific actor, and handle inventory by making decisions that prioritize specific actors. 

--

Query #4- Movies that have been rented more than the average across all movies
This query shows us the movies that are above the average across all the movies. (the average is 4.4667)

<img width="429" alt="Screenshot 2025-03-14 at 1 21 03 PM" src="https://github.com/user-attachments/assets/4af0ea81-6b38-4f47-88e3-3f02b4197b45" />

<img width="322" alt="Screenshot 2025-03-14 at 1 21 25 PM" src="https://github.com/user-attachments/assets/061a7312-309b-4917-84f5-20b3dda9a04c" />

The main purpose of this query is to help with identifying the high-demand movies to understand how to optimize our inventory and to have higher projected growth revenue. 
Some of the insights that are provided with this query are: 
 - Top performing movies that exceed the average of all the movies combined 
 - Customer preferences of movies 
 - A benchmark for the performance of the overall catalog and which movies are bringing in more profit 

--

Query #5- Employees sorted from highest to lowest commission
This query shows the employees sorted from the highest to lowest commission which is very important to business operations. 

<img width="548" alt="Screenshot 2025-03-14 at 1 22 08 PM" src="https://github.com/user-attachments/assets/30e5d437-4cc5-4676-ac55-e77cb72011b2" />

<img width="360" alt="Screenshot 2025-03-14 at 1 22 42 PM" src="https://github.com/user-attachments/assets/8a5cd715-c428-4498-91da-ea25af94e2cc" />

It helps provide insight on the employee performance and any incentives/bonuses that we may offer. 
It also identifies key employees that contribute to top revenue generation. 

--

Query #6- Order Actors from most to least number of movies acted in
This query takes all the column from the actors table and orders the  actors in the movies based on descending order based on the actor_numMovies table. 

<img width="289" alt="Screenshot 2025-03-14 at 1 23 35 PM" src="https://github.com/user-attachments/assets/9897d139-3104-4047-b12f-8e0d2dd44b04" />

<img width="356" alt="Screenshot 2025-03-14 at 1 24 06 PM" src="https://github.com/user-attachments/assets/0f6e848f-f554-4dae-b15c-3be98824b5e3" />


This data is useful to managers for inventory. Managers would want to see if they habve many movies of a very popular actor that people would want to watch.

--

Query #7- Number of movies in Korean 
This allows us to take the number of movies in the Movie table and filter it based on the movie_language to see how many movies belong to a specific genre. 

<img width="431" alt="Screenshot 2025-03-14 at 1 36 45 PM" src="https://github.com/user-attachments/assets/ec85e7e8-3a79-4e52-89d6-fcfd0343c21b" />

Management is able to understand how diverse their movie rental selection is and can make adjustments to their inventory based on customer demand. If the count of a language is low, they can add more to attract different types of customers. 

--

Query #8- Rental Transactions from 01/01/2024 to 07/01/2024 (6 months)
By utilizing the checkout_date and rental_id from the rentals table, this filters the rental transactions from a specific period of time. 

<img width="490" alt="Screenshot 2025-03-14 at 1 37 45 PM" src="https://github.com/user-attachments/assets/215e5dfd-2f6e-4ba4-85a0-263bf8e6a0b3" />

<img width="198" alt="Screenshot 2025-03-14 at 1 38 17 PM" src="https://github.com/user-attachments/assets/c64450f2-36e5-4543-a2c6-d27f83d592e4" />

The main benefit of this query is that it allows management to forecast future revenues based on this data. This allows us to see the seasonal rental trends and see which month customers buy the most movies. It also shows which customers are more likely to rent movies during specific periods of time. 

--


Query #9- Top 5 most rented movies along with their rental count.
This query joins the movies and movies_checkedout tables, groups the results by movie_name, counts the number of times each movie appears (movies_checkedout), orders the results in descending order, and finally limits the results to the top 5 movies rented. 

<img width="542" alt="Screenshot 2025-03-14 at 1 59 39 PM" src="https://github.com/user-attachments/assets/fb6a25d8-9421-41e1-b17f-5ff867cd9c6d" />


Management can use this to effectively identify the best sellers and understand which movies are the most popular among the customers. 

--

Query #10- Total revenue generated by each employee 
The following query joins the employees and rental tables to link each transaction to the specific employee who processed it. It is grouped by the employee_id, the sums the rental price for each employee and the total revenue generated, and orders the results in descending order by the total revenue. 

<img width="619" alt="Screenshot 2025-03-14 at 2 00 38 PM" src="https://github.com/user-attachments/assets/31222469-d301-4d90-a73d-838bc03307d4" />


This helps with identifying the top performing employee which can lead to offering incentives and bonuses. This will also motivate the underperforming employees to do better. 

--

## Database Information:

<img width="604" alt="Screenshot 2025-03-14 at 2 01 22 PM" src="https://github.com/user-attachments/assets/0e69b8bc-735d-4878-ad28-e75f7290a59f" />

