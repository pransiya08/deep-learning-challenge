# Deep Learning Challenge

# Overview
Using machine learning and neural networks, this tool can be used to identify which applicants for funding will have the best chance of success in their ventures. Given the CSV of 34,000 organisations that have received funding previously, the file is preprocessed first by cleaning it up and removing unwanted columns, scaled the data, categorical values were converted into numerical dummies, and the data was split into training and testing sets. Once preprocessed, the training data were used to train the model. The accuracy of the model was improved to achieve the target of 75% by changing the model parameters. Once done, the testing data was fit into the model and the Loss and Accuracy parameters were calculated. It was then exported as an HDF5 file.

# Results
* Data Preprocessing
    * Target Variables: 'IS_SUCCESSFUL'
    
        The target variable for this model is to identify if a project is successful or not 

    * Features: 
    
        The features considered for this are the Application Type, Affiliation, Classification, Use Case, Organisation, and Special Considerations. These are all categorical variables which were then transformed to numerical using pd.get_dummies
      

    * Removed Variables: 
    
        In terms of accuracy, out of all the predictions that the model made, 99% of them are correctly predicted.
      
* Compiling, Training, and Evaluating the Model
    * Neurons: 150 (Layer 1), 30
    * Layers:
    * Activation Functions:
        The model predicts healthy loans ('0') correctly all the time, whereas, predicting high-risk loans (1) is only correct 85% of the time.
      
    * Model Performance:
        The model predicts healthy loans ('0') correctly all the time, whereas, predicting high-risk loans (1) is only correct 85% of the time.

    * Optimising Performance:
    
        The initial parameters of the model are Layer 1 with 100 hidden nodes, Layer 2 with 30 hidden nodes, and epochs of 100. This resulted in a model with a loss of 0.5608 and an accuracy of 0.7248, which is a bit far from the target accuracy of 75%.
      To optimise the model and increase its accuracy, certain parameters were adjusted:
      * Layer 1 - from 100 neurons, it was increased to 150. Increasing it more than this number resulted in a decrease in the accuracy. Also to avoid overfitting, no more adjustments were made to Layer 1's hidden nodes.
      * Layer 2 - adjusting this layer showed a decrease in the model's accuracy. This layer was kept to its original value of 30 neurons.
      * Number of epochs - increased to 200 as it showed the most accurate result. Increasing it further resulted in an accuracy that is not significantly different when it is set as 200.
      * Batch Size - set to 150 to fit the model in a more optimised manner. Increasing it to more than 150 did not really affect the accuracy significantly.

    * Accuracy: '0.99'
    
        In terms of accuracy, out of all the predictions that the model made, 99% of them are correctly predicted.       


# Summary
