# deep-learning-challenge
Homework 21 for the deep learning challenge module of Datavis bootcamp

# Alphabet Soup Charity Funding Predictor

## Overview of the analysis: 
This project aims to develop a binary classifier using neural network models for the fictional nonprofit foundation Alphabet Soup which wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With the dataset provided, a binary classifier was created to predict whether applicants will succeed if funded by Alphabet Soup.

The dataset received is a CSV containing over 34,000 organizations that have received funding from Alphabet Soup. Within this dataset are several columns that capture metadata about each organization, such as:

<img width="646" alt="image" src="https://github.com/priyajainnyc/deep-learning-challenge/assets/124069684/41aa4755-0f32-44de-9f8f-67e2f40127ed">

## Results For Optimized Model:

### Data Preprocessing

* After running the model with different combinations of features, the features that hold the majority of the signal required for the model to achieve the target model performance are:
    * ```NAME```  
    * ```APPLICATION_TYPE```
    * ```AFFILIATION```
    * ```CLASSIFICATION```
    * ```USE_CASE```
    * ```ORGANIZATION```
    * ```INCOME_AMT```
    * ```ASK_AMT```
* On the other hand, the features that hold minor to no significance for the model to performance are:
    * ```EIN ```
    * ```STATUS```
    * ```SPECIAL_CONSIDERATIONS```  
* For the purpose of this project, the target variable that is being predicted is  ``` IS_SUCCESSFUL```

### Compiling, Training, and Evaluating the Model

* The Optimized Neural Network Model was defined as follows:
   * <img width="904" alt="image" src="https://github.com/priyajainnyc/deep-learning-challenge/assets/124069684/f24c69d6-4c7f-433d-b065-3cc0c7e3d8fe">
   * Since a binary classifier needed to be built,  the sigmoid activation function was used for the output layer. Sigmoid reduces the output to a value from 0.0 to 1.0, representing a probability.
   * Since the model achieved the target performance during the first epoch and to reduce the training time per epoch, fewer neurons were used
   * <img width="669" alt="image" src="https://github.com/vasabril98/deep-learning-challenge/assets/120423945/1837a460-7682-49a4-a18d-0d4ecb6cabb8">
   * The binary_crossentropy loss function was used since it is purpose-built for binary classifiers. A metric to ‘accuracy’ so accuracies computed by the loss function are captured in the history object returned by fit.
   * The model only trained for ten epochs since the model achieved the target performance during the first epoch and showed little to no improvement in accuracy after the three epochs.
   * <img width="805" alt="image" src="https://github.com/vasabril98/deep-learning-challenge/assets/120423945/564d7be8-c268-4b18-800d-21925bbebd19">

   * One significant change that was added to increase the model performance was adding the ```NAME``` feature back as an input during the model optimization. Due to this change, a significant improvement in the model performance was noticed.

## Summary:
* In this project, a binary classification model was built using Neural Networks. Before optimizing the model, the accuracy was approximately 73%. However, after optimizing the model, the target performance was achieved with an accuracy of over 79%.

* After researching binary classifiers (models that are trained with datasets labeled with 1s and 0s representing the two classes), other popular learning algorithms that do well with binary classification were found, including logistic regression, Naïve Bayes, and k-Nearest Neighbor. Future work of this project would include comparing the performance of the optimized neural network model against the other machine learning models that typically perform well on binary classification. 
