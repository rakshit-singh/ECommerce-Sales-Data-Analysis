# ECommerce-Sales-Data-Analysis
Analysis of ECommerce company's data to understand user patterns, enhance customer acquisition, retention, and revenue optimization. The analysis conducted helps understand key business trends and improve decision-making as well as give data-driven answers to key business questions.
We will be performing a comprehensive EDA and analysing the dataset to answer the business questions. These answers will in turn enable the company to understand key business, improve decision making, drive up revenue and increase the customer acquisition and retention.

### **Dataset Description:**<br/>
The dataset contains data from 1 Jan 2019 to 31 December 2019, i.e., for the year 2019.
The data is divided into five different files:
**Online_Sales.csv**<br/>
**Customers_Data.csv**<br/>
**Discount_Coupon.csv**<br/>
**Marketing_Spend.csv**<br/>
**Tax_Amount.csv**<br/>

Below you can find a brief description along with the major keys and what is the meaning of those keys for the data contained in each file:
The datasets below have been provided.</br>

**Online_Sales.csv**: This file contains actual orders data (point of Sales data) at the transaction level with the following variables.</br>
**CustomerID**: Customer unique ID</br>
**Transaction_ID**: Transaction Unique ID</br>
**Transaction_Date**: Date of Transaction</br>
**Product_SKU**: SKU ID – Unique Id for product</br>
**Product_Description**: Product Description</br>
**Product_Cateogry**: Product Category</br>
**Quantit**y: Number of items ordered</br>
**Avg_Price**: Price per one quantity</br>
**Delivery_Charges**: Charges for delivery</br>
**Coupon_Status**: Any discount coupon applied</br>

**Customers_Data.csv**: This file contains customer’s demographics.</br>
**CustomerID**: Customer Unique ID</br>
**Gender**: Gender of the customer</br>
**Location**: Location of Customer</br>
**Tenure_Month**s: Tenure in Months</br>

**Discount_Coupon.csv**: Discount coupons have been given for different categories in different
months</br>
**Month**: Discount coupon applied in that month</br>
**Product_Category**: Product category</br>
**Coupon_Code**: Coupon Code for the given Category and the given month</br>
**Discount_pct**: Discount Percentage for the given coupon</br>

**Marketing_Spend.csv**: Marketing spend on both offline & online channels on day day-wise.</br>
**Date**: Date</br>
**Offline_Spend**: Marketing spend on offline channels like TV, Radio, NewsPapers, hoardings, etc.</br>
**Online_Spend**: Marketing spend on online channels like Google keywords, Facebook, etc.</br>

**Tax_Amount.csv**: GST Details for given category</br>
**Product_Category**: Product Category</br>
**GST**: Percentage of GST</br>

The same data can be found in the file Dataset Description.pdf in the github repository.</br>
The jupiter notebook containing the code is in the github repository as well. This can be referred to for the code related part of the analysis.</br>


### **EDA:**
We will now proceed with the analysis of each of these datasets, clean the datasets wherever required and engineer new features as per the results of the analysis.  
The steps followed will include:  
1. Analyse each of the individual datasets. Analyse all the columns present, the types of the values contained in those columns. We will also be checking for data corruption or the presence of null values.  
2. Deal with null or missing values in the dataset if any.  
3. Convert the types of columns to the required types so as to make it easier to perform operations on these columns.  
4. Identify the keys in each dataset that can be used to merge the individual datasets into one comprehensive data frame. This will help us do a more comprehensive analysis on the data and see how different variables are related to each other. For example: combining the sales and the tax data will help us see how the tax on the products affects the sales and the spendings.  

There are no null values in any of the provided datasets, so no explicit handling is required for the null values.

**Next Step** is to convert the columns of the data into a standard format. Do data type conversions wherever required and convert all the column names to lowercase. The logic for the same can be found in the hupyter notebook under the section **Data Conversion and standardisation**. 

Now the final step of the EDA is to merge the dataframes for easier analyses across the different dataframes. The logic and code for the data merging part can be found in the notebook under the section **Merging the datasets**. 

The analysis of the data is complete now and we will start with using the datasets to answer the business questions.

### Q1, Q2. 
**Assumptions:** For calculating the customer acquisition on a monthly basis, we calculate the customers who are shopping for the first time in that month and divide that by the total unique customers on the platform to get the acquisition percentage for a particular month.  

