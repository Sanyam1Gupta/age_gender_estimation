# Age Gender Estimation

## The goal of this project is to train a Convolutional Neural Network for predicting the age and gender of people.

## NOTE- The 'train_age_and_gender.ipynb' was run on Google Collaboratory to make use of the GPU provided by it for training the model.Thus the starting lines of this file had been written to enable Google Collaboratory to make use of the files from my google drive. These starting lines may be removed if you wish to use file by cloning this repository.

## Requirements-
#### 1.) Keras-
An open source Neural Network library
#### 2.) TensorFlow-
An open source Machine Learning Framework
#### 3.) Various Python libraries and packages such as 'pandas','numpy','scikit-learn','SciPy' and 'HDF5'.

## Dataset for training- 
#### The IMDB dataset was processed to generate 'imdb_db.mat'.The pre-processed dataset is available at my google drive link https://drive.google.com/open?id=16_koz1epvMZbWPEtHuMhVPsFE_dmeV67 .

## Important Points-
#### 1.) The project makes use of Transfer learning. It refers to the technique of using knowledge of one domain to another domain.i.e. a Neural Network model trained on one dataset can be used for another dataset by fine-tuning the former network.
#### 2.) The project makes use of the pre-trained weights(model) on UTKFace dataset.The pre-trained weights are available at https://github.com/yu4u/age-gender-estimation/releases/download/v0.5/weights.29-3.76_utk.hdf5 .This model is 'model'.
#### 3.) The last 3 layers of 'model' are not used and 4 new layers are added to it to get a 'model_custom".
#### 4.) Only the last three dense layers of 'model_custom' are fine tuned as per our requirement. All the layers of the 'model_custom' are made non-trainable except the last three layers.

## Model Architecture-
#### All the layers of pre-trained UTKFace dataset are used as such except the last 3 layers which are removed .4 new layers are added to it to get a 'model_custom".
#### These 4 new layers are-
#### 1.) flatten (type=Flatten) of output shape (None, 131072)
#### 2.) fc1 (type=Dense)  of output shape (None, 128)-- fully connected layer
#### 3.) gender (type=Dense) of output shape (None, 2)-- to output predicted gender
#### 4.) age (Dense) of output shape (None, 101)-- to output predicted age
