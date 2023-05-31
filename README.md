# Supply-Chain-Data-Analytics

## Problem Statement
AtliQ Mart is a growing FMCG manufacturer headquartered in Gujarat, India. It is currently operational in three cities Surat, Ahmedabad, and Vadodara. 
They want to expand to other metros/Tier 1 cities in the next 2 years.AtliQ Mart is currently facing a problem where a few key customers did not extend their annual contracts due to service issues. It is speculated that some of the essential products were either not delivered on time or not delivered in full over a continued period, which could have resulted in bad customer service. Management wants to fix this issue before expanding to other cities and requested to track the ’On time’ and ‘In Full’ delivery service level for all the customer's daily basis so that they can respond swiftly to these issues. using a standard approach to measure the service level in which they will measure ‘On-time delivery (OT) %’, ‘In-full delivery (IF) %’, and OnTime in full (OTIF) %’ of the customer orders daily basis against the target service level set for each customer.

[Live Dashboard Link](https://www.novypro.com/project/nikhil-rane-)

## Tech Stack Used
- SQL
- PowerBi Desktop
- Excel
- DAX language
## Business-related terms
 
#### Orders and Lines
Orders are nothing but unique requests placed by a customer on a given date Within an order, 
a customer could request multiple items. Each of these items requested within the order is called an order line

#### Measuring Line Fill Rate & Volume Fill Rate
Line Fill Rate is an important metric for the supply planning team to understand how many lines they shipped out of the total lines ordered. 
This metric does not consider the delivery time of the order.
Volume fill rate or case fill rate is a similar metric useful for the supply planning team to understand the total quantity they can ship for a customer per order or for a given

#### Measuring On-Time Delivery %
Unlike Line Fill Rate, this measure is measured at the order level. It determines if
an order is delivered as per the agreed time with the customer.
This metric is important for the warehouse & distribution team.
An order is On Time only when all the line items inside the order are delivered on
time.

#### Measuring In Full Delivery %
Unlike Line Fill Rate, this measure is measured at the order level. It determines if an
order is delivered in full as per the requested quantity by the customer.
This metric is important for the supply planning team.
An order is In Full only when all the line items inside the order are delivered In Full.

#### Measuring On Time In Full (OTIF) %
Unlike Line Fill Rate, this measure is measured at the order level. It determines if an
order is delivered BOTH in full and On Time as per the customer's order request.
This metric is important for all the sub-functions in the supply chain team.
An order is OTIF only when all the line items inside the order are delivered In Full
and ON Time. This is a hard metric that measures the reliability of an order from
customer's point of view.

## Dataset 

1. dim_customers.csv
2. dim_products.csv
3. dim_date
4. dim_targets_orders
5. fact_order_lines.csv
6. fact_orders_aggregate.csv

---------------------------------------------------------------------------------------------

Column Description for dim_customers:

This table contains all the information about customers

1. customer_id: Unique ID is given to each customer
2. customer_name: Name of the customer
3. city: It is the city where the customer is present

---------------------------------------------------------------------------------------------------

Column Description for dim_products:

This table contains all the information about the products

1. product_name: It is the name of the product
2. product_id: Unique ID is given to each of the products
3. category: It is the class to which the product belongs

---------------------------------------------------------------------------------------------------

Column Description for dim_date:

This table contains the dates at daily, monthly level and week numbers of the year

1. date: date at the daily level
2. mmm_yy: date at the monthly level
3. week_no: week number of the year as per the date column

---------------------------------------------------------------------------------------------------

Column Description for dim_targets_orders:

This table contains all target data at the customer level

customer_id: Unique ID that is given to each of the customers
ontime_target %: Target assigned for Ontime % for a given customer
infull_target %: Target assigned for infull % for a given customer
otif_target %:   Target assigned for otif % for a given customer

---------------------------------------------------------------------------------------------------

Column Description for fact_order_lines:

This table contains all information about orders and each item inside the orders.

1. order_id: Unique ID for each order the customer placed
2. order_placement_date: It is the date when the customer placed the order
3. customer_id: Unique ID that is given to each of the customers
4. product_id: Unique ID that is given to each of the products
5. order_qty: It is the number of products requested by the customer to be delivered
6. agreed_delivery_date: It is the date agreed between the customer and Atliq Mart to deliver the products
7. actual_delivery_date: It is the actual date Atliq Mart delivered the product to the customer
8. delivered_qty: It is the number of products that are actually delivered to the customer


---------------------------------------------------------------------------------------------------

Column Description for fact_orders_aggregate:

This table contains information about OnTime, InFull and OnTime Infull information aggregated at the order level per customer

1. order_id: Unique ID for each order the customer placed
2. customer_id: Unique ID that is given to each of the customers
3. order_placement_date: It is the date when the customer placed the order
4. on_time: '1' denotes the order is delviered on time. '0' denotes the order is not delivered on time.
5. in_full: '1' denotes the order is delviered in full quantity. '0' denotes the order is not delivered in full quantity.
6: otif:    '1' denotes the order is delviered both on time and in full quantity. '0' denotes the order is either not delivered on time or not in full quantity.


## Insights
- In June LIFR and VIFR % decreased by 0.6 and 0.08 % respectively
- None of the key measures meet the target % 
- Coolblue and Lotus mart, acclaimed stores have the highest total orders but their OT % is below30%
- Vijay store, acclaimed store, and Lotus mart are not fulfilling the quantity their IF % is below 50 % 
- Coolblue, Lotus Mart, Acclaimed stores, and Vijay store contributed 9.57 % of total OTIF % 
- Diary products have high demand 
- Elite Mart, Coolblue, Sorefoz Mart, and info stores their LIFR % is below 60 % 




