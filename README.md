# deep-learning-challenge
UNC Module 21 Challenge

## Report

### Overview
This analysis is to evaluate the tool created to help the Alphabet Soup foundation select applicants for funding with the best chance of success in their ventures.  I am going to show how I designed the tool and the steps taken to optimize it.

### Results
#### Data Preprocessing
* Target variable: "IS_SUCCESSFUL" column
* Feature variables for final model:
  * NAME
  * APPLICATION_TYPE
  * AFFILIATION
  * CLASSIFICATION
  * USE_CASE
  * ORGANIZATION
  * INCOME_AMT
  * ASK_AMT
* Variables removed for final model:
  * EIN
  * SPECIAL_CONSIDERATIONS
  * STATUS

#### Compiling, Training, and Evaluating the Model
* The final model had three layers, with the first layer having 105 neurons, the second having 35 neurons, and the third layer having 10 neurons.  The first layer used relu as the activation function, while the second and third layer used sigmoid activation functions. I used relu and sigmoid activation functions because they both worked with values between 0 and 1.  The relu function in the first layer helped simplify the output for the sigmoid functions, which works best with probabilities, and since we are trying to find the probability that a venture is successful, it works well.  I used 150 total neurons because in the original model there were 44 input features, and we learned that you should use 2-3 times as many neurons as input features.
* I was able to achieve the goal of 75% accuracy in my final model, with the model achieving 79% accuracy.
* In order to improve the model's accuracy, I added a third layer and changed the activation function of the second and third layer to sigmoid.  When this didn't improve the accuracy, I then re-evaluated some of the columns to see if I could remove any of them, and found that the Name column could be kept while the SPECIAL_CONSIDERATIONS and STATUS columns had almost no variation and could be safely removed from the final model.  This combined with changing the layer neuron counts allowed me to achieve 79% accuracy with my model.

### Summary
My final model was able to achieve 79% accuracy, which is significantly better than the original model, which could only achieve 72% accuracy.  I was able to do this by adding layers, changing the activation functions on my layers, and editing the feature variables and removing a couple of variables.  

If I was looking for an alternative to the neural network, I might look at a decision tree model, since that uses true/false questions, which we used in our neural network.  And since this a non-linear relationship in our data, a decision tree would help us map this relationship and trace the decision logic through branches.  You can also do pruning to help clean up the model, like how we cleaned up the dataset before the final model was successful.  
