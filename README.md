# titanic

## Titanic dataset:
This is a titanic dataset that has the following information:
* survived : if the passenger survived or not
* Pclass: range from 1-3
* Name: name of the passengers
* Sex: male/female
* Age: age of the passenger
* Siblings/Spouses Aboard
* Parents/Children aboard
* Fare

I later added a column "relatives" to capture how many relatives the passengers have. "relatives" = "Siblings/Spouses Aboard" + "Parents/Children aboard"

## Step 1: exploring the data
1) I built a bar chart to capture the relationship between sex and class. We could see that most passengers are males (across all classes)
2) I then tried to build another plot to see if sex could be a factor that affected survival rate.  Across all classes, I could see that more females survived than males. 
3) I then used a swarm plot to plot together age, class, and the survival of passengers. 
4) After creating a column called "relatives", I built another plot to see if number of relatives on board would also affect the passengers' survival rate. 

## Step 2: building machine learning models
Goal: building a models to predict if a passenger can survive. 

1) I used keras to build a neural network. The first layer has 15 nodes, and the second layer has 25 nodes. I also used "binary crossentropy" as my loss function because we are classifying "survived" and "not survived" of passengers. I noticed that the model that I first built has 83.9 testing accuracy rate. After building the model, I also experienced with different number of nodes, and I noticed that even if I increased the nodes to 40 or 50, the testing accuracy rate did not improve much. That means a less complex model is sufficient for our data. 

2) I also spent some time experimenting using drop out layers. Adding drop out layers could improve the testing accuracy and reduce overfitting. 

3) I then tried to build a logisitic regression function to predict if a passenger can survive and evaluated the model by using a confusion matrix. We could see that 34 people were wrongly classified as "not survived" while 22 people were wrongly ckassified as "survived". 

4) Next, I tried to build a random forest model. The accuracy rate of random forest initially was 0.81, and after hypter parameter tunning, the testing score became 0.83 and the training score became 0.88. 