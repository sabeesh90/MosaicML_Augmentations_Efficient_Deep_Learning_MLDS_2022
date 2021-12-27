# Mosaic ML implementation 

## This paper was presented in MLDS 2022 [MLDC_2022.pdf](https://github.com/sabeesh90/MosaicML_Advanced_Optimization_Augmentations_Depthwise/files/7781588/MLDC_2022.pdf)

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


Baseline models have been built by progressively reducing the number of parameters using Depth wise convolution and GAP both in case of MNIST and CIFAR-10. 
## MNIST Architectures
![image](https://user-images.githubusercontent.com/48343095/147500168-9c46bdc4-4054-411d-b7ac-b0b50809831f.png)

## CIFAR-10 Architectures
![image](https://user-images.githubusercontent.com/48343095/147500209-d4f9f25d-0098-45fa-9226-2be9103e0243.png)

## Efficiency of DW convolutions / GAP on Accuracy / inference time
- SOTA Accuracy of 98.35% with 1.5K params  on MNIST dataset
- Accuracy of 79.9% with 140K params on CIFAR-10 dataset
- No direct effect on DW convs on latency. DW models with same number of params perform SLOWER than models with 3x3 convs. 
- inference time is proportional to the number of parameters. DW models with lesser params show a decrease in inference time than models with higher params

DW on Accuracy|DW on inference time
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/48343095/147501848-6c49f676-aaa4-494f-9a68-e641af42df12.png) | ![image](https://user-images.githubusercontent.com/48343095/147500485-23b7a36e-3c84-42a2-ae7f-47df6f891365.png)

## Efficiency of Mosaic ML techniques
- Blurpool is the most efficient technique with SOTA 99.21% with 1.5K params / Combination resulted in no significant increase in accuracy
- Combination of BP + CO + M + LS + SWA + SAM resulted in a SOTA accuracy of 86.76% with 140K params (6.865 increase) / In isolation Mixup performed better with 3.62% increase to 83.52%
- No direct effect on DW convs on latency. DW models with same number of params perform SLOWER than models with 3x3 convs. 
- inference time is proportional to the number of parameters. DW models with lesser params show a decrease in inference time than models with higher params

Isolated techniques on Accuracy|Combined techniques on Accuracy
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/48343095/147501691-01ce737e-6233-4945-a067-1cb03393876b.png) | ![image](https://user-images.githubusercontent.com/48343095/147501700-171eb2c3-b25b-4b8c-b499-97bdf2e22380.png)

## Take Home!

These techniques may be applied on other standard and custom datasets to establish the superioirty of these model enhancement techniques.
