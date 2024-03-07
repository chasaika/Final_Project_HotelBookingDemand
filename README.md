# Final_Project_HotelBookingDemand
Hotel Booking Demand Classification Case

# Classification_Case : Hotel Booking Demand

## **Business Understanding**

**Context:**

Cancellation of reservations is a key aspect of hotel revenue management as it affects the room reservation system. Cancellations in hotel booking reservations can result in losses for the hotel in terms of hotel industry demand management decisions. There are many factors that cause reservation cancellations such as business travel schedules, holidays, adverse conditions (pandemics), and other factors. Understanding the reasons for customer reservation cancellations is an important aspect for hotels. Identifying the factors that cause reservation cancellations can help hotels address issues, improve customer satisfaction, and implement strategies to minimize cancellations. This can be done by hotels to tailor their services and offerings to meet customer expectations.

However, predicting factors for reservation cancellations poses a challenge. To reduce reservation cancellations, it would be very helpful for hotels to have a system that can predict whether a reservation will be canceled so that they can offer rooms to other customers or make other plans. In the hospitality industry, there is a standard format called Passenger Name Record (PNR) developed by the tourism and travel industry which is used for developing predictive models to classify the likelihood of hotel reservation cancellations.

**Problem Statement:**

LisGarve City & Resort Hotel is an accommodation located in Portugal. Currently, it is experiencing a decrease in revenue due to many reservation cancellations, resulting in losses for the hotel. The datasets show that the cancellation rate is approximately 37%. This impact results in significant revenue loss for the hotel, as canceled orders can reach up to 15%.

They want to know what actions should be taken by hotel management to reduce the likelihood of reservation cancellations by identifying the characteristics of the hotel. Many factors contribute to hotel cancellations, but it is difficult for hotels to track the reasons why potential customers cancel their reservations. Therefore, the hotel requires the ability to predict which potential customers are likely to cancel their hotel reservations.

source : https://revenue-hub.com/three-most-common-trends-impacting-cancellation-rates/

**Goals:**

The Data Team is trying to help the company LisGarve City & Resort Hotel reduce marketing costs or provide conditions (such as deposits or double booking) to customers who are likely to cancel hotel reservations by understanding the characteristics causing hotel reservation cancellations. This enables the marketing team to take more targeted actions. Some points that can be elaborated to identify these characteristics are:

1. How do the characteristics of the interval between booking and scheduled date, and specific times, influence the habit of canceling hotel reservations? (number of days between booking date and scheduled date, specific months)
2. How do the characteristics of hotel facilities and services affect customers in canceling hotel bookings? (type of hotel, meal packages, special facility/service requests, differences between the booked room type and available room type)
3. What are the characteristics of customers who cancel hotel reservations? (number of guests, previous cancellation frequency, customer type, previous cancellation history, deposit type, country of origin)

Based on the issues outlined, the hotel wants to understand the characteristics of customers who are likely to cancel hotel reservations based on the available features. This allows them to direct marketing efforts to customers with these characteristics, thereby reducing promotion costs. This strategy aims for good Key Performance Indicators (KPIs) and high conversion rates to avoid unfocused campaigns. The Data Team aims to create a more targeted program for potential customers with the above characteristics.

Stakeholder: LisGarve City & Resort Hotel Marketing Team

**Analytic Approach:**

The analytic approach involves several stages of the process such as comprehensive data collection, data cleaning, and data processing to obtain analysis results. With this data to obtain analysis results that will be used for decision-making, we process the data using machine learning modeling to predict prospective customers likely to cancel hotel reservations or not.

**Metric Evaluation:**
To assess the performance of a model in predicting its target, we need metric evaluation by measuring its error value. Since our main focus is to increase revenue by maximizing the model on the Positive Class while reducing losses caused by hotel bookings that are actually canceled but predicted not to be canceled (False Negative) or caused by hotel bookings that are actually not canceled but predicted to be canceled (False Positive). In this experiment, we use the following identification:

Target:

0: Not Canceled
<br>
1: Canceled
<br>
The hotel's actions based on prediction results:
Cancel: Perform double booking on transactions that are actually canceled or impose a deposit on hotel bookings, but it needs to be reviewed for the deposit as it may lead to customer loss if the deposit charged to consumers is sufficiently high.

Type I Error: False Positive (Customers who are actually not canceled but predicted to be canceled)
<br>
Consequences: Promotions for hotel bookings are not targeted, resulting in suboptimal revenue. Without incurring marketing costs, the hotel can generate full revenue from hotel bookings, leading to a revenue decrease of about 11% (4-5% for digital marketing and 6% for conventional marketing) according to the reference below. These costs also include the impact of double booking, which, according to the source below, can lead to negative reviews. Therefore, the marketing team needs to allocate funds to mitigate negative reviews due to double booking.

Type II Error: False Negative (Customers who are actually canceled but predicted not to be canceled)
<br>
Consequences: The hotel loses potential customers who cancel their bookings, resulting in revenue loss. Thus, the hotel loses revenue equivalent to the hotel booking price.

To provide a quantitative overview of the consequences, we will attempt to calculate the cost impact based on the following assumptions:
- Average hotel price per night in Portugal: 91.85 Euro
- Average hotel marketing costs
- Marketing team salaries
- Negative review impact from double booking
- Points 2-4: 11% x hotel price per night = 11% x 91.85 = 10 Euro

Based on the consequences, we will try to create a model that can focus on evaluating the Positive class, namely (Recall, Precision, F1). However, from a simple observation above, recall has a significant impact because the costs borne by the hotel will be higher (losing the opportunity cost of one room/night). Furthermore, another reason for using recall is that the value of Type II Error, which can be addressed using a deposit, may cause the hotel to lose customers because the majority of hotel customers in the dataset book without a deposit, raising concerns about chargebacks as per the source below.

However, we need to further explore the maximum business benefits, and we will try several metrics and conclude the best metric for the business as the primary metric.

source:
- https://www.bu.edu/bhr/2015/08/25/digital-marketing-budgets-for-independent-hotels-continuously-shifting-to-remain-competitive-in-the-online-world/
- https://www.orourkehospitality.com/resources/topic/hospitality-digital-marketing/4-tips-for-planning-your-2022-hospitality-marketing-budget/
- https://www.selecthub.com/hotel-management/double-booking/
- https://www.hoteliga.com/en/blog/how-to-minimize-hotel-booking-cancellations-and-chargebacks (deposit)

**Visualization**
link : https://public.tableau.com/views/HotelBookingDashboard_17078230063390/Dashboard?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link

**Presentation**
link : https://www.canva.com/design/DAF89YIzkkI/Qd7P3cFTHwAztbv5bZf1qg/edit
