
# Online Gambling Advertisment Image Prediction Using CNN

This model is built with a system that can predict images of online gambling ads and non-gambling ads using Convolutional Neural Network.


## This model project is built using:

- TensorFlow
- KERAS

## Step by Step

- Sample (Get the dataset)
- Explore (Explore the dataset, find an anomaly, image cleaning)
- Modify (Normalitation, Labelling, Split)
- Model (Create model using CNN Architectur Standard using TensorFlow - KERAS)
- Access (Train the model (epoch 10,15,20), evaluation, prediction)

## Dataset

![Screenshot](https://raw.githubusercontent.com/marssihsaan/model-cnn-deteksiiklanjudi/main/Screenshot%202024-07-15%20105510.png)

## Dataset Visualization

![Screenshot](https://raw.githubusercontent.com/marssihsaan/model-cnn-deteksiiklanjudi/main/Screenshot%202024-07-15%20110116.png)

## Normalization, Labelling, Split
- Normalization output (0-1 binary for classification)

```bash
  (array([[[[0.9764706 , 0.9764706 , 0.9764706 ],
          [0.9764706 , 0.9764706 , 0.9764706 ],
          [0.9764706 , 0.9764706 , 0.9764706 ],
          ...,
          [0.22405073, 0.2513265 , 0.19455135],
          [0.25674307, 0.30136576, 0.23203364],
          [0.4257755 , 0.47810394, 0.3813515 ]],
 
         [[0.9764706 , 0.9764706 , 0.9764706 ],
          [0.9764706 , 0.9764706 , 0.9764706 ],
          [0.9764706 , 0.9764706 , 0.9764706 ],
          ...,
          [0.2146269 , 0.26340142, 0.19799086],
          [0.26851305, 0.32625037, 0.25785413],
          [0.3424551 , 0.421009  , 0.32309234]],
 
         [[0.9764706 , 0.9764706 , 0.9764706 ],
          [0.9764706 , 0.9764706 , 0.9764706 ],
          [0.9764706 , 0.9764706 , 0.9764706 ],
          ...,
          [0.21381165, 0.26644647, 0.21157514],
          [0.27634853, 0.3496022 , 0.28419167],
          [0.2892329 , 0.38475987, 0.29346088]],
 ```
- Labelling (0 & 1)

![Screenshot](https://raw.githubusercontent.com/marssihsaan/model-cnn-deteksiiklanjudi/main/Screenshot%202024-06-04%20105944.png)

Non Judi Online = 1 ;
Judi Online = 0

- Split Data

```bash
  train_size = int(len(data)*.7)
  val_size = int(len(data)*.2)
  test_size = int(len(data)*.1)
 ```  

## Modelling

```bash
model.add(Conv2D(16, (3,3), 1, activation='relu', input_shape=(256,256,3)))
model.add(MaxPooling2D())
model.add(Conv2D(32, (3,3), 1, activation='relu'))
model.add(MaxPooling2D())
model.add(Conv2D(16, (3,3), 1, activation='relu'))
model.add(MaxPooling2D())
model.add(Flatten())
model.add(Dense(256, activation='relu'))
model.add(Dense(1, activation='sigmoid'))
 ```
## Access (Evaluation, Result Prediction)

- Using Accuracy for easy interpretetaion

| Epoch | High Accuracy     | Avarage Accuracy |
| :-------- | :------- | :---------------------|
| 10 | 89%  | 73% | 
|  15 | 99%  | 87% |
|  20 | 100% | 88% |

- Result Prediction:

![Screenshot](https://raw.githubusercontent.com/marssihsaan/model-cnn-deteksiiklanjudi/main/Screenshot%202024-06-05%20143428.png)
