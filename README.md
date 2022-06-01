# Face Mask Detection

Face mask detection is used to detect the use of masks during the COVID-19 pandemic. This project is a personal experiment to implement the Convolutional Neural Network algorithm in face detection that is not wearing a mask, wearing a mask and wearing a mask but not properly.

## About Dataset

The face mask dataset used in this experiment can be downloaded [here](https://www.kaggle.com/datasets/vijaykumar1799/face-mask-detection).
The following is a summary of the dataset.

| Number of Classes | 3                                                             |
| :---------------- | :------------------------------------------------------------ |
| Class Details     | mask_weared_incorrect, with_mask, without_mask                |
| Amount of data    | 2994 mask_weared_incorrect, 3000 with_mask, 2994 without_mask |

The data is divided into 2 parts, namely 7185 train data and 1797 validation data.

## Model Architecture

The model architecture used in this experiment is as follows.

`Model: Sequential`
| Layer Type | Output Shape | Params # |
| :-------- | :------- | :-------|
| conv2d (Conv2D) | (None, 298, 298, 8) | 224 |
| max_pooling2d (MaxPooling2D) | (None, 149, 149, 8) | 0 |
| conv2d_1 (Conv2D) | (None, 147, 147, 16) | 1168 |
| max_pooling2d_1 (MaxPooling2D) | (None, 73, 73, 16) | 0 |
| conv2d_2 (Conv2D) | (None, 71, 71, 32) | 4640 |
| max_pooling2d_2 (MaxPooling2D) | (None, 35, 35, 32) | 0 |
| flatten (Flatten) | (None, 39200) | 0 |
| dense (Dense) | (None, 64) | 2508864 |
| dense_1 (Dense) | (None, 3) | 195 |
| Total params: 2,515,091 |
| Trainable params: 2,515,091 |
| Non-trainable params: 0 |

## Model Evaluation

Model training is performed with `epoch = 10` and uses an Early Stopping callback which will stop model training if `val_accuracy` has converged to a value.
From the results of the training, the evaluation of the model in the last epoch (epochs = 9) was obtained as follows.
| Metrics | Value |
| :-------- | :------- |
| Accuracy | 0.9662 |
| Loss | 0.1026 |
| Val Accuracy | 0.9509 |
| Val Loss | 0.1263 |

### Accuracy Plot per Epoch

![Accuracy Plot](https://raw.githubusercontent.com/taqiyyaghazi/cnn-face-mask-detection/main/img/accuracy.png)

### Loss Plot per Epoch

![Loss Plot](https://raw.githubusercontent.com/taqiyyaghazi/cnn-face-mask-detection/main/img/loss.png)

## Acknowledgements

- [Data Resource](https://www.kaggle.com/datasets/vijaykumar1799/face-mask-detection)
