# Neural Network Charity Analysis

## Overview of Analysis

The purpose of this analysis is to try to determine whether an applicant will be successful or not with the funding they receive from Alphabet Soup. The data for this project was from 34,000 organizations with all of their information in the charity_data.csv. In order to determine if a charity will benefit from funding from Alphabet Soup, a machine learning model using a neural network was used to create a binary classifier for sucessful charities.

### Neural Network

A neural network or deep learning model is a type of machine learning that utlizings a structure similar to the human brain, with neurons organized in layers and an acitvation function to return a single clear output.In order to use a neural network, all of the data has to be preprocessed and formatted so that the model can correctly interpret the information. All unnecessary columns were removed such as the "NAME" and "EIN" columns. Another step of processing data for a neural network is "binning" which combines values with few numbers from a particular column into an "other" category. This was done for the application type column since some of the applicate types had very few values. Several columns were binned. Another step of preprocessing data is OneHotEncoding, which is the process of changing necessary categorical data into a binary format so that the model can understand it. This was done for the dataset and finally the model could be created and compiled.

## Results

There is a lot of work that goes into designing a neural network, which activation functions to use and which variables are valuable. The y variable was the "IS_SUCCESSFUL" column and the X variable was all of the other remaining columns after preprocessing.

### Compiling, Training and Evaluating

The data was then split into training and testing sets and scaled. The first neural network model was created with two hidden layers with 80 and 30 neurons respectively. The activation function for the hidden layers was "relu" and the activation function for the output layer was "sigmond" since a binary outcome was wanted.
![Preliminary NN Model Structure](https://github.com/likenberry/Neural_Network_Charity_Analysis/blob/main/Resources/Preliminary_nn_model.png)
The model was compiled and trained using 100 epochs with checkpoints inserted so that the model wouldn't have to run all the way through and shared with others. The accuracy and loss was calculated and seen in the output below.
![Preliminary NN Model Output](https://github.com/likenberry/Neural_Network_Charity_Analysis/blob/main/Resources/Preliminary_nn_output.png)
The accuracy of the model was only around 72% which isn't ideal or very useful so steps were taken to try and optimize and improved the accuracy of this model. Three more attempts were made to improve the performance of this model.

- The first optimization was adding another hidden layer with 10 neurons. This is what the model looked like with the third hidden layer.![Optimazation 1 Model](https://github.com/likenberry/Neural_Network_Charity_Analysis/blob/main/Resources/Opt1_nn_model.png) The accuracy and loss of this model was around the same without the third hidden layer at about 72%.![Optimazation 1 Output](https://github.com/likenberry/Neural_Network_Charity_Analysis/blob/main/Resources/Opt1_nn_output.png)

- The second optimization was adding more neurons to each hidden layer. This is the structure of the model after the second optimzation. ![Optimazation 2 Model](https://github.com/likenberry/Neural_Network_Charity_Analysis/blob/main/Resources/Opt2_nn_model.png) The model was compiled and the accuracy and loss was calculated. ![Optimazation 2 Output](https://github.com/likenberry/Neural_Network_Charity_Analysis/blob/main/Resources/Opt2_nn_output.png) Adding more neurons did not increase the accuracy of this model since the accuracy stayed around 72%.

- The third and final optimazation was increasing the number of epochs or times the model was run. The epochs were increased from 100 to 200 with the same model structure from optimazation 2. The accuracy did not improve with this optimazation either remaining at 72%. ![Optimazation 3 Output](https://github.com/likenberry/Neural_Network_Charity_Analysis/blob/main/Resources/Opt3_nn_output.png)

## Summary

As seen with the original model and the three attempts at optimization, the accuracy of this model was always around 72% which means that this model was only able to correctly label a successful applicant 72% of the time which is not ideal in a real world situation. There are more ways that this model could be tweaked to maybe improve the performance but there are also other models that could be tried on this data that might be more successful. A logistic regression model or a random forest model could be tried since both work well with binary outcomes. Sometimes a simpler model is better than a more complicated deep learning or neural network model. It's better to start simple before going more complicated.

## Resources

- Data Source: charity_data.csv
- Software: Visual Studio Code (version 1.63.2), jupyter notebook
