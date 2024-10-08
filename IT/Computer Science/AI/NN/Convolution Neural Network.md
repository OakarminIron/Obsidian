Convolution Neural Networks (CNNs) are a class of deep learning models specifically designed for processing structured grid data, such as images. Here’s a brief overview of their key components.

1. **Convolutional Layers**: These layers apply convolution operations to the input. A filter (or kernel) slides over the input image, performing element-wise multiplication and summing the results to produce a feature map. This helps detect features like edges, textures, and shapes.

2. **Activation Function**: Typically, the Rectified Linear Unit (ReLU) is used as an activation function, introducing non-linearity into the model. It replaces negative values with zero, helping the network learn complex patterns.

3. **Pooling Layers**: These layers reduce the spatial dimensions of the feature maps (e.g., max pooling or average pooling). This down-sampling helps reduce computational load and controls over-fitting by making the representation more abstract.

4. **Fully Connected Layers**: After several convolution and pooling layers, the high-level features are flattened and passed through fully connected layers. These layers make the final classification based on the learned features.

5. **Dropout**: A regularisation technique used to prevent over fitting. During training, some neurons are randomly "dropped" (set to zero) to encourage the model to learn robust features.


### How CNNs Work

1. **Input**: An image is fed into the CNN as a multi-dimensional tensor (height, width, colour channels).
2. **Feature Extraction**: The convolutional and pooling layers extract hierarchical features from the image. Early layers detect simple features (like edges), while deeper layers capture more complex patterns (like shapes or objects).
3. **Classification**: The fully connected layers interpret these features and output probabilities for each class in a classification task.
    

### Applications

CNNs are widely used in various domains, primarily for image-related tasks such as:

- Image classification (e.g., identifying objects in photos)
- Object detection (e.g., locating and classifying objects in images)
- Image segmentation (e.g., dividing an image into meaningful parts)

Overall, CNNs have revolutionised computer vision and remain a foundational tool in many deep learning applications.