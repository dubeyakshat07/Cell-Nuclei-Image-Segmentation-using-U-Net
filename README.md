# Cell-Nuclei-Image-Segmentation-using-U-Net

## Introduction:
U-Net is a convolutional neural network that was developed for biomedical image segmentation at the Computer Science Department of the University of Freiburg, Germany. The network is based on the fully convolutional network and its architecture was modified and extended to work with fewer training images and to yield more precise segmentations. Segmentation of a 512 × 512 image takes less than a second on a modern GPU.

<img src="https://www.researchgate.net/profile/Alan_Jackson9/publication/323597886/figure/fig2/AS:601386504957959@1520393124691/Convolutional-neural-network-CNN-architecture-based-on-UNET-Ronneberger-et-al.png">

The U-Net architecture stems from the so-called “fully convolutional network” first proposed by Long and Shelhamer.

The main idea is to supplement a usual contracting network by successive layers, where pooling operations are replaced by upsampling operators. Hence these layers increase the resolution of the output. What's more, a successive convolutional layer can then learn to assemble a precise output based on this information.

One important modification in U-Net is that there are a large number of feature channels in the upsampling part, which allow the network to propagate context information to higher resolution layers. As a consequence, the expansive path is more or less symmetric to the contracting part, and yields a u-shaped architecture. The network only uses the valid part of each convolution without any fully connected layers. To predict the pixels in the border region of the image, the missing context is extrapolated by mirroring the input image. This tiling strategy is important to apply the network to large images, since otherwise the resolution would be limited by the GPU memory.

Source: https://en.wikipedia.org/wiki/U-Net

## Project details:
Here we trained the U-Net for the image segmentation task. The aim was to correctly segment the portion where the nuclei were seen. Then the neural network was trained on the 2018 Data Science Bowl from Kaggle (link: https://www.kaggle.com/c/data-science-bowl-2018). After training the model for 10 epochs the training accuracy was around 96.29% and the validation accuracy was around 96.36%.

## Spot Nuclei. Speed Cures.
Imagine speeding up research for almost every disease, from lung cancer and heart disease to rare disorders. The 2018 Data Science Bowl offers our most ambitious mission yet: create an algorithm to automate nucleus detection.

We’ve all seen people suffer from diseases like cancer, heart disease, chronic obstructive pulmonary disease, Alzheimer’s, and diabetes. Many have seen their loved ones pass away. Think how many lives would be transformed if cures came faster.

By automating nucleus detection, we could help unlock cures faster—from rare disorders to the common cold.

Identifying the cells’ nuclei is the starting point for most analyses because most of the human body’s 30 trillion cells contain a nucleus full of DNA, the genetic code that programs each cell. Identifying nuclei allows researchers to identify each individual cell in a sample, and by measuring how cells react to various treatments, the researcher can understand the underlying biological processes at work.


## Aim: 
We created a computer model that can identify a range of nuclei across varied conditions. 

## Result: 
Model was trained on 670 images and the validated upon 65 images. After training the model for 10 epochs the training accuracy was around 96.29% and the validation accuracy was around 96.36%. Adam optimizer was used and was evaluated on the binary crossentropy loss function. 

### Input Image:
<img src="https://www.kaggleusercontent.com/kf/44783023/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..E_ENOuW3pDj_WgOL6MrXdg.kTDah2GyyIMYuYz4XQLdMToxyeW2pu5z24L8s9Hi9rg84XwjEQfzzTYMoOEFAUFFW1ZxmQ2WTvFGz-Tlb5uYOQbpu6MvsmtNjB6bU0TSQjdH4hFpEz7VwkjHshidPtzYWe4weE5a2y0CA9VXhPl4-JXIfVmRq250LLtT-lqrdemk3GbpNMTA5XJ5wGR4jiOhEO-jRxNmh9_MWDxGA3C6OaA7wcLKiNFYhh-VUEdcgcz4g-EQ2seVkeLiDyTBHSjMrpNJOSrwNlwlUdzIKOms4frPpd4KM4MWk00VUMucDD6znPij4n1KmdQS_OlH11CPN3a58KGsrhiO_XazNkoqlFxelU4HGqQw6qQeLZ_kUDXkg5aMCOfJo9l1qCfxWlXq_m9vpuqht8JLbq0qWAwceHGvJ0bmqaAKi19iduEJM4gerEzWjkVH5rgbHnGSg5kpMgrYS-miBC9N2EKOT8H6oBFSiwJp28PZ6RZLe2XuVLP-2M7AnGTaIVBIFyZ__g8UWLmxoz6S1HNs-Dk--dnu7v9sWCuuk3X46o7ruzA5EAxDS2L6pfRvN5WS0hqdSaYCGmPGCfZqn63pP8VZyh4wKiGpkuAlxYal420iYuRl06CO1CeZMM0nzrBuVI6zsLXdOWu9DlkyiZz4vLy7VEhAbQ.aS1gn_mrtmr5FZrkqZcDaw/__results___files/__results___27_0.png">

### Output Image: 
<img src="https://www.kaggleusercontent.com/kf/44783023/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..E_ENOuW3pDj_WgOL6MrXdg.kTDah2GyyIMYuYz4XQLdMToxyeW2pu5z24L8s9Hi9rg84XwjEQfzzTYMoOEFAUFFW1ZxmQ2WTvFGz-Tlb5uYOQbpu6MvsmtNjB6bU0TSQjdH4hFpEz7VwkjHshidPtzYWe4weE5a2y0CA9VXhPl4-JXIfVmRq250LLtT-lqrdemk3GbpNMTA5XJ5wGR4jiOhEO-jRxNmh9_MWDxGA3C6OaA7wcLKiNFYhh-VUEdcgcz4g-EQ2seVkeLiDyTBHSjMrpNJOSrwNlwlUdzIKOms4frPpd4KM4MWk00VUMucDD6znPij4n1KmdQS_OlH11CPN3a58KGsrhiO_XazNkoqlFxelU4HGqQw6qQeLZ_kUDXkg5aMCOfJo9l1qCfxWlXq_m9vpuqht8JLbq0qWAwceHGvJ0bmqaAKi19iduEJM4gerEzWjkVH5rgbHnGSg5kpMgrYS-miBC9N2EKOT8H6oBFSiwJp28PZ6RZLe2XuVLP-2M7AnGTaIVBIFyZ__g8UWLmxoz6S1HNs-Dk--dnu7v9sWCuuk3X46o7ruzA5EAxDS2L6pfRvN5WS0hqdSaYCGmPGCfZqn63pP8VZyh4wKiGpkuAlxYal420iYuRl06CO1CeZMM0nzrBuVI6zsLXdOWu9DlkyiZz4vLy7VEhAbQ.aS1gn_mrtmr5FZrkqZcDaw/__results___files/__results___27_1.png">

## Tech Stack: Python, Jupyter Notebook, Tensorflow, skimage
