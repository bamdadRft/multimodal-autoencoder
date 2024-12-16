# multimodal-autoencoder-for-Image-Reconstruction
This project implements a multimodal autoencoder using PyTorch to reconstruct images from a combined dataset of CIFAR-10 and MNIST images. The model extracts features from combined images, decodes them, and generates reconstructed versions of both CIFAR-10 and MNIST images.

features:
* Combines two distinct datasets (CIFAR-10 and MNIST) into a single training pipeline.

* Uses a shared encoder for feature extraction.

* Implements dataset-specific decoders for image reconstruction.

* Visualizes reconstruction results after each epoch.

Requirements

* Python 3.7+

* PyTorch 1.10+

* torchvision

* matplotlib

* tqdm

# how-it-works
1- CIFAR-10 and MNIST images are combined by averaging pixel values, resizing, and channel-adjusting where necessary.

2- A shared encoder extracts features from the combined images.

3- Two decoders (specific to CIFAR-10 and MNIST) reconstruct the respective images from the shared encoded features.

4- The model is trained using a reconstruction loss (MSE) for both CIFAR-10 and MNIST outputs.

# model-architecture

Encoder:

3 convolutional layers with batch normalization and ReLU activation.

Fully connected layer to map features to a 512-dimensional latent space.

CIFAR Decoder:

Fully connected layer to reshape latent features.

3 transposed convolutional layers for upsampling.

MNIST Decoder:

Similar to CIFAR Decoder but trained to reconstruct MNIST images.

# results
Reconstructed images are visualized after each epoch, allowing for both quantitative and qualitative evaluation. The model performance is measured using metrics such as SSIM and PSNR.
The following figure shows an example of input and reconstructed images after training:

Row 1: Combined input images

Row 2: Reconstructed CIFAR-10 images

Row 3: Reconstructed MNIST images
