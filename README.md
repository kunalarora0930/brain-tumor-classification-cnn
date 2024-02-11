# Brain Tumor Detection and Classification with Convolutional Neural Networks

Kaggle notebook link - https://www.kaggle.com/code/cheesecke/brain-tumor-classification-using-cnn/

Dataset Used - https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

## Introduction

This project utilizes TensorFlow and Keras to build and train a CNN model for brain tumor classification. The dataset used for training and evaluation contains MRI images of brain tumors, with each image labeled according to its tumor type.

## Model Architecture

The CNN model architecture used for brain tumor classification consists of multiple convolutional layers followed by fully connected dense layers. Here's a detailed explanation of the model architecture:

1. **Input Layer**: 
   - Input images are expected to have a size of 224x224 pixels with 3 color channels (RGB).

2. **Convolutional Layers**:
   - The model starts with a series of convolutional layers (`Conv2D`) with 64 filters, each having a kernel size of (3, 3), using the ReLU activation function.
   - This pattern repeats, increasing the number of filters.
   - Each convolutional layer uses "same" padding to ensure the output feature maps have the same spatial dimensions as the input.
   - After every two convolutional layers, a max-pooling layer (`MaxPooling2D`) with a pool size of (2, 2) is added to reduce spatial dimensions and extract dominant features.

3. **Flatten Layer**: 
   - The output feature maps from the last convolutional layer are flattened into a one-dimensional array.

4. **Dense Layers**:
   - A series of fully connected dense layers (`Dense`) follows the flatten layer.
   - The first dense layer has 256 units with ReLU activation, followed by another dense layer with 64 units and ReLU activation.
   - The final dense layer has a number of units equal to the total number of classes in the dataset (determined by `class_count`) and uses the softmax activation function to output class probabilities.

5. **Compilation**:
   - The model is compiled using the Adamax optimizer with a learning rate of 0.001.
   - Categorical cross-entropy is used as the loss function since this is a multi-class classification problem.
   - Accuracy is chosen as the evaluation metric.
  

## Results

The trained CNN model achieved promising results in classifying brain tumor images. The evaluation metrics, including accuracy, precision, recall, and F1-score, demonstrate the model's effectiveness in accurately identifying different tumor types.

![Confusion Matrix](images/confusion_matrix.png)


## Contributing

Contributions are welcome! If you'd like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/improvement`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push the changes to your fork (`git push origin feature/improvement`).
5. Create a new Pull Request.
