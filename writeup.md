## Neural Network Architecture
- Input layer (3 features)
- Encoding layers (16, 32, 64) - increase depth for more information
- 1x1 convolution layer - retain spatial information
- Decoding layer (64, 32, 16) - upsample layers to retain spatial information, also contains skip connections

## Neural Network Diagram

## Neural Network Parameters
- `learning_rate = 0.05` The learning rate was made small so the network would converge to a lower minimum. However, because of the lower learning rate, the number of epochs needed to be increased so the cost fo the neural network could properly be minimized
- `batch_size = 50` The batch size was
- `num_epochs = 5` Due to the limitations of time, it was decided to keep the number of epochs as low as possible. Also, from testing, going above 10 epochs did not improve the overall network performance by a significant amount.
- `validation_steps = 50` Kept as default
- `workers = 2` Kept as default

## Neural Network Techniques
### 1x1 convolutions
A 1x1 convolution is used to preserve spatial information as well as make neural newtorks deeper to model more complex relationships. They are relatively inexpensive since they are just another matrix multiplication.

### Fully connected layers
Fully connected layers should be used when spatial information does not matter such as classifying a single object, or predicting an abstract value. However, due to the nature of the problem, 1x1 convolutions are preferred because of they retain spatial information.

### Skip connections
Skip connections allow for cleaner segmentations as it gives access to information from different levels of the filter. By incorporating information from different convolution layers in the network, the spatial information can be more accurate.

### Encoding
Encoding reduces the height and width of the convolution in favour of more features/depth. This can extract higher levels of information or features that may not be immediately present in shallower levels. To retain the spatial information lost from encoding, decoding and skip connections are used.

### Decoding
Due to the encoding process, the segmented portions of the image can be recognized but there is a loss of spatial information. The process of decoding allows the network to regain the spatial information, specifically locating where the segmented object is located within the dimensions of the original image. This is done from Bilinear upsampling. Skip connections are also used to gain more accurate spatial information.

## Applications of the Neural Network
Although the trained model is able to locate humans within given images, its application to other class segmentation is limited. Other objects like dogs, cats, or cars would not be properly segmented since the training set did not contain those kinds of objects as well as the training . If it was necessary to expand the network's functionality, new training data would be needed and the neural network may need to modified to adjust to the new images.
