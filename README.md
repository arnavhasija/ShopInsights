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
