# Using Decision Trees to optimize marketing campaign performance

We use Bank Marketing Dataset from the UCI Machine learning repository to demonstrate ***how Decision Trees can be leveraged for indentifying combination of promising consumer attributes*** (Demographic, Technographic, Geographic & Psychographic) for desired outcome (in our case conversions)

Digital marketing campaigns, segmentation and personalization have evolved dramatically over the past decade with availaibilty of data. One on going need continues to be to find insights that help further optmize performance of ongoing marketing campaigns. 

## Step 1 
We explore and visualize Conversion Rate by Education, Marital status, Job and Campaign. We also determine the overall conversion rate (11.70%)
## Step 2
To prep the data for Machine learning, we preprocess & encode non-numerical columns using Pandas and Scikit learn and drop featuers that have high 
## Step 3
Fit the decision trees with Max Depth 4
## Step 4 
Output of Decision Tree
![Screen Shot 2022-11-17 at 6 27 22 PM](https://user-images.githubusercontent.com/80999165/202605135-139a632c-3358-437b-87b0-e067c6ba2916.png)
## Interpreting the output of Decision Tree

Let's take a closer look at the above diagram. Each node contains five lines that describe the information that the given node has. 
1. The top line tells us the criteria of the split. The root node, for exampl, is split into its child nodes base don the value of the *previous* variable. If the value of the this *previuos* variable is less then or equal to 0.5 then it goes to the left child. 
2. The second line tells us the value of the qualiyt measure for the split. Here we selected the gini impurity measure for the criteria, so we can see the changes in the impourty measures in each node from the second line.
3. the fourth line in each node tells us the composition of the records in two different classes. The first element stands for the number of records in the non-conversion group, and the second element stands for the number of records in the conversion group. 

## Insights
Now that we know what each of the lines in each nodes mean, we can now draw insight from this tree graph. In order to understand the customers the belong to each leaf node, we need to follow thorugh the tree. 

**Insight 1** 

Those customers that belong to eight leaf node from the left are those with a 0 value for the *previous* variable, age greater thatn 60.5, a martial_divorced variable with a value of 1, and a job-self-employed variable with a value of 1. 
In other words, those ***who were not contacted before this campaign and who are older than 60.5, not-divorced, and self-employed*** belong to this node and ***have very high chance of converting***

![Screen Shot 2022-11-17 at 7 36 42 PM](https://user-images.githubusercontent.com/80999165/202612343-1b304370-be05-4d75-933a-f6a7dbe23b63.png)

**Insight 2** 

Second example. Those customers that belong to the second leaf node from the right are those wiht a value of 1 for the previous variable, a value of 1 for the housing variable, age greater thatn 60.5 and balance less than equal to 4660.5. In other words, those customers that were contacted before this campaign and that have a housing loan, are older thatn 60.5, and have a bank balance less thant 4660.5 belong to this node and 20 out of 29 that belong this node have converted and subscribed to the offer. 

![Screen Shot 2022-11-17 at 7 53 36 PM](https://user-images.githubusercontent.com/80999165/202613176-5399c022-9303-4a1c-aac6-0ae742e9f7ad.png)



