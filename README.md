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
    
        The removed variables are the EIN and the Name.
      
* Compiling, Training, and Evaluating the Model
    * Neurons: 150 (Layer 1), 30 (Layer 2)
    * Layers: 2
    * Activation Functions: Sigmoid
        These parameters proved to be the most effective ones to use in optimising the deep learning model.
      
    * Model Performance: Loss = 0.5274 | Accuracy = 0.7442
        The target performance of 75% was not achieved, despite several attempts to optimise the model.

    * Optimising Performance:
    
        The initial parameters of the model are Layer 1 with 80 hidden nodes, Layer 2 with 30 hidden nodes, and epochs of 100. This resulted in a model with a loss of 0.5608 and an accuracy of 0.7248, which is a bit far from the target accuracy of 75%.
      To optimise the model and increase its accuracy, certain parameters were adjusted:
      * Layer 1 - from 100 neurons, it was increased to 150. Increasing it more than this number resulted in a decrease in the accuracy. Also to avoid overfitting, no more adjustments were made to Layer 1's hidden nodes.
      * Layer 2 - adjusting this layer showed a decrease in the model's accuracy. This layer was kept to its original value of 30 neurons.
      * Number of epochs - increased to 200 as it showed the most accurate result. Increasing it further resulted in an accuracy that is not significantly different when it is set as 200.
      * Batch Size - set to 150 to fit the model in a more optimised manner. Increasing it to more than 150 did not really affect the accuracy significantly.

# Summary
Before training the machine learning model, the data were first preprocessed and standardised to achieve a minimal loss and the highest accuracy possible. After that, the training data were fed into the model and check the initial loss and accuracy values. Based on these, the model was optimised by changing the parameters of the neurons, layers, epochs, and adding a batch size. Changing these parameters allowed our model to have an increase in accuracy from 72% to 74%. However, this accuracy is still lower than the target of 75%. As a recommendation to achieve the model's target performance, adding a few more layers and neurons can be done but with extreme caution as to avoid overfitting. Once changed, the batch size and number of epochs can also be amended to optimise the model's accuracy and loss.
