# Binary image classification with transfer learning

This project trains and tests pretrained CNN models for any given binary image classification task.

## Model: VGG16  

VGG16 is a convolutional neural network, known for its depth and its small convolutional filter size. I have added a linear layer (4096, 1) after VGG16 to make binary classification. 

### Features of VGG16:

- **Depth**: Contains 16 layers in total (13 convolutional layers + 3 fully connected layers).
- **Convolutions**: Employs 3x3 convolutional filters.
- **Pooling**: Utilizes max-pooling to systematically reduce the spatial dimensions.
- **Fully Connected Layers**: Consists of three dense layers at the end, the last of which is modified in this project for binary classification.
- **Dropout**: Incorporates dropout for regularization in the dense layers.

### Implementation Details:

- **Preprocessing**: Images are resized to 224x224 and normalized.
- **Training**: The model is trained using the Binary Cross Entropy with Logits loss and optimized using the Adam optimizer.
- **Evaluation**: After each epoch, the model's performance is assessed on a validation set.

## Model: ResNet18 

### Features of ResNet18:

- **Depth**: Contains 18 layers in total, which includes convolutional layers and fully connected layers.
- **Residual Blocks**: Employs a unique structure called the "residual block" with skip connections. This allows the network to have shorter paths during backpropagation, making training deep networks more feasible.
- **Convolutions**: Utilizes a combination of 3x3 and 7x7 convolutional filters.
- **Pooling**: Uses average-pooling before the final fully connected layer.
- **Fully Connected Layers**: Contains a single dense layer at the end, which has been modified in this project for binary classification.
- **Shortcut Connections**: The defining feature of ResNets, these connections "skip" one or more layers and perform identity transformation if necessary. They help in preventing the vanishing gradient problem in deeper models.

### Implementation Details:

- **Preprocessing**: Images are resized to 224x224 and normalized.
- **Training**: The model is trained using the Binary Cross Entropy with Logits loss and optimized using the SGD optimizer.
- **Evaluation**: After each epoch, the model's performance is assessed on a validation set.

## Usage
1. Install dependencies listed in `requirements.txt`
2. On `paths.py`, enter the paths to your dataset.
3. Images should be named sequentially from `1.jpg` to `n.jpg` where 'n' is the number of images. Labels of the images should be ordered accordingly.
4. Run the provided Python script to train and evaluate the model.
5. After training, new model Iights will be saved in `{model_name}_trained.pth` for future inference tasks.

