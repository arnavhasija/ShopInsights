# ShopInsights
Explore customer preferences with e-commerce trends data. Uncover demographics, purchase history, and consumer choices to optimize marketing and boost satisfaction, which could help reshape how businesses connect with their audience.

<h2>Background and Motivation</h2>

In this exploration, I will delve into the fascinating realm of consumer behavior and shopping habits using a rich dataset sourced from C. Okan Sakar and Yomi Kastro's paper, "Real-time prediction of online shoppers’ purchasing intention using multilayer perceptron and LSTM recurrent neural networks." The paper proposes a real-time analysis system that predicts a visitor's shopping intent and the likelihood of them abandoning a website.

Understanding customer preferences is paramount in today's dynamic market. Through this project, I aim to embark on this journey to decode real-time predictions of online shoppers' purchasing intentions. My motivation lies in leveraging this comprehensive dataset to glean insights that can revolutionize marketing strategies, optimize product offerings, and enhance overall customer satisfaction. I plan to explore the nuances of consumer behavior and transform raw data into actionable insights that redefine the way businesses connect with their audience.

<h2>Dataset</h2>

The dataset, comprising 12,330 customer sessions over a year (excluding holidays, special days, or campaigns), serves as a compass in navigating the intricacies of online shopping. With 10 numerical and 8 categorical variables at  my disposal, I aim to unravel the underlying patterns that shape purchasing decisions. Below is a description of the features available in this dataset.

| Feature | Definition  | Significance |
| ------------- | ------------- | ------------- |
| Administrative | Number of pages visited in the administrative section | Level of engagement with administrative content  |
| Administrative_Duration  | Total time spent on administrative pages  | Duration of interaction with administrative content |
| Informational  | Number of pages visited in the informational section | Engagement with informational content |
| Informational_Duration  | Total time spent on informational pages | Duration of interaction with informational content |
| ProductRelated | Number of pages visited in the product-related section | Interest in products and potential purchase intent |
| ProductRelated_Duration | Total time spent on product-related pages| Duration of interaction with product-related content |
| BounceRates | Percentage of visitors who navigate away after one page | Reflects the bounce rate, a metric for website engagement |
| ExitRates | Percentage of visitors who leave the site from a page | Measures the likelihood of users exiting the website |
| PageValues | Average value of a page visited before completing a transaction | Quantifies the contribution of a page to overall revenue |
| SpecialDay | Proximity of the visit to a special day | Captures the impact of special occasions on user behavior |
| Month | Month of the year of the visit | Provides a temporal dimension to user behavior |
| OperatingSystems | Operating system used by the visitor | Insight into the user's technology preferences |
| Browser | Browser used by the visitor | Indicates the user's choice of web browser |
| Region | Geographic region of the visitor | Geographical context for understanding user demographics |
| TrafficType | Source of the traffic (e.g., search engines, direct traffic) | Helps identify the channels driving user visits |
| VisitorType | Type of visitor (new, returning, or other) | Categorizes users based on their visit history |
| Weekend | Binary indicator of whether the visit occurred on a weekend | Captures potential variations in user behavior on weekends |
| Revenue | Binary indicator of whether the visitor made a purchase	| Key target variable indicating successful conversion |

<h2>Exploratory Data Analysis (EDA) Overview</h2>

The correlation matrix heatmap below provides a visual representation of the relationships between various features in the dataset. 

<p align="center">
  <br>
  <img src="/images/img1.JPG">
</p>

Each cell in the matrix represents the correlation coefficient between two corresponding features, ranging from -1 (perfect negative correlation) to 1 (perfect positive correlation). The intensity of the color indicates the strength and direction of the correlation. Let's delve into some key insights derived from this visualization.

<b>BounceRate and ExitRates:</b>
The strong positive correlation (coefficient of 0.91) between BounceRate and ExitRates indicates a close relationship in user behavior. When a visitor bounces from the website (views only a single page) and subsequently exits, it suggests a quick departure without exploring further content. This association highlights the significance of understanding and addressing factors contributing to both bounce and exit behaviors for a more effective user engagement strategy.

<b>ProductRelated and ProductRelated_Duration:</b>
The substantial correlation (coefficient of 0.86) between the number of ProductRelated pages visited and the corresponding duration spent on these pages implies a deep level of engagement with product-related content. Users who explore a higher number of product-related pages tend to invest more time on the site. This insight underscores the importance of optimizing and enhancing the user experience on product-related pages to maximize engagement and potentially influence purchasing decisions.

<b>Weekend and Revenue:</b>
The correlation between Weekend and Revenue is very weak, with a coefficient of 0.029. This implies that sessions on weekends have only a marginal impact on the likelihood of revenue generation. While weekends may not strongly influence revenue, other factors such as marketing campaigns or specific promotions during weekends could be explored to boost revenue during these periods. The subtle correlation encourages a nuanced approach when tailoring strategies for weekend engagement.

