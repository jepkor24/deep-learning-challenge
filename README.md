# Deep-Learning-Challenge Background
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks
# Overview of the Project

The purpose of this analysis is to develop a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.  The data set contains information about the application	EIN	NAME, APPLICATION_TYPE, AFFILIATION	CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT	and IS_SUCCESSFUL . By accurately predicting the success of applicants, Alphabet Soup can optimize its funding allocation and increase the impact of its efforts.  

## Analysis 
Data Preprocessing:  
- The variable that is used as the target for the model = IS_SUCCESSFUL.  
- The variables used for features:  
    - APPLICATION_TYPE,
    - AFFILIATION,
    - CLASSIFICATION,
    - USE_CASE,
    - ORGANIZATION,
    - STATUS,
    - INCOME_AMT,
    - SPECIAL_CONSIDERATIONS,
    - ASK_AMT
- The variables removed from the input data due to being targets or not beneficial columns are:
    - IS_SUCCESSFUL,
    - EIN,
    - NAME
- The two models used to check their effectiveness are 
    1.   Best Model from Hyperparameter Tuning
    2.   Custom model  

**1 . Best Model from Hyperparameters Tuning:**  
         - Input layer = 43 units
         - Hidden Layers = 5 with varying units (7,1,1,3,7)  
         - Activation Functions used = Tanh on all 
         - Output Layer = 1 unit with Sigmoid activation
    **Evaluation Results :**  **Loss:** 0.5555  and **Accuracy:**  0.7316  

**2. Custom Model:**  
         - Input layer = 43 units
         - Hidden Layers = 3 with varying units (10,5,3)  
         - Activation Functions used = ReLU, ReLU, Tanh 
         - Output Layer = 1 unit with Sigmoid activation
    **Evaluation Results :**  **Loss:** 0.5560  and **Accuracy:**  0.7303  
- The best model from hyperparameter tuning is deeper with 5 hidden layers, while the custom has 3 hidden layers. Varied the number of hidden layers to see the performance of the model.   
- Both models have different activation functions in their hidden layers as shown above and the custom model has more units in the first hidden layer compared to the best model
- The number of epochs used varied i.e. 250 for the custom model and 100 for the best model from hyperparameter. I did try to increase the number of epochs for the best model but it did not yield a higher accuracy score.

## Results
- The best model achieved an accuracy of 73.16%, while the custom model achieved an accuracy of 73.03%.
- The difference in accuracy between the two models is marginal, with the best model performing slightly better.
The best model's training time took longer due to the hyperparameter tuning process but yielded slightly higher results.

## Conclusion

Both models perform similarly in terms of accuracy, with the best model from hyperparameter tuning slightly outperforming the custom model.
The best model from hyperparameter tuning has a more complex architecture with a larger number of hidden layers and different activation functions, potentially allowing it to capture more complex patterns in the data. It took about 22mins and 58 secs to use the best model while the custom model only took 6 mins and 38 sec. And therefore, custom model would be preferred method to use due to its computational time and the accuracy since the difference in accuracy is marginal.   
Another model that would be suitable to be used for modeling would be the use of the Random Forest classifier. This is because Random Forest is relatively easy to implement and requires minimal hyperparameter tuning compared to neural networks. In addition Random Forest provides feature scores that can allow the identification of the most relevant features for predicting success of the funding applicants  and the information can be very valuable in decision making process 