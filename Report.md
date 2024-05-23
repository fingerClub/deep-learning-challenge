# Deep Learning Optimization Report (Module 21)

## Overview of the Analysis

The purpose of this analysis is to assess the effectiveness of the Neural Network model in selecting the applicants with the best chance of success in their ventures. A Neural network model was made using TensorFlow with features selected to predict if applicants were successful in their venture as signified with a 1 in the IS_SUCCESSFUL label.

## Initial Model

The features selected were all columns except IS_SUCCESSFUL, EIN, and NAME for the intial model. Because the CLASSIFICATION and APPLICATION_TYPE features had the most unique values, further analysis was conducted on those two features. There was a skew in both CLASSIFICATION and APPLICATION_TYPE. For instance, Most applications were T3s with them making up 27037 of all applications with 276 being applications that are grouped in an "Other" category for their individual total amounts were less than 160 for all applications. Likewise, with classification, there were 71 different classifications, an aggregate of those less than 800 equating to 2261 of the total applications and were placed in an "Other" Group.


The layers were all activated with a sigmoid activation as follows:

  layer1 = tf.keras.layers.Dense(input_dim=43, units=129, activation='sigmoid')
  nn.add(layer1)
  # Second hidden layer
  #  YOUR CODE GOES HERE
  layer2 = tf.keras.layers.Dense(units=258, activation='sigmoid')
  nn.add(layer2)

  # Output layer
  #  YOUR CODE GOES HERE
  layerOut = tf.keras.layers.Dense(units=1, activation='sigmoid')
  nn.add(layerOut)

A large amount of units were added to compensate for the ammount of categories and features. This resulted in an accuracy of 0.7271 and a loss of 0.5573 for the initial model.

* all models were fitted as follows: nn.fit(X_train_scaled, y_train, epochs=50, batch_size=600, validation_split=0.2)

## Optimzation

In short, Optimization of above .75 accuracy was not achieved but the foillowing results were achieved: accuracy: 0.7318 - loss: 0.5731 which indicates a .0047 increase. the following methods were tested to increase optimization: 
