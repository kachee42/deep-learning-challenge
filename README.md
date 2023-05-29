# deep-learning-challenge

## Overview

There are many companies and organizations seeking funding to meet their goals. Any organization looking to fund these organizations wants to know that the money contributed will be used effectively. To that end, the code in this repository is designed to evaulate the likeliness of success or failure of the goals of the organizations based on several different features of the application for funding of past applications, including the type of application, the affiliation of the organization, the classification of the organization, the use case of the funding, the type of organization, whether the organization is currently active, the income of the organization, whether there are any special considerations for the funding, the amount requested, and whether the goal was met. 

## Results

### Data Preprocessing

- The success of the funded ventures was isolated as the target feature of the dataset.
- Employer identification Number (EIN) and organization name were removide from the dataset as irrelevant to the success or failure of the organization's goals.
- Application Type, affiliation, classification, use case, organization type, current status of the organization, income of the organization, special considerations for the application, and amount requested were left as the features.
- Application type and classification categories were encoded using "get_dummies" to turn the non-numerical variables into numerical ones.
- Application types and classifications with fewer occurences were grouped in bins based on their frequency.
- Some variation in groups of application types and classifications were tried in order to optimize the model.

### Compiling, Training, and Evaluating Model

- The initial model was created with 3 total layers: the input layer, one hidden layer and the output layer, with 6 nodes in each of the first two layers and relu activation in the first two and sigmoid acitivation in the output layer.
- Model performance did not achieve the 75% accuracy target, instead reaching about 73% accuracy when checked against the test data.
![image](https://github.com/kachee42/deep-learning-challenge/assets/118322354/40a43c14-ff54-42ca-8edc-42695fb444d7)
- In attempts to increase the accuracy a few different methods were employed: more bins for the less frequently occuring application types and classifications were created and Keras tuner was employed several times with varying numbers of layers and neurons to determine the best numbers of layers and neurons per layer. The below images show the number of neurons per layer for each of 3 different attempts.
- ![image](https://github.com/kachee42/deep-learning-challenge/assets/118322354/afb614e9-5b03-4359-be35-09230d1bc034)
- ![image](https://github.com/kachee42/deep-learning-challenge/assets/118322354/ac18b509-2c9d-448e-8381-2760f52d3fec)
- ![image](https://github.com/kachee42/deep-learning-challenge/assets/118322354/6d43cef2-5f53-4ee6-bb50-4e5c819c22ab)
- Unfortunately the changed binning of the application types and classifications along with the optimized neural network models did not seem to improve the overall performance of the model.
- Note that the models uploaded in this repository do not represent all of the attempts made to optimize the performance of the model. Several other atttempts were made, some of which slightly improved the accuracy of the training data, but none of the models improved on the performance of the model when checked with the test data.

## Summary

The accuracy and loss of the 3 models are shown in the images below.
![image](https://github.com/kachee42/deep-learning-challenge/assets/118322354/14265704-ad18-4fc3-8bb1-cd581a3815fc)
![image](https://github.com/kachee42/deep-learning-challenge/assets/118322354/606e5d97-72db-44ea-875d-bbbc20381550)
![image](https://github.com/kachee42/deep-learning-challenge/assets/118322354/634e3363-501b-4e33-abb5-f913426ffcd4)

The limited accuracy of these models suggests that there must be other factors that are unaccounted for in the data. While these variations could possibly be accounted for with a factor that might be gatherable and therefore could be added to the model to increase the accuracy, but the success or failure of a project may not be entirely deteriminable based on easily recorded data, such as the ability level of the people undertaking the project. To improve the accuracy of the model, it may be necessary to gather more data on the track record of the organizations requesting the funding. Whether the organizations have been succussful in the past may very well be a better indicator of the success of future projects than the provided data.
