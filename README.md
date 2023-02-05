### Hotel Bookings Exploratory Data Analysis
## Objective

Our main objective is to uncover patterns and trends in hotel booking data and use this information to gain insights into the factors affecting hotel bookings. The primary focus is on identifying correlations between variables such as customer demographics, seasonality, pricing, and promotions, and the number of bookings. The analysis aims to provide actionable recommendations for hotel managers to optimize their pricing strategies, promotions, and inventory management, resulting in increased revenue and customer satisfaction. Furthermore, the analysis will aim to shed light on any underlying trends and patterns that can inform future decision-making and allow hotels to stay ahead of the competition. The ultimate goal of the project is to assist hotels in making informed decisions that will drive business growth and improve their bottom line.

### Dataset

We are given a hotel bookings dataset. This dataset contains booking information for a city hotel and a resort hotel. It contains the following features.

- hotel: Name of hotel ( City or Resort)
- is_canceled: Whether the booking is canceled or not (0 for no canceled and 1 for canceled)
- lead_time: time (in days) between booking transaction and actual arrival.
- arrival_date_year: Year of arrival
- arrival_date_month: month of arrival
- arrival_date_week_number: week number of arrival date.
- arrival_date_day_of_month: Day of month of arrival date
- stays_in_weekend_nights: No. of weekend nights spent in a hotel
- stays_in_week_nights: No. of weeknights spent in a hotel
- adults: No. of adults in single booking record.
- children: No. of children in single booking record.
- babies: No. of babies in single booking record. 
- meal: Type of meal chosen 
- country: Country of origin of customers (as mentioned by them)
- market_segment: What segment via booking was made and for what purpose.
- distribution_channel: Via which medium booking was made.
- is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for 
                     Yes)
- previous_cancellations: No. of previous canceled bookings.
- previous_bookings_not_canceled: No. of previous non-canceled bookings.
- reserved_room_type: Room type reserved by a customer.
- assigned_room_type: Room type assigned to the customer.
- booking_changes: No. of booking changes done by customers
- deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
- agent: Id of agent for booking
- company: Id of the company making a booking
- days_in_waiting_list: No. of days on waiting list.
- customer_type: Type of customer(Transient, Group, etc.)
- adr: Average Daily rate.
- required_car_parking_spaces: No. of car parking asked in booking
- total_of_special_requests: total no. of special request.
- reservation_status: Whether a customer has checked out or canceled,or not showed 
- reservation_status_date: Date of making reservation status.


Total number of rows in data: 119390
Total number of columns: 32


#### Data Cleaning and Feature Engineering
## (1) Removing Duplicate rows

All duplicate rows were dropped.

## (2) Handling null values
* Null values in columns company and agent were replaced by 0.
* Null values in column country were replaced by 'others'.
* Null values in column children were replaced by the mean of the column.

## (3) Converting columns to appropriate data types
* Changed data type of children, company, agent to int type.
* Changed data type of reservation_status_date to date type.

## (4) Removing outliers
* One outlier was found in the adr column. Simply dropped it.

## (5) Creating new columns
* Created new column total_stay by adding stays_in_weekend_nights+stays_in_week_nights.
* Created new column total_people by adding adults+children+babies.

#### Exploratory Data Analysis
Performed EDA and tried answering the following questions:

 Q1) Which agent makes the most no. of bookings?
 Q2) Which room type is in most demand and which room type generatesthe  highest adr?
 Q3) Which meal type isthe  most preffered meal of customers?
 Q4) What isthe  percentage of bookings in each hotel?
 Q5) Which is the most common channel for booking hotels?
 Q6) Which are the most busy months?
 Q7) From which country most of the guests are comin ?
 Q8) How long do people stay at the hotels?
 Q9)  Which hotel seems to make more revenue?
 Q10)  Which hotel hasa  higher lead time?
 Q11)  What is preferred stay length in each hotel?
 Q12)  Which hotel has higher bookings cancellation rate.
 Q13)  Which hotel hasa  high chance that its customer will return for another stay?
 Q14)  Which channel is mostly used forthe  early booking of hotels?
 Q15)  Which channel hasa  longer average waiting time?
 Q16)  Which distribution channel brings betterrevenue-generatingg deals for hotels?
 Q17)  Which significant distribution channel has the highest cancellation percentage?
 Q18) Doesa  longer waiting period or longer lead time causes the cancellation of bookings?
 Q19) Whether not getting allotted the same room type as demand is the main cause of cancellation for bookings?
 Q20) Does not alloting the  same room as demanded affect adr? 
 Q21) What is the trend of bookings within a month?
 Q22) Which types of customers mostly make bookings?


#Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:

* Bar Plot.
* Histogram.
* Scatter Plot.
* Pie Chart.
* Line Plot.
* Heatmap.
* Box Plot


## Univariate Analysis:

Performed univariate analysis and made following conclusions:

* 1.) Agent no. 9 has made most no. of bookings.
*  2.) Most demanded room type is A, but better adr generating rooms H, G and C. Hotels should increase the no. of room types A and H to maximise revenue.
* 3.) Most popular meal type is BB(Bed and Breakfast).
* 4.) Around 60% bookings are for City hotel and 40% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel.
* 5.) Guests use different channels for making bookings out of which most preferred way is TA/TO.
* 6.) July- August are the most busier and profitable months for both of hotels. 
* 7.) Most of the guests came from european countries, with highest number of guests from Portugal.
* 8.) Most common stay length is less than 4 days and generally people prefer City hotel for short stay, but for long stays, Resort Hotel is preferred.
 
## Bivariate Analysis :

We tried to answer following questions

* 1.) Overall adr of City hotel is slightly higher than Resort hotel and no. of bookings of City hotel is also higher than Resort hotel. Hence, City hotel is makes more revenue.
* 2.) City hotel has slightly higher median lead time. Also median lead time is significantly higher for both hotels, this means customers generally plan their hotel   visits way early.
* 3.) Almost 30 % of City Hotel bookings got canceled.
* 4.) Both hotels have very small percentage that customer will repeat, but Resort hotel has slightly higher repeat % than City Hotel.
* 5.) TA/TO is mostly used for planning Hotel visits well ahead of time. 
* 6.) While booking via TA/TO one may have to wait a little longer to confirm booking of rooms.
* 7.) GDS channel brings higher revenue generating deals for City hotel, in contrast to that most bookings come via TA/TO. City Hotel can work to increase outreach on GDS channels to get more higher revenue generating deals.
* 8.) TA/TO has highest booking cancellation %. Therefore, a booking via TA/TO is 30% likely to get cancelled.
* 9.) Longer lead time has no affect on cancellation of bookings.
* 10.) Not getting same room as demanded is not the case of cancellation of rooms. A significant percentage of bookings are not cancelled even after getting different room as demanded.
* 11.) Not getting same room do affects the adr, people who didn't got same room have paid a little lower adr. 
* 12.) Arrivals in hotels increases at weekends and also the avg adr tends to go up as month ends. 
* 13.)Moslty bookings are done by couples(bookings have two adults.)


## Multivariate Analysis :

* 1.)
 
 
 ### Solution to Business Objective 
 
Based on the project and outcomes, I would suggest the client as follows:

* If you thinking of opening a hotel go for city hotel since they will give you more profit.
* If you already have a hotel and want to make more profit, then summer time is the best.
* Make your hotel couple friendly since most of the bookings are made by the couples.
* Try to know from customers why are they cancelling the bookings.
* Collect feedbacks when the customers leave so as to know which part to work on.
* Have meals available of different countries since most of the bookings are from foreign * countries.
* Have professional tour agents or travel operators since most of the bookings are made by them only



### Conclusion

1) City hotels are the most preferred hotel type by the guests and we can say City hotel is the busiest hotel. Hence, City hotel seems to be making more revenue.

2) We get to know that 98.7% of the guests prefer "No deposit" type of deposit

3) Only 3.9% people revisit the hotels. Rest 96.1 % were new guests.Therefore retention rate is low.

4) We can say the peak months are : August, July, May(Summer Time).

5) Most of the customers (91.6%) do not require car parking spaces.

6) Most of the bookings were made through TA/TO (travel agents/Tour operators).

7) People generally prefer long stays on weekdays rather than weekends.

8) We see that majority of the rooms booked are couple rooms

9) Majority of the customers prefer online booking rather than offline booking.

10) Average ADR for city hotel is high as compared to resort hotels. These City hotels are generating more revenue than the resort hotels.

11) Booking cancellation rate is high for City hotels which almost 45%.

12) Average lead time for resort hotel is high.

13) Waiting time period for City hotel is high as compared to resort hotels. That means city hotels are much busier than Resort hotels.

14) Resort hotels have the most repeated guests.

15) Best stay in both the type hotel is less than 7 days.

16) Majority of the customers has got the room type they have booked.

17) City Hotel has the highest booking cancellation percentage.
