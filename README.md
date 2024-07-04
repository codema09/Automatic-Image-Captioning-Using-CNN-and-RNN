
# Automatic Image Captioning Using CNN and RNN

This model is designed to generate descriptive captions for input images by leveraging both visual and linguistic information.
## Model Architecture
### Encoder (CNN) Definition
The Encoder_CNN class defines the CNN-based encoder 
responsible for extracting features from input images using a pre
trained ResNet-50 model.
- Model Description:
    - The encoder utilizes a pre-trained ResNet-50 architecture to extract high-level features from images.
    - The ResNet-50 model is adapted by removing the last fully connected layer (fc) and replacing it with a linear layer (embed) to obtain image feature embeddings of a specified size (sz_embed).
### Decoder (RNN) Definition
 The Decoder_RNN class defines the RNN-based decoder 
responsible for generating captions based on extracted image 
features.
- Model Description:
    - The decoder consists of an embedding layer followed by an LSTM (Long Short-Term Memory) layer.
    - The LSTM processes embedded caption tokens along with image features to generate sequential outputs.
    - A linear layer (fc) predicts the next word in the caption sequence.
### Training Setup
 The training process involves fine-tuning the encoder-decoder 
model using a dataset of images paired with corresponding 
captions.
- Training Steps:
    - Initialize the encoder and decoder models.
    - Define optimizer and loss function (CrossEntropyLoss).
    - Iterate over batches of image-caption pairs:
    - Pass images through the encoder to obtain feature embeddings.
    - Feed feature embeddings and caption tokens into the decoder to generate captions.
    - Compute loss based on predicted captions and ground truth captions.
    - Update model parameters using backpropagation.