![image](https://github.com/user-attachments/assets/85f8f64a-9303-4b2f-8996-2b5812125852) </br>

Month with the **highest acquisition rate**: **January** </br>
Month with the **lowest acquisition rate**: **November** </br>

Plotting the acquisition rate along with the marketing spend and the discount percentage will help us get a better understanding of the trends between them.
![image](https://github.com/user-attachments/assets/f5a355aa-ca12-4b11-9cea-2f66107d365c)
![image](https://github.com/user-attachments/assets/32a388f7-790c-4ab2-b0f8-01ad91f63b91)

**Based on the above graphs plotted with the data, we can conclude th following:**: </br>
**Strategies that can be implemented to address the fluctuations and ensure consistent growth throughout the year:**</br>
1. We can see that discounts drive acquisitions, so we can target more campaigns during the weaker performing months rather than saturating the god performing month with campaigns.  
2. after we have a high performing month with lots of new acquisitions, rolling out loyalty programs can help retain these acquired customers thus driving user retention post acquisition.  
3. From the plots, we can see that spending on marketing alone isn't directly translating into high acquisitions. We can analyse trhe marketing strategies and dicount coupons offered during high retention months and replicate those strategies across the underperforming months to increase customer acquistion for those months as well.  

**How the company can capitalize on high-performing months and improve performance during slower periods:**</br>
1. January, March, and April consistently show higher acquisition rates across the first two plots out of which March and April show strong acquisition numbers accompanied by high discount percentages.
2. September, October, and November consistently show lower acquisition rates. September has the lowest acquisition rate despite moderate marketing spend whereas Whereas for November the acquisition rate has been weak despite rise in dicounts and marketing spends.
3. We should capitalise on January, March and April, i.e., the high performing months by increasing the market spending here to capitalise during high acquisition months.
4. For the low performing months, we see that even high marketing spends and discounts are not driving acquisition rates up, so increasing the discounts and marketing spend might or moight not drive the acquisition numbers up. Analyzing campaign content and running more targeted campaigns would be better for these months.

### **Q3**. 
**Assumption:** Retention Rate is calculated monthly. RententionRate for a month = (Number of users that shopped in the previous and then shopped in teh current month too)/(number of unique users in the current month)
Customer Retention Trends:
<img width="630" alt="image" src="https://github.com/user-attachments/assets/365a5f00-2f8f-43af-9ac7-e18ce80cd22e" />
<img width="609" alt="image" src="https://github.com/user-attachments/assets/c0eb8b1e-c944-4dc4-a19c-e26d48d582e8" />
<img width="1190" alt="image" src="https://github.com/user-attachments/assets/6e19328b-685b-43fd-835c-8c1640ddd82c" />

From the plots, we can see the **weakest retention month is: February** and the **strongest retention month is: August**. 


**strategies to improve retention during weaker months:**
1. Instead of having very high discounts in one or two months, focus on more targeted campaigns and spread the discounts across months to improve the overall rate of user retention. We can see in the beginning period of February to April with very high discount s but still low user retentions. So dicsounts alone cannot drive the user retention rate up.
2. Use targeted marketings with time sensitive offers to motivate users to make their second purchase in the lower retention months. We know the lower retention months from the plots, so we can target those months with time sensitive offers to drive user retenytion up druing those months.

### **Q4**. 
1. Based on the data analysis we know that June-August are the high perfroming months in terms of user retention.
2. From the line plot, we can see that even when market spend or discounts are down, the user retention keeps going up. This might be a seasonal pattern. We can analyse the practices followed in the high retention months of June-August through the months having lower retention rates(February-May).

### **Q5**. 
We use a line plot to compare the revenue generated by new and existing customers month-over-month.  
<img width="987" alt="image" src="https://github.com/user-attachments/assets/34822fad-462b-41d8-8afb-7f890e69ead6" />
From the plotted graph, we can conclude the following about the revenue generated by new and existing customers month-over-month:
1. From january to June, the new customer revenue is much higher than the existing customer revenue indicating higher acquisition during these months.
2. However, during the mid year, starting from July, the existing customer revenue starts to increase and the new customer revenue starts to drop and the apttern remains more or less consistent during the secodn half of the year. Looking at acquisition startegies during these months can help boost the overall revenue even further.
3. Investing more in acquisition and retention of users during the second half odf the year using marketing and targeted coupons for customer onbaording can help increase the overall revenue of the comapny.

### **Q6**. 
Trends for monthly total Revenue for Coupon vs no coupon transaction are:</br>
<img width="802" alt="image" src="https://github.com/user-attachments/assets/7ffa5279-8172-4ffb-af79-2a812b42e7ea" /></br>
Total revenue with coupons is indeed higher across most months—that simply reflects the fact that a large fraction of your sales are transacting with a coupon. 

Trends for monthly Average Revenue for Coupon vs no coupon transaction are:</br>
<img width="632" alt="image" src="https://github.com/user-attachments/assets/d9adf6e3-8a51-416e-92c0-590a5f95a071" /></br>
Average revenue per transaction is slightly higher for no-coupon orders in most months—meaning that, on a per-order basis, coupon-users tend to spend a little less than coupon users. 

**Optimizations that can be done to maximize revenue while maintaining profitability:** </br>
1. From plots 1 and 2 we can see that coupons are working to bring in more transactions, but not to raise average order sizes. So to optimize revenue, we can start offering coupons that are applicable with higher basket values to increase the order value for coupon users thus increasing the profitability.

### **Q7**. 
The top performing products by revenue are: </br>
<img width="294" alt="image" src="https://github.com/user-attachments/assets/56ff92f1-869b-475a-a936-c486cf07ac99" />

Some more statistics about the total revenue, Average price and the average discount p[er product for the top 10 products are:
<img width="1318" alt="image" src="https://github.com/user-attachments/assets/67f0cf40-d705-4514-996e-09fdaceab20f" />

**We can use these insights to inform inventory management and promotional strategies in the following ways:**</br>
1. Prepare the inventory accordingly for the top selling products as they are expected to have a higher demand and these items going out of stock can affect revenue.
2. All of the top selling products have an average discount of approximately 20% or higher. This shows that discounts on particular products are a factor that can lead to driving uo the demand for that product. These insights can help drive coupon and promotional strategies as well as marketing strategies.
3. Most of the top selling have a low average price. So, product price also is a factor that affects the demand of a product.
4. So based on all these factors, we can draw insights about expected demands of products and the promotional strategies that can be used to drive upo their demand.

### **Q8**. 
The monthly pattern for the ROI is: </br>
<img width="1189" alt="image" src="https://github.com/user-attachments/assets/1af9e144-8a54-46cd-a261-a2473ad22210" />
Observations from the data and visualization: </br>
1. July 2019 has the highest ROI.
2. February 2019 has the lowest ROI.
3. There is a general upward trend in ROI from February to July.
4. There is some month-to-month variability in the ROI.

**How can marketing strategies be adjusted to improve ROI:** </br>
1. Analyze, Identify and document the marketing strategies employed during July month to see what led to such a high ROI and consider replicating those strategies in the future.
2. Explore what factors might have contributed to the low ROI in February, like seasonality, external economic conditions or poor marketing strategies. Identify and avoid similar strategies or plan more efficient approaches if those factors are likely to recur.
3. Based on the data, the upward trend in ROI from Feb-July indicates that increasing marketing spend can lead to a higher ROI. So investing more on marketing on months having historically high spending can lead to increase in ROI.

### **Q9**. 
<img width="627" alt="image" src="https://github.com/user-attachments/assets/4dd6abfe-7d05-4ae1-994a-20949ab1f210" /></br>
**Observations:**  
1. ROI for online marketing spending is constantly much higher than the ROI for offline marketing spend.

There are indeed opportunities here to relocate resources for better use. Shifting more budget from offline to Online investments can help increase the ROI. From the hostorical data, we have the months for which offline spending is generating highest ROI. So for these months we can focus more on the offline spending on marketing to increase the ROI as much as possible.  
We can also analyse the marketing startegies employed during months having peaks of ROI for offline spending and replicate those across the low performing months to increase the overall ROI for offlien marketing spend.  

### **Q10**. 
The code level logic for segmenting customers into dofferent groups using RFM segmentation Technique can be found in the jupyter notebook under the section named Q10. The logic for calculating the recency, frequency and the monetary value is under the Feature Engineering section in the jupyter notebook for the project.</br>
**Some staticstics about the different segments are:** </br>
<img width="407" alt="image" src="https://github.com/user-attachments/assets/f98ffc7e-ca90-4e3a-bf1a-328a5f3a20e5" />

**Segment wise revenue is:** </br>
<img width="240" alt="image" src="https://github.com/user-attachments/assets/277aa69a-cfa5-4445-b6fe-265dd2cc6e48" />

**Average discount across segments is:** </br>
<img width="230" alt="image" src="https://github.com/user-attachments/assets/712616c7-97f9-4995-b3e2-ee024977cb97" />

**Some targeted strategies that can be developed for each segment to improve retention and revenue are:**</br>
1. Premium Segment - They are the most recent, frequent and high-spending customers. Ategeted strategies for premium customers. 
   a. Offer rewards based on some milestone program to incentivise them to increase their spendings and interaction with platform even more. Give them exlusive offers fro being high spending customers.  
2. Gold Segment: These are recent, frequent but moderate spending customers.  
   a. Spend more on marketing and reaching out to these people since they are moderate spending customers and with right strategies can be converetd into premium/high spending ciustomers.  
3. Slver Segment: They have less frequency and recency and have moderate spendings on the platform.
   a. Use targeted campaigns by providing limited time ofers to increase the freequency of these customers since they shop less frequent on the platform.  
   b. Give them higher discounts to increase their purchase frequency and subsequently try to promote them to gold segment with repeated marketing campaigns and increased platform interaction.  
4. Standard Segment: These are the customers who have the least recency, frequency and spend the least amount on the platform.  
   a.Offer thse customers promotions to shop more frequently on the platform. These customers we can consider as target groups for increasing the customer retention and engage with them accordingly.  
We can further segraegate users nto each ssegment and then analyse trends like total revenue, the products preferred by each segment, the average order value of each segment to furthe develop targeted strategies tailored to each segment.

### **Q11**. 
**Pie chart and bar plot showing the revenue contribution of each segment:**</br>
<img width="638" alt="Screenshot 2025-05-12 at 11 49 34 PM" src="https://github.com/user-attachments/assets/839fc1fe-72af-4b91-b871-e42e3d0c7408" />
<img width="848" alt="image" src="https://github.com/user-attachments/assets/b05a9dc7-df3b-448c-8cda-7392bc08a365" />

As per the graphs, the Gold and Premium segments are the top segments in terms of revenue contribution. Whereas, the standard and Silver segent have almost the same revenue contribution.  
From the barplot for the revenue per segment: </br>
<img width="989" alt="image" src="https://github.com/user-attachments/assets/5090491a-7183-4a87-9fa5-0753414f0ba1" />
We can see that the median revenue of premium segment is higher than the gold segment. Alsom the premium segment also has a number of outliers. This means that a small portion of the users in the premium segment have much higher revenue than the rest of users in that segment. We see something similar for gold segment as well. The comapny can target these high revenue users and give them more incentives along with preium meberships to encourage them to spend even more. Along with that for the entire cohort, the marketing spend can be increased along with discounst as this group high spending individuals leading to more profit.  
The Standard and Silver segment have relatively less individuals that are very high spenders as compared to other users in those segment. For nurtuting the users in these segments, a balance between marketing spend and discounts need to be maintained so that the comopany can increase revenue and motivate theses users to spend more without taking a loss.  

### **Q12**. 
**Assumption:** Retention Rate is calculated monthly. RententionRate for a month = (Number of users that shopped in the previous and then shopped in teh current month too)/(number of unique users in the current month)
Customer Retention Trends:
<img width="630" alt="image" src="https://github.com/user-attachments/assets/365a5f00-2f8f-43af-9ac7-e18ce80cd22e" />
<img width="609" alt="image" src="https://github.com/user-attachments/assets/c0eb8b1e-c944-4dc4-a19c-e26d48d582e8" />
<img width="1190" alt="image" src="https://github.com/user-attachments/assets/6e19328b-685b-43fd-835c-8c1640ddd82c" />

From the plots, we can see the **weakest retention month is: February** and the **strongest retention month is: August**. 

**strategies to improve retention during weaker months:**
1. Instead of having very high discounts in one or two months, focus on more targeted campaigns and spread the discounts across months to improve the overall rate of user retention. We can see in the beginning period of February to April with very high discount s but still low user retentions. So dicsounts alone cannot drive the user retention rate up.
2. Use targeted marketings with time sensitive offers to motivate users to make their second purchase in the lower retention months. We know the lower retention months from the plots, so we can target those months with time sensitive offers to drive user retenytion up druing those months.


### **Q13**. 
Plot showing the lifetime value of customers acquired in different months: </br>
<img width="1000" alt="image" src="https://github.com/user-attachments/assets/f0e374b1-8f16-4331-89f2-3293fa476074" />
**Observations:**  
1. The lifetime value of customers acquired during the first half of the year is much higher as compared to the lifetime value of the customers acquired in the second half of the year. This shows that we have a weak negative correlation between the acquisition month of a customer and their lifetime value
2. The customer acquired in January have the highest lifetime value.

**How these insights can inform acquisition and retention strategies:**  
1. We can analyze the strategies implemented for customer acquisition for high lifetime value for retention and replicate those values across the low performing months.
2. Investigating the periods for low CLTV can also help provide insights to factors aas well as strategies that do not work and need to be improved upon.

### **Q14**  
We will be usinga statistical test to answer the following question:  
**Do customers who use coupons have a different average transaction value compared to those who do not**
Null Hypothesis: There is no difference in average transaction value between coupon users and non-coupon users.  
Alternative Hypothesis: There is a difference in average transaction value between coupon users and non-coupon users.  
**T-statistic: -5.974679218749349**  
**P-value: 2.3059138816811853e-09**  
**Since p value < 0.5 we reject the null hypothesis and conclude that there is a statistically significant difference in average transaction value between coupon users and non-coupon users**  
This can also be seen in the plot below comparing the average revenue with and without coupon usage.
<img width="630" alt="image" src="https://github.com/user-attachments/assets/fba98135-dabb-419c-87b8-b84c29153cbe"/></br>
From the image, we can see that there in no signifact in monthly average revenue with coupon use and without coupon use which also confirms the results of the hypothesis testing.

### **Q15**  
To check if purchase behaviours differ significantly across locations, we will use ANOVA statistical test.  
We will check for purchase behaviour(order value and order frequency) across locations. The results for the same are:  
**ANOVA for order value across locations: F-value = 2.8361212203128505, p-value = 0.02296323645910237**
The f and p values show that the order values vary significantly across locations. 

**ANOVA for frequency across locations: F-value = 566.0589430758187, p-value = 0.0**  
These values show that the difference in order values across locations is highly significant. So, we can conclude that customers in some cities are placing much more orders than the customers in other places.

### **Q16**  
**The correlation value between the transaction frequency(transactions per month) and the tenure_months is -0.40274277057546637**  
To furthere visualise this, we have divided the customer tenures into 5 bins and plotted the average transaction frequency for each bin:  
<img width="631" alt="image" src="https://github.com/user-attachments/assets/20533d29-bea1-46c0-801d-23bbedb8e88f" /></br>
This shows that the newer customer/ customers with lower value of tenure_months are buying more frequently than the older customers. This is also consistent with the negative correlation between the transaction frequeency and the customer tenure, which effectively means that as the customer tenure increases the transaction frequency decreases.
This results can be used to improve customer engagement and retrntion strategies in teh following ways:
1. From the analysis, we know that as the customer tenure increases their transaction frequency decreases.
2. To improve this, we can target customers who have high tenure months with coupons or rewards on further shopping to encourage them to interact more frequently with the platform even as there tenure grows. Through this we can increase the transaction frequency of high tenure/older customers and that will in turn lead to an increase in the revenue.

### **Q17**  
Plot for order count vs Delivery charges:  
<img width="622" alt="image" src="https://github.com/user-attachments/assets/1ba90715-3631-4eef-9ed8-dd8718084c2f" /></br>
Plot for order value vs Delivery charges:  
<img width="622" alt="image" src="https://github.com/user-attachments/assets/a5ee34f1-4c3c-4a44-bbe9-e4993837d442" /></br>
From the above plots, we can make the following observations:  
1. Majority of the orders are for the lower delivery fees(around Rs 0-74.48). This shows that most of the users prefer ordering for items with lower delivery charges.
2. The order count significantly drops as the delivery fee increases, so delivery fee is a major factor influencing the order count.
3. From the order value vs Delivery Charges, plot we can see that for higher delivery fee, the average order value is much higher than the average order value for lower delivery fee orders. This shows that the few customers that order with high delivery charges have higher value buckets and in turn higher order values.
**How can we optimize delivery pricing to increase order quantities or revenue:**
1. Higher delivery fees are a major detterent that discourages customers to buy. So reviewing, the delivery fees and offering incentives or concessions on delivery fees to new or less frequently shopping customers for products haveing higher delivery fees to help increase their interactoion with the platform.
2. We see that higher delivery fee increases the order value, so reducing the delivery fee by some magnitude on orders above a certain basket value can help capitalise more on this segment and slowly drive the order values up by giving customers incentives for bigger order values.
3. Since delivery fees is inversely proportional to the order count, a free delivery subscription model can help drive the order count up further while making sure profit margin is there as well. Some experimenting with this idea can help drive more revenue.

### **Q18**  
Plot for Average total spend/order value vs the GST Rate:  
<img width="589" alt="image" src="https://github.com/user-attachments/assets/6f498603-9dd5-4a7d-a937-1aa7209cce45" /></br>
Plot for Average total spend/order value vs Delivery Charge:
<img width="587" alt="image" src="https://github.com/user-attachments/assets/281ed513-bfd2-42c7-bc9e-c3bfa27f7a8e" /></br>
**Observations:**  
1. From the total spend vs GST rate graph, we can see that cuastomers tend to spend more on products with lower tax as increase in taxt increases the final cost of the product as well. Thus we can see a negative correlation between the customer spending and the GST rate.
2. Orders with higher delivery fee also have a higher order value. We can observe that delivery fee increases with increase in order size. So for orders woth higher cart value, we see higher delivery fees, but for orders with lower cart value, customers prefer to have lower delivery fees only. This observation was also seen in one of the previous plots in this business study.

**Opportunities to adjust pricing strategies to improve customer satisfaction and revenue:**  
1. Since customers spend most on low GST items, promoting theses items will more likely help in increasing the sale and the revenue.
2. Adjust delivery fees during periods expected to have high sales. Offering free delivery during for orders above a certain threshold as well as reduced delivery fees for normal products can lead to even higher sales during these months, since majority fo the customers prefer products with low delivery charges.

### **Q19**  
Plot for Seasonal trends in sales by product category:
<img width="652" alt="image" src="https://github.com/user-attachments/assets/1c5c4871-cb07-4ab6-844c-9eed796ce2f9" /></br>
**Observations:**    
1. Both Chicago and California which are the top locations by revenue, show a drop in May-June and a steep increase in sales during year end(November-December).
2. New York sees a sharp dip in sales in February and September followed by rise in sales October and November.
3. New Jersey and Washington also see an increase in sales in November-December but they are the lowest performings tates in terms of revenues,.

Plot for seasonal trends in sales across locations:
<img width="654" alt="image" src="https://github.com/user-attachments/assets/c2ad4d3e-23fb-4d3d-97c7-d2ad3ab43d97" /></br>
**Observations:**  
1. The product category with code nest-canada has the highest sales.
2. Apparel category has the highest demand in April with high demand from February-June period and demand slows down during the end of the year.
3. We see a start increase in teh demand for the product category nest From July onwards till teh end of the year.
4. Rest of the products have overall low demans as compared to these three products throughout the year.

The company can use this history data about the demands of the poducts during different seasons to better manage their inventory.
This darta can also be used to identify low selling periods for different product categories and try to increase the sales of these products during the low selling months using targeted promotion campaigns and product specific dicounst to encourage cutstomers to shop more for these products.  

### **Q20**  
Plot showing the average demand by the day of the week:  
<img width="631" alt="image" src="https://github.com/user-attachments/assets/7ec0f8a9-4390-4588-a56d-daffef0bb862" />

**Observations:**  
1. Week start has lower demand and hence lower revenue. Monday and Tuesday are the lowest performing days.
2. The sales and revenue picks up in mid week with the highest values seen across wednesday-friday. Weekends also have comparatively high sales.

**Strategies can be implemented to boost sales on slower days:**  
1. We need to boost the revenue for the starting days of the weeks. Special coupons or lower delivery rates for these days can act as ways to increase the sales during the starting days of the week.
2. The data shows that the revebue during the mid and later half of the week is strong, so shifting some of the marketing spend to start of the week can help drive the sales up for these days as well.
