# Decrypt Black Friday
## 1. Project overview

Our dataset, coming from Kaggle, is a summary of retail sales happened in the client store during the Black Friday. The dataset contains some basic customer demographic information and their purchase data associated. The customer demographic data include such as gender, city in stay, occupation, marital status and so on.

![GitHub](https://github.com/zhangyingchi/BlackFriday/blob/chi-zhang/image/user_profile.png)

Our goal of this project is that standing in the shoes of the retail store, we try to help our client store understand their customers’ purchasing behaviors better. Hence, the store can make better decisions on customer management and resources allocations to boost its sales.

To achieve that, we first performed linear regression analysis by using OLS model to understand what factors affect the purchase amount more greatly than others. After gaining the basic understanding of our customers, we then use clustering and classification algorithms to segment our customers and to identify the most important customers for our client. To further understand consumer purchasing behaviors, we performed market basket analysis to see the correlations between categories of products purchased. We also performed Matrix Factorization analysis to gain understanding of customers’ “opinions” on different products. We will then discuss the analyses we performed in detail below.


## 2. Customer labeling and classification model
To improve the purchase prediction, we need to label customers and classify them according to their characteristics. Here we use k-means clustering to classify customers into four groups in terms of basket size and purchase amount. The reason we choose four groups is that we want to focus on the group with high purchase amount and big basket size, which will be our VIP customers (very important to our business), and by labeling customers into four groups the result of classification is more clear.

![GitHub](https://github.com/zhangyingchi/BlackFriday/blob/chi-zhang/image/users_label.png)

In order to label our customers, we used top 3 frequently bought categories as features to pass into Decision Tree, Random Forest and SVM models. The outcomes of the first two models are overfitting, but SVM gives us a fairly good estimate on identifying the cluster of an in-come customer, and thus, we can check whether the in-come is customer is our VIP customer or not.

## 3. Market Basket Analysis
This dataset also enables us to explore the associations between each product and category. It would be very helpful for our business to predict what kinds of product our customer would likely to buy given some historical purchase records. To make good predictions of the correlations between items, we introduce Apriori algorithm here to mining the association rules of our historical records.
Apriori is an algorithm for frequent-item-set mining and association-rule learning over transactional databases. Some parameters here are below.
- Support: how popular an itemset is
- Confidence: how likely item Y is purchased when X is purchased
- Lift:How likely item Y is purchased when item X is purchased, while controlling for how popular item Y is.

![GitHub](https://github.com/zhangyingchi/BlackFriday/blob/chi-zhang/image/product_rules.png)


## 4. Personalized recommendation system
In order to construct a precise recommendation system within limited features, we came up with
a model that requires only users ID, product ID and rating of customers based on purchased
amount, which is called Matrix Factorization.

This model can help our client gain market insights of each customer’s opinion for each product and thus give correct recommendations. What’s more, our output could be valuable information to be applied to further research such as customers’ purchase behaviors trending analysis and influential factors testing on customers’ purchase behaviors.

-----------------
<div align="center">
  <img src="https://github.com/zhangyingchi/BlackFriday/blob/chi-zhang/image/poster.jpg">
</div>

