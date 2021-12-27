# Mosaic ML implementation 

## This paper was presented in MLDS 2022
## SOTA Accuracies on MNIST and CIFAR-10 

This paper covers advanced topics on making deep neural networks more efficient and robust by enhancing architectural efficiency, optimization, label manipulations, and learning rate techniques.

### Architectural Efficiency
- Depth wise separable convolutions - Parameter Reduction
- Global average pooling - Paramter reduction
- Blurpool - Anti Aliasing
- Squeeze and Excite - Channel Attention

Depthwise Separable Convolutions|Squeeze and Excitation Blocks|Blurpool
:-------------------------:|:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/48343095/147498710-c7c49d99-c156-4b21-8a28-0afe48c2bb2d.png) | ![image](https://user-images.githubusercontent.com/48343095/147498685-bbe2e3c8-6fac-4f16-9132-46931383ab86.png)|![image](https://user-images.githubusercontent.com/48343095/147498991-f4da12e8-d09a-45fd-810d-18aeb1ee7557.png)


### Weight Space Altlerations
- Stochastic Weight Averaging

### Optimization & Regularization
- Sharpness Aware minimization
- Label Smoothing
- One Cycle LR

Sharpness Aware minimization
:-------------------------:
![image](https://user-images.githubusercontent.com/48343095/147498698-33884aa8-8afa-4811-9761-d9060014506d.png)


### Augmentations
- Mixup
- Cutout

Depthwise Separable Convolutions|Squeeze and Excitation Blocks
:-------------------------:|:-------------------------:
<img src="https://user-images.githubusercontent.com/48343095/147499358-1481a720-8e92-4a04-982f-414b068a9bb6.png" width="300"  height = "250"/> | <img src="https://user-images.githubusercontent.com/48343095/147499507-fbeba322-7a41-48c8-860d-e128ba54bb0c.jpg" width="300"  height = "250"/>


## MNIST Architectures
## CIFAR-10 Architectures