<b>Revenue and PageValue:</b>
The moderate positive correlation (coefficient of 0.49) between PageValue and Revenue suggests a noteworthy relationship between the perceived value of a page (as measured by PageValue) and the likelihood of generating revenue. Pages with higher perceived value, whether through informative content or enticing offers, are more likely to contribute to revenue generation.

<h3>Monthly Revenue Distribution</h3>

The analysis reveals distinct trends in monthly revenue distribution, with notable peaks observed in May, November, March, and December. These months coincide with heightened customer activity and significant instances of customer sessions generating revenue.

<p align="center">
  <br>
  <img src="/images/img3.JPG">
</p>

May and November emerge as the months with the highest instances of customer sessions generating revenue. Several factors contribute to this trend. May marks the onset of summer in many regions, leading to increased spending on travel, outdoor activities, and summer-related products. Similarly, November is associated with the holiday season, including events like Black Friday and Cyber Monday, which drive consumer spending on gifts, decorations, and festive items. Retailers often roll out special promotions and discounts during these months to capitalize on seasonal trends and holiday shopping sprees. These promotional efforts can stimulate consumer demand and incentivize purchases, resulting in higher revenue generation.

While not as pronounced as May and November, March and December also exhibit notable peaks in customer activity and revenue generation. Spring March represents a transitional period as winter fades and spring approaches. Customers may engage in home renovations, or wardrobe updates, leading to increased spending on related products and services. December is characterized by holiday preparations, including gift shopping and travel arrangements. As the holiday season approaches, customers actively seek out gifts and travel accommodations, contributing to heightened revenue generation during this month.

Overall, the observed trends in monthly revenue distribution reflect a combination of seasonal influences, promotional strategies, and consumer behavior patterns. By understanding these trends, businesses can tailor their marketing efforts, inventory management, and customer engagement strategies to maximize revenue opportunities during peak months.

<h3>Feature Importance Analysis</h3>

The feature importance chart shown below was generated from a Random Forest (RF) model and provides insights into which features have the most significant impact on the model's predictive performance. The importance values indicate the relative contribution of each feature to the model's decision-making process.

<p align="center">
  <br>
  <img src="/images/img2.JPG">
</p>

The PageValues feature holds the highest importance value of approximately 0.33. This suggests that the average value of pages visited before a transaction plays a crucial role in predicting revenue. It indicates that pages with higher PageValues tend to contribute more significantly to revenue generation. Next, ProductRelated_Duration and ExitRates, both have importance values around 0.08. ProductRelated_Duration signifies the total time spent by users on product-related pages during their session, indicating that prolonged engagement with product-related content correlates positively with revenue. Conversely, ExitRates represent the percentage of exits from specific pages, indicating potential areas of user dissatisfaction or obstacles that may lead to revenue loss. 

ProductRelated, BounceRates, and Adminstrative_Duration also contribute to revenue prediction, but with slightly lower importance values. ProductRelated denotes the total number of product-related pages visited, suggesting that the quantity of product interactions influences revenue. BounceRates highlight the significance of user engagement and satisfaction, as higher bounce rates may indicate lower conversion rates and revenue. Adminstrative_Duration measures the time spent on administrative pages, such as account management or checkout processes, underscoring the importance of streamlining these processes to enhance revenue generation. Overall, these insights underscore the multifaceted nature of revenue prediction in e-commerce and emphasize the importance of optimizing user experience, content relevance, and transaction processes to maximize revenue and customer satisfaction.

<h2>Model Development</h2>

Through exploratory data analysis (EDA), I gained an understanding of the dataset's structure, distribution of features, and potential relationships between variables. Next, predictive models were trained to predict if the online sessions resulted in revenue, aiming to uncover insights into customer shopping behavior and revenue generation patterns. Leveraging techniques such as feature selection, hyperparameter tuning, and model evaluation, I built predictive models capable of capturing the complexities of consumer decision-making processes in the e-commerce domain. 

I performed feature engineering to create new features or transform existing ones to capture additional information relevant to the problem domain. Feature selection helps identify the most informative features for predictive modeling, reducing dimensionality and improving model performance. Based on the correlation analysis, I omitted highly correlated features which could impact the performance of the predictive model.

For the predictive model, I chose the GradientBoostingClassifier algorithm due to its effectiveness in handling complex datasets and capturing nonlinear relationships. I trained the model on the preprocessed dataset and evaluated its performance using metrics like F1 score, which accounts for both precision and recall, making it suitable for imbalanced classification tasks. I used GridSearchCV to systematically search over a range of hyperparameters and identify the combination that yields the best results.

Model building is an iterative process, and I continuously refined my approach based on insights gained from evaluation results. I explored alternative modeling techniques, feature engineering strategies, and hyperparameter tuning methods to enhance the model's predictive capabilities and address specific challenges encountered during the process.

