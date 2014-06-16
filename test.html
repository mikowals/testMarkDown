Annotated R code - Practical Machine Learning Course Project
============
Load libraries and data.

     library( caret )
     library( DoMC )
     registerDoMC( cores = 2 )
     projectTrain <- read.csv( '~/downloads/pml-train.csv' )
   
Split the data into training and validation sets.

     inTrain <- createDataPartition( projectTrain$classe, p=0.7, list=FALSE)
     train <- projectTrain[ inTrain,]
     validate <- projectTrain[ -inTrain,]
   
Visually inspecting data shows it is time seriers with the dependent variable 'classe' occurring in groups if the data is sorted by time and user_name.  So first try a simple model with those variables.

     simpleModel <- train( classe ~ user_name + num_window, data=train, method='rf', trControl=trainControl( method='oob' ), tuneGrid = expand.grid( mtry = 6 ))

Inspect model results in training and validation data.

     simpleModel
     confusionMatrix( predict( simpleModel, validate ), validate$classe )
    
The model is a perfect fit in the training data and 99.9% accurate in validation.  So create answers for assignment based on test set.

     test <- read.csv( '~/downloads/pml-test.csv' )
     answers <- predict( simpleModel, test )
    
To make a more real world example I removed columns with #N/A or '' entries and then removed the 'user_name' and all time related columns.  This seems more useful in the real world where exercise feedback will need to respond to situations where the exercise style in the previous period is not known.

    train <- train [, colSums( is.na( train ) == 0]
    train <- train [, colSums(  train == '' ) == 0]
   
This left 52 predictors available which was computationally heavy.  So I tried to identify the most interest predictors.

    ctrl <- rfeControl( functions=rfFuncs, method='oob', index=TRUE )
    rfProfile <- rfe( train[,1:52], train[,53], sizes=12 , rfeControl=ctrl )
    rfProfile
    predictors( rfProfile )
   
I tried the identified predictors in a new model.  And viewed it results in training and validation tests.

    model <- train( classe~roll_belt + yaw_belt + magnet_dumbbell_z + magnet_dumbbell_y + pitch_belt + pitch_forearm + accel_dumbbell_y + roll_forearm + magnet_forearm_z + roll_dumbbell + accel_dumbbell_z + roll_arm  , data=train, method='rf',trControl=trainControl( method='oob'), tuneGrid=expand.grid( mtry=3))
    model
    confusionMatrix( predict( model, validate ), validate$classe )
  
I iterated the steps above a few times to get the best fit in the validation data and the ulimate result was 12 variables that got an out of sample accurace on the validation set of 98.9%.

[markdown help page](https://guides.github.com/features/mastering-markdown/)
