# Enhancing Marketing Strategies Through Customer Segmentation and Retention Analysis
## Capstone Project #2 | Inggar Gumintang | JCDSOL - 014 - 2
- Tableau: [Capstone 2-Tableau](https://public.tableau.com/views/Capstone2_17202812459990/Capstone?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link),

## Project Description
This project aims to analyze supermarket customer data to understand purchasing behaviors and customer preferences. By employing segmentation techniques, statistical analysis, and data visualization, the project focuses on developing more effective marketing strategies and personalization to enhance customer engagement and revenue growth.

`Background and Context:`
- Supermarkets face intense competition and need to retain customers to maintain profitability.
- Customer segmentation and retention analysis help understand different customer groups and their behaviors, enabling personalized marketing strategies and improved engagement.

`Objectives of the Analysis:`
- Customer Profiling: Develop detailed profiles of customer segments.
- Retention Insights: Analyze recency data to understand retention patterns.
- Campaign Insights Unveiled:  Reveal valuable insights from marketing campaigns to improve strategic decision-making.

`Scope and Methodology:`
- Stakeholders: Business and Marketing Strategy Manager.
- Case study in a four-season country.
- Data Understanding and Preparation.
- Customer Segmentation Insights.
- Analysis of Customer Retention.
- Unveiling Campaign Insight.

## Description of the Dataset
The data can be accessed at the following link: [Customer Supermarket](https://drive.google.com/drive/folders/1WodnBbuYTvsF0-6HTuQABQ0KCS31lqbK), which has 2240 rows and  29 columns.
![Content Attributes, People & Products](image/CA_People&Products.png)
![Content Attributes, Promotion & Place](image/CA_Promotion&Place.png)

## Data Cleaning and Preparation Processes
### Data Type Changes
![Data Type Changes](image/Data_Types_Changes.png)
To perform a more accurate and efficient analysis, it is necessary to change the data types for the following columns: Education, Marital_Status, and Dt_Customer.
- `Education` and `Marital_Status`:The Education and Marital_Status columns should be changed to categorical data types. This change will help in the data analysis by enabling more efficient analysis methods and a more precise representation of the data.
- `Dt_Customer`: The Dt_Customer column should be changed to a datetime data type. This change will facilitate analyses that involve dates, such as calculating the time since a customer's enrollment or other time-based analyses.

### Handling Missing Value
![Handling Missing Value](image/Handling_Missing_Value.png)
Identification of Missing Values:
- Since the Income column has less than 5% missing values, they can be handled by filling with the mean.
There are two options for handling missing values:
- Delete rows or columns containing missing values.
- Fill in missing data: Replace missing values with appropriate or close estimates based on related columns using domain knowledge or statistical relationships. If this is not possible, use the mean, median, or mode. Deleting data should be a last resort.

### Checking Duplicate Update
![Checking Duplicate Update](image/Checking_Duplicate.png)
The analysis revealed 0 duplicate rows in the dataset, ensuring data integrity and uniqueness across records.

### Checking Outliers
![Checking Outliers](image/Outliers.png)
The columns MntWines, MntFruits, MntMeatProducts, MntFishProducts, MntSweetProducts, and MntGoldProds contain numerous outliers. However, we will not drop them because high-spending customers (outliers) are often significant for business insights. They represent a small but valuable segment of customers who contribute a large portion of revenue. Dropping them could lead to a loss of crucial information about high-value customers.

## Data Transformation
### Change Marital Status
The code replaces specific values in the Marital_Status column of df_new DataFrame with broader categories like 'Relationship' and 'Single'. This simplification aims to streamline customer data analysis and segmentation based on marital status.
![Change Marital Status](image/Marital_Status.png)

### Change Education Column
The code replaces values in the "Education" column of df_new to categorize educational levels into broader categories: "Graduate" for Graduation, PhD, and Master degrees, and "Undergraduate" for 2n Cycle and Basic education. It then prints the value counts of each category, providing a summary of the distribution of educational backgrounds among customers.
![Change Education Column](image/Education_Levels.png)

### Making Age Column
The code calculates the age of each customer by subtracting their birth year (Year_Birth) from 2014, which serves as the reference year for the calculation. This creates a new column Age in the df_new DataFrame, providing insights into the age distribution of customers based on their birth year.

![Change Education Column](image/Age_Column.png)

### Making Childern Column
The code creates a new column named 'Children' in the DataFrame df_new. This column sums up the values from two existing columns, 'Kidhome' and 'Teenhome', representing the number of children in each household. The purpose is to consolidate the information about children in a more convenient single column for analysis or reporting purposes.
![Making Children Column](image/Children_Column.png)

### Making Monthly Income Column
The code snippet adds a new column named 'Monthly Income' to the DataFrame df_new. This column is created by dividing the existing 'Income' column by 12, which converts the annual household income of each customer into a monthly equivalent. This transformation facilitates further analysis and insights based on monthly income levels, enabling more granular examination of consumer spending patterns, budgeting behaviors, and financial planning considerations within the dataset.
![Making Monthly Income Column](image/Monthly_Income.png)

### Making Monthly Spending Column
The code first creates a new column named 'Total Spending' in the DataFrame df_new. This column is the sum of the values from six existing columns: 'MntWines', 'MntFruits', 'MntMeatProducts', 'MntFishProducts', 'MntSweetProducts', and 'MntGoldProds'. Each of these columns represents the amount spent by customers on different product categories over two years. The purpose of creating the 'Total Spending' column is to calculate the overall spending of each customer across all product categories. Next, the code creates another column named 'Monthly Spending' by dividing the 'Total Spending' by 24. This calculation provides the average monthly spending of each customer, assuming the data covers a period of two years. The 'Monthly Spending' column is useful for further analysis, such as identifying high-value customers on a monthly basis or understanding monthly spending behavior.
![Making Monthly Spending Column](image/Monthly_Spending.png)

### Rename Column
The code renames several columns in the DataFrame df_new to more concise and readable names. This makes the dataset easier to understand and work with. The purpose is to improve the clarity of the dataset by replacing the original column names with shorter, more descriptive names that are easier to reference in analysis and visualization.
![Rename Column](image/Rename_Column.png)

## Data Analysis
### Customer Segmentation Insights
#### Comparing Monthly Income and Spending

|          Monthly Income                |         Monthly Spending                   |
| :------------------------------------: | :----------------------------------------: |
| ![Income](image/DA_Monthly_Income.png) | ![Spending](image/DA_Monthly_Spending.png) |

Based on the previous analysis and the insight that the average monthly spending percentage of 0.58% indicates a potentially low level of consumer expenditure relative to their income, here are additional strategies and insights:

Additional Analysis and Strategies

- `Diversification of Product Offerings:` Conduct market research to identify complementary products or services that align with consumer lifestyles and preferences. Introduce diverse product lines that cater to varying consumer needs and aspirations, thereby encouraging increased spending across multiple categories.
- `Behavioral Economics Approach:` Apply behavioral economics principles to incentivize consumer spending. Utilize tactics such as bundling products, creating scarcity through limited-time offers, and leveraging social proof to influence purchase decisions and stimulate higher transaction volumes.
- `Segment-Specific Strategies:` Segment customers based on spending behavior and preferences identified in the analysis. Develop targeted marketing campaigns and product promotions tailored to each segment’s unique characteristics and buying patterns, thereby maximizing engagement and conversion rates.
- `Promotion of High-Margin Products:` Identify and promote products with higher profit margins to enhance revenue growth. Implement strategies to highlight the value and benefits of premium offerings, encouraging consumers to trade up and increase their average transaction value.
- `Data-Driven Personalization:` Leverage customer data and analytics to personalize marketing communications and product recommendations. Implement predictive analytics to anticipate consumer needs and preferences, delivering relevant offers and experiences that drive incremental sales and customer satisfaction.
- `Cross-Selling and Upselling Initiatives:` Implement cross-selling and upselling strategies to increase the average order value. Recommend complementary products or upgrades based on consumer purchasing history and preferences, enhancing the overall shopping experience and maximizing revenue per transaction.
- `Continuous Monitoring and Optimization:` Establish a robust monitoring framework to track the impact of implemented strategies on consumer spending behaviors and business performance. Regularly analyze key performance indicators (KPIs) and consumer feedback to iterate and refine strategies for continuous improvement.
- `Collaboration with Suppliers and Partners:` Collaborate with suppliers and strategic partners to negotiate favorable terms, optimize inventory management, and introduce exclusive product offerings. Strengthening these relationships can lead to enhanced product availability, competitive pricing, and increased consumer appeal.

By integrating these additional strategies into the existing framework, businesses can foster a more dynamic and consumer-centric approach to revenue growth. This holistic approach not only aims to maximize consumer spending but also cultivates long-term customer loyalty and sustainable business growth in an evolving market landscape.

#### Analyzing Consumer Spending Patterns Across Different Age Groups

![Spending per Age Group](image/DA_Spending_Age.png)

From the graph, we observe that:
- The average spending increases progressively with age.
- Customers aged greater than 61 (>61) exhibit the highest average spending.

Based on these insights, the following strategies could be employed to maximize customer engagement and revenue across different age groups:

`Targeted Marketing for Older Age Groups:`

- Focus on High-Spending Segments: Given that older customers (51-60 and >61) are spending more, marketing campaigns should target these age groups with premium products and services.
- Loyalty Programs: Develop loyalty programs tailored to older customers, offering them exclusive deals and rewards based on their higher spending patterns.

`Engagement Strategies for Middle-Aged Groups:`

- Promotional Offers: For the 31-40 and 41-50 age groups, use promotional offers and discounts to encourage increased spending. Highlight products that cater to family needs and professional lifestyles.
- Cross-Selling and Upselling: Implement strategies to cross-sell and upsell related products, capitalizing on the established spending patterns within these age groups.

`Attracting Younger Customers:`

- Affordable Options: Develop product lines that are affordable for customers under 30. Consider bundle deals or entry-level products to attract younger customers.
- Engagement through Digital Channels: Younger customers are typically more engaged with digital marketing. Utilize social media, influencer marketing, and mobile-friendly campaigns to capture their attention.

`Personalized Customer Experiences:`

- Data-Driven Personalization: Leverage customer data to provide personalized recommendations and shopping experiences. Tailor messages and product suggestions based on previous spending habits and age-related preferences.
- Feedback and Adaptation: Regularly gather feedback from different age groups to understand their evolving needs and preferences, and adapt marketing strategies accordingly.
By implementing these strategies, the business can better engage customers across various age groups, thereby increasing overall customer satisfaction and boosting revenue.

#### Understanding Marital Status and Education Levels Composition in Customer Segmentation

|             Marital Status              |               Education Levels              |
| :-------------------------------------: | :-----------------------------------------: |
| ![Marital](image/DA_Marital_Status.png) | ![Education](image/DA_Education_Levels.png) |

The majority of customers are in the 'Relationship' category and have 'Postgraduate' education levels. This suggests that a significant portion of the customer base consists of educated couples or individuals in stable relationships. Marketing strategies should prioritize this dominant group by offering premium products or services that cater to their sophisticated tastes and family-oriented needs.

`Target Market Potential:`

- For 'Relationship' and 'Postgraduate': Focus on products and services that appeal to educated couples or families, such as family vacation packages, educational products for children, or high-end home appliances.
- For 'Relationship' and 'Undergraduate': Although smaller, this segment may be interested in affordable yet high-quality family-oriented products, entry-level luxury items, or career advancement tools.

`Further Segmentation:`

- Conduct detailed segmentation within the 'Relationship' and 'Postgraduate' category to uncover variations in purchasing behavior. For example, consider age, income level, and specific interests to tailor marketing efforts.
- Within the 'Single' and 'Postgraduate' segment, identify the specific needs of single, highly educated individuals, such as professional development courses, solo travel packages, or luxury lifestyle products.

`Opportunities with 'Single' and 'Undergraduate' Categories:`

- Although these segments are smaller, they present unique opportunities for engagement. For 'Single' and 'Undergraduate' customers, consider marketing affordable lifestyle products, social events, or educational services that can help them advance their careers or personal lives.
- Tailored strategies for 'Single' and 'Postgraduate' individuals might include networking events, high-end personal development programs, or exclusive memberships.

`Cross-Segment Marketing:`

- Leverage insights from both marital status and education level to create cross-segment marketing strategies. For instance, design campaigns that appeal to both 'Relationship' and 'Single' customers by highlighting different product benefits tailored to their education levels.

Conclusion:
- By combining the insights from marital status and education levels, businesses can develop more nuanced and effective marketing strategies. This approach ensures that products and services are aligned with the preferences and needs of each customer segment, thereby enhancing customer satisfaction, retention, and overall business growth.

Actionable Recommendations:
- Develop Personalized Marketing Campaigns: Create campaigns that specifically target 'Relationship' and 'Postgraduate' customers with premium offerings, while also addressing the unique needs of 'Single' and 'Undergraduate' segments.
- Enhance Customer Segmentation: Use advanced analytics to further segment the customer base, identifying key behavioral and demographic traits that can inform marketing strategies.
- Strengthen Loyalty Programs: Design loyalty programs that reward both 'Relationship' and 'Single' customers, with a focus on educational achievements and lifestyle preferences.
- Product Development: Tailor product development to meet the demands of educated customers, ensuring high quality and relevance to their lifestyles.

By integrating insights from both marital status and education level proportions, businesses can create more targeted and effective marketing strategies that drive engagement and growth.


#### Holiday Magic: Winning Over Customers with Strategic Family Packages

![Number of Children](image/DA_Number_Children.png)

The results indicate that customers with one child outnumber those without children, with two children, and with three children. This suggests that the group of customers with one child holds significant influence in purchasing patterns or consumer preferences within the supermarket dataset. Such analysis provides insights for marketing teams to tailor more specific strategies or adjust product offerings that better suit the preferences of this customer segment.

Furthermore, this data highlights the potential for implementing holiday package promotions. Marketing teams could develop targeted promotional campaigns, such as offering holiday packages to popular destinations as part of a purchase incentive, particularly for customers with one child who form a significant segment of the customer base.

#### Targeted Treats: Maximizing Profit with Family-Focused Products

![Spend Product](image/DA_Spend_Product.png)

The bar chart above reveals that the highest spending is on wines, meats, and gold. Conversely, spending on fish, sweets, and fruits is significantly lower. Additionally, our previous analysis indicates that the monthly spending is only 0.58% of the total monthly income. This suggests that customers might be allocating a minimal portion of their budget to these categories.

Given the low spending on family-related products such as fish, sweets, and fruits, there is a clear opportunity to develop and promote products that cater to family needs. This aligns with our findings regarding the influence of customers with one child, highlighting the potential to create targeted marketing strategies to increase spending in these areas.

Action Plan:

`Expand Family-Friendly Product Lines:`

- Introduce New Products: Launch new products that appeal to families, such as healthy snack options, family meal kits, and kid-friendly fruits and vegetables.
- Promote Existing Family Products: Increase visibility and availability of existing products that cater to families, such as bulk packaging for fruits, fish, and sweets.

`Targeted Marketing Campaigns:`

- Holiday Package Promotions: Develop promotional campaigns offering holiday packages for families as part of a purchase incentive, particularly focusing on customers with one child.
- Family-Centric Advertisements: Create marketing materials that highlight the benefits of family-friendly products, emphasizing convenience, health benefits, and cost savings.

`In-Store and Online Engagement:`

- Family Events and Workshops: Organize events and workshops aimed at families, such as cooking classes using family-friendly products, tasting events, and nutrition seminars.
- Enhanced Online Experience: Improve the online shopping experience with sections dedicated to family needs, offering tailored recommendations, and easy-to-find family-friendly products.

`Collaborations and Partnerships:`

- Partner with Schools and Community Centers: Collaborate with local schools and community centers to promote healthy eating habits and provide special offers to families.
- Collaborate with Health Experts: Partner with nutritionists and pediatricians to endorse family-friendly products and provide expert advice on healthy family eating.

`Loyalty Programs and Incentives:`

- Family Loyalty Programs: Develop loyalty programs that reward families for their purchases, offering points, discounts, and exclusive family-oriented deals.
- Incentives for Bulk Purchases: Provide incentives for bulk purchases of family-friendly products, such as discounts or free items with large orders.

By implementing these strategies, we can better cater to the needs of families, ultimately driving revenue growth through increased spending on products that support family needs. This approach not only addresses current spending patterns but also fosters long-term customer loyalty and satisfaction.

#### Beyond the Checkout: Unveiling Opportunities in Store and Web Purchases

![Purchases Place](image/DA_Purchases_Place.png)

The analysis reveals that store purchases dominate as the most common method of purchase, followed by web purchases, catalog purchases, and deals purchases. This indicates that while traditional in-store shopping remains the preferred choice among customers, there is a significant trend towards online shopping, highlighting the growing importance of e-commerce. Catalog and deals purchases are less popular, suggesting potential areas for targeted marketing and promotional efforts to boost these channels. Additionally, the average number of web visits is approximately 5 times per month for each customer, indicating a substantial level of online engagement that can be further leveraged through targeted digital marketing strategies.


Action Plan
To leverage the insights gained from the purchase method analysis, the following action plan can be implemented to boost marketing campaigns via web and onsite branding:

`Enhance Online Presence and User Experience:`

- Optimize Website: Ensure the website is user-friendly, with easy navigation, fast loading times, and a seamless checkout process.
- Personalized Recommendations: Utilize customer data to offer personalized product recommendations and promotions.
Mobile Optimization: Make sure the website is fully optimized for mobile devices, providing a smooth shopping experience on smartphones and tablets.

`Boost Marketing Campaigns:`

- Web Promotions: Increase web-based promotional campaigns, including discounts, flash sales, and exclusive online offers to drive web purchases.
- SEO and SEM: Invest in search engine optimization (SEO) and search engine marketing (SEM) to enhance online visibility and attract more traffic to the website.
Social Media Advertising: Utilize social media platforms to run targeted ad campaigns, focusing on customer segments most likely to make web purchases.

`Onsite Branding and In-Store Experience:`

- In-Store Promotions: Implement attractive in-store promotions, such as buy-one-get-one (BOGO) offers, discounts on bulk purchases, and loyalty programs.
- Brand Ambassadors: Employ brand ambassadors or in-store promoters to engage with customers, provide product information, and encourage purchases.
- Enhanced Visual Merchandising: Improve visual merchandising in-store to create an appealing shopping environment, using eye-catching displays and signage to highlight promotions and new products.

`Integrate Online and Offline Strategies:`

- Omni-Channel Approach: Develop an integrated omni-channel marketing strategy that seamlessly connects online and offline channels, providing a consistent customer experience.
- Click-and-Collect Services: Promote click-and-collect services, allowing customers to purchase online and pick up in-store, combining the convenience of online shopping with the immediate gratification of in-store pickup.
- Cross-Promotions: Offer cross-promotions that encourage customers to explore both online and in-store options, such as exclusive online discounts redeemable in-store.

`Customer Engagement and Feedback:`

- Customer Loyalty Programs: Enhance loyalty programs to reward repeat purchases both online and in-store, offering points, discounts, and exclusive deals.
- Feedback Mechanisms: Implement mechanisms to collect customer feedback on their shopping experience, both online and in-store, to identify areas for improvement and tailor marketing efforts accordingly.
- Customer Support: Provide excellent customer support across all channels, ensuring quick resolution of issues and a positive shopping experience.

By implementing these strategies, the business can boost marketing campaigns via the web and enhance onsite branding, ultimately driving sales and improving customer satisfaction across multiple purchase methods.

### Analysis of Customer Retention
#### Recency Radar: Navigating Peaks in Customer Engagement

![Recency Distribution](image/DA_Recency_Distribution.png)

The distribution of Recency in the data shows distinct peaks on specific days (around 0, 10, 30, 50, and 90 days). These high-frequency days indicate increased purchasing activity from customers, although the overall distribution of Recency does not follow a normal pattern.

Action Plan

`On-site Branding:`

- Target Day 0: Customers who have just made a purchase. Enhance in-store branding to encourage impulse purchases.
- Target Day 10: Customers who tend to return within 10 days. Display special promotional banners in-store to capture their attention.

`Email Marketing Campaigns:`

- Day 30 and Day 50: Send promotional or reminder emails a few days before customers typically return, incentivizing them to shop again with special offers or discounts.

`Social Media Promotions:`

- Day 90: Use social media to remind and promote products to customers who tend to return after a longer period.

`Store Layout Optimization:`

- General: Optimize store layout to maximize exposure to products frequently purchased by customers with high Recency on these specific days.
With this action plan, you can leverage Recency data to enhance customer retention and drive more in-store purchases.

#### Segment Spotlight: Unveiling Recency-Based Spending

![Recency Distribution](image/DA_Recency_Segment.png)

While the distribution of customers based on Recency segments is fairly balanced, there is no significant difference observed in the average total spending across segments.

`Action Plan:` Focus on additional promotional strategies or incentives for customers in the 'Very Recent' and 'Moderate' segments to enhance retention and repeat purchases. Given the proximity in behavior, the impact on the 'Recent' segment from strategies targeting 'Moderate' and 'Very Recent' segments could help optimize promotional budgets effectively. Additionally, consider further personalization for the 'Long Time Ago' segment.

### Campaign Insights Unveiled
#### Campaign Data Distribution and Response Analysis

![Campaign Distribution](image/DA_Campaign_Distribution.png)

The results of the normality tests indicate that all campaign columns (Campaign 1, Campaign 2, Campaign 3, Campaign 4, Campaign 5) and the response column have very low p-values (close to 0.0), meaning that the data in these columns are not normally distributed. Therefore, non-parametric tests such as the Chi-Square test are more appropriate.

Based on these results, the use of the Chi-Square test is justified because:
- The data are not normally distributed.
- The data are categorical.

All p-values are very low (well below the significance level of 0.05), meaning we can conclude that there is a statistically significant relationship between each campaign and the response. Thus, the initial use of the Chi-Square test was appropriate, and the results indicate a significant relationship between the variables.

#### Statistical Correlation Between Campaigns and Response
![Correlation Campaign & Response](image/DA_Campaign_vs_Response.png)

All campaign offers show a statistically significant relationship with the customer's response to the last campaign. This indicates that customers who responded positively to earlier campaigns are more likely to respond positively to future campaigns.

Campaign 5 has the highest chi-square value, indicating the strongest association with customer response.

Possible Reasons for the Strong Association:

- More Attractive Offer: Campaign 5 might have offered more attractive or relevant deals to customers, making it more likely for them to respond positively. This could include bigger discounts, highly desired products, or exclusive offers.
- Increased Customer Trust: Customers who responded positively to previous campaigns may have developed more trust in the company's offers. By Campaign 5, this trust could have peaked, leading to a higher response rate.
- Better Customer Segmentation: Campaign 5 might have used more refined customer segmentation, ensuring that the offers were highly targeted and relevant to the recipients' preferences and buying behavior.
- Improved Communication Channels: There might have been improvements in the communication strategies used in Campaign 5, such as more effective email marketing, better-targeted ads, or personalized messages that resonated more with the customers.
- Optimal Timing: The timing of Campaign 5 might have been more optimal, possibly aligning with periods when customers are more likely to make purchases, such as during holidays or promotional seasons.

Action Plan

`Leverage Past Campaign Data:`

- Utilize customer response data from previous campaigns to tailor future offers.
- Target customers who have responded positively to earlier campaigns with personalized and attractive offers.

`Maximize Web Platform Potential:`

- Enhance User Experience: Improve website interface and user experience to make online shopping more appealing.
- Personalized Online Offers: Use data-driven insights to create personalized offers for web purchases, targeting customers based on their purchase history and campaign responses.
- Promotional Campaigns: Launch targeted web-exclusive promotions and discounts to drive more traffic and sales through the online platform.

`Campaign Optimization:`

- Analyze Campaign Patterns: Conduct a deeper analysis of customer demographics and preferences to understand which segments are more responsive to certain campaigns.
- Test and Iterate: Implement A/B testing for different campaign strategies to determine the most effective approaches.
- Cross-Channel Integration: Ensure consistent messaging and offers across both online and offline channels to provide a seamless customer experience.

`Focus on High-Value Customers:` 

- Identify high-value customers who consistently respond to campaigns and create loyalty programs to retain them.
- Offer exclusive deals and rewards to high-value customers to incentivize repeat purchases.

By leveraging the insights from the campaign analysis and focusing on maximizing the potential of the web platform, the business can enhance its marketing strategies, improve customer engagement, and drive higher sales and retention rates.

## Conclusion and Future Work

Summary Key Findings:
- `Customer Spending Behavior:` Customers allocate only 0.58% of their monthly income on average to supermarket purchases, indicating potential for increased spending with targeted strategies.

- `Marital Status and Education:` Majority of customers are in relationships and have postgraduate education, suggesting a focus on premium products and family-oriented offerings.
- `Product Preferences:` High spending is observed on wines, meats, and gold, with lower spending on fish, sweets, and fruits, highlighting opportunities for product diversification.
- `Purchase Methods:` Store purchases dominate, but there's growing importance of web purchases, suggesting a need to enhance online marketing and sales strategies.
- `Campaign Effectiveness:` All campaigns (Campaigns 1-5) show significant associations with customer response, with Campaign 5 exhibiting the strongest impact.

Final Strategic Recommendations:
- `Diversification of Product Offerings:` Introduce new products and promotions tailored to family needs, including holiday package promotions to increase average transaction value.
- `Enhanced Digital Marketing:` Optimize online platforms with personalized offers and targeted promotions, particularly for high-spending segments like customers with families.
- `Segment-Specific Campaigns:` Develop marketing campaigns that resonate with different demographic segments (e.g., couples, families, singles) based on spending behaviors and preferences.
- `Cross-Channel Integration:` Integrate online and offline channels to provide a seamless customer experience, promoting family-oriented products and holiday packages consistently.
- `Loyalty Programs and Incentives:` Implement loyalty programs with rewards for repeat purchases and high-value customer segments, including incentives for purchasing holiday packages and family-oriented products.

By focusing on these strategic recommendations, businesses can leverage customer insights to drive engagement, increase spending, and foster long-term loyalty, particularly through targeted promotions such as holiday packages for families.
