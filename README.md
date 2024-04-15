# Deepfake-Detection-using-CNN-RNN
### Our Model Accuracy ~82%
Overall, the "Deepfake Detection using CNN-RNN" model leverages the powerful feature extraction capabilities of the Xception model, along with the sequence processing capabilities of the GRU RNN layer, to effectively detect deepfake images. The model is trained using SGD as the optimizer to minimize the classification loss on the training data.

### Feature extraction - ![image](https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/ed6bcceb-e974-4550-bca3-d2c39118e77f)


https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/56cbdf5e-9c65-4bef-8bfe-04006e62236c



## Real and Fake images
![image](https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/28d1ecc1-c108-44d2-93fb-c326a385f078)

## Deepfake model for Images

### Dataset - https://www.kaggle.com/datasets/dagnelies/deepfake-faces
![image](https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/997fca74-0141-4640-ab79-c71d779627b5)


### Model -

| Layer (type)                  | Output Shape       | Param #    |
|-------------------------------|--------------------|------------|
| conv2d_3 (Conv2D)             | (None, 224, 224, 64) | 9,472      |
| max_pooling2d_2 (MaxPooling2D)| (None, 112, 112, 64) | 0          |
| conv2d_4 (Conv2D)             | (None, 112, 112, 128)| 73,856     |
| conv2d_5 (Conv2D)             | (None, 112, 112, 128)| 147,584    |
| max_pooling2d_3 (MaxPooling2D)| (None, 56, 56, 128)  | 0          |
| flatten_1 (Flatten)           | (None, 401408)       | 0          |
| dense_3 (Dense)               | (None, 128)          | 51,380,352 |
| dropout_2 (Dropout)           | (None, 128)          | 0          |
| dense_4 (Dense)               | (None, 64)           | 8,256      |
| dropout_3 (Dropout)           | (None, 64)           | 0          |
| dense_5 (Dense)               | (None, 1)            | 65         |

#### Total params: 51,619,585 (196.91 MB)
#### Trainable params: 51,619,585 (196.91 MB)
#### Non-trainable params: 0 (0.00 B)



### loss curve - 

![image](https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/c3464783-87d5-48c3-99d2-3a710c58ce89)

## Deepfake detection for Videos

### Dataset - https://www.kaggle.com/competitions/deepfake-detection-challenge/data
![image](https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/0838a494-70c4-436d-83d1-ea45ce42d14a)


### Model -

| Layer (type)   | Output Shape     | Param # | Connected to       |
|----------------|------------------|---------|--------------------|
| input_layer_4  | (None, 20, 2048) | 0       | -                  |
| (InputLayer)   |                  |         |                    |
| input_layer_5  | (None, 20)       | 0       | -                  |
| (InputLayer)   |                  |         |                    |
| gru (GRU)      | (None, 20, 16)   | 99,168  | input_layer_4[0]… |
|                |                  |         | input_layer_5[0]… |
| gru_1 (GRU)    | (None, 8)        | 624     | gru[0][0]          |
| dropout        | (None, 8)        | 0       | gru_1[0][0]        |
| dense_1        | (None, 8)        | 72      | dropout[0][0]      |
| dense_2        | (None, 1)        | 9       | dense_1[0][0]      |

#### Total params: 99,873 (390.13 KB)
#### Trainable params: 99,873 (390.13 KB)
#### Non-trainable params: 0 (0.00 B)


### loss curve -
![image](https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/e284f609-37bb-4419-bafa-94f840e5502d)  ![image](https://github.com/irohan0/Deepfake-Detection-using-CNN-RNN/assets/121719717/7ff7e350-a688-4e6a-8fd9-6dfdb88dd241)


## Contributors

- [Rohan Inamdar](https://github.com/irohan0)
- [Kavin Sundarr](https://github.com/KavinSundarr)


