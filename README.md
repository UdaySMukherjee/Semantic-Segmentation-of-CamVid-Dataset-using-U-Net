# Semantic Segmentation of CamVid Dataset using U-Net

## Dataset Overview
The CamVid dataset is a collection of images captured from a vehicle-mounted camera. It is widely used for semantic segmentation tasks and contains images with corresponding pixel-wise labeled masks. The dataset includes 32 different classes, such as road, sidewalk, building, sky, and others.

## U-Net Architecture
The U-Net architecture consists of a contracting path, a bottleneck, and an expansive path. The contracting path captures context and spatial information through convolutional and pooling layers, while the expansive path enables precise localization using transposed convolutions. Skip connections between corresponding layers in the contracting and expansive paths help preserve spatial information.

The architecture is divided into the following key components:

1. Contracting Path
The contracting path comprises a series of convolutional blocks, each containing two convolutional layers with batch normalization and ReLU activation functions. Max-pooling is applied after each block to reduce spatial dimensions.

2. Bottleneck
The bottleneck consists of a double convolution block, which retains the most critical information in a compressed form.

3. Expansive Path
The expansive path consists of transposed convolutions and concatenation with the corresponding feature maps from the contracting path. Each block in the expansive path consists of two convolutional layers with batch normalization and ReLU activation.

4. Output Layer
The final layer employs a 1x1 convolution to produce the segmentation map with pixel-wise class predictions.

## Data Preprocessing
Images and masks from the CamVid dataset are preprocessed using standard transformations, including resizing and normalization. The masks are converted to one-hot encoded tensors to match the model's output format.

## Loss Function and Optimization
The Focal Loss, a modification of the cross-entropy loss, is used as the loss function. Stochastic Gradient Descent (SGD) is employed as the optimization algorithm with momentum.

## Results and Visualization
![](https://imgur.com/2RjxOEQ.png)

The training process is visualized by plotting the training and validation loss curves. Additionally, sample images, original masks, and predicted masks are displayed to assess the model's performance.

