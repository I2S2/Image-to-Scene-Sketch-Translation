# The datasets used in our paper: I2S^2: Image-to-Scene Sketch Translation using Conditional Input and Adversarial Networks. NOTE THAT for the best view experience, one may need to click on an image to see the full view. 


# For Training:

### PHOTOSKETCH-DATASET-RAW

This dataset is from [1]. The training images are fed into the generative model directly without being conditioned by the HED (Holistically-Nested Edge Detection) [2]. Typical image augmentation methods are used, including flipping, rotation and translation.

There are two directories: UNALIGNED and ALIGNED. ALIGNED images contain both the input image and the label in the same file, resulting in a 256H x 512W X 3D (RGB) image. The UNALIGNED images are all 256H x 256W x 3D (RGB).

Due to its large size, we ignore its uploading during this stage. 

### PHOTOSKETCH-DATASET-HED

This dataset is from [1]. The training images are conditioned by the HED before they are fed into the generative model. This dataset is entirely aligned and grayscale, yielding a dimension of 256H x 512W x 1D for each image, which consists of an edge map (extracted by the HED) and its sketch label. 


# For Testing:

In the folder TEST-RESULTS-ALL-MODELS, there is a subfolder SKETCHY-DB-TEST-SET-UNALIGNED that includes all the 98 testing images, which are adopted from the Sketchy Database [3]. 




# More results of our method and the other competing methods


### In the folder TEST-RESULTS-ALL-MODELS:

# CYCLEGAN-LSGAN-HED (our best)

This is the model which gives the best results. The HED is used to provide conditioning input, and the CycleGAN loss is adopted. 

# CYCLEGAN-LSGAN-RAW (ours)

Input is not conditioned by the HED. The CycleGAN loss is used. 

# CYCLEGAN-LSGAN-CANNY (ours)

Canny operator is used to provide conditioning input, and the CycleGAN loss is used. 

# CYCLEGAN-WGANGP-CANNY (ours)

Canny operator is used to provide conditioning input, and the Wasserstein distance with gradient-penalty is exploited for CycleGAN training.

# PHOTO-SKETCHING-INFERRING-CONTOURS (the method in [1])

The results are obtained by the method in [1]. 

# HOLISTICALLY-NESTED-EDGE-DETECTION (the method in [2])

The results are obtained by the method in [2]. 



### TRAIN-RESULTS-OUR-MODEL-STITCHED

This folder contains samples of our model output at fixed intervals throughout 32 epochs of training. We have stitched the images together in three rows and two columns. The top row is the original image-pair prior to being fed into the generative model for training. The second row shows the images after data augmentation. The bottom row gives the output of both generators in the CycleGAN. Fake_A is the generated sketch during training. 



Reference

[1] Mengtian Li, Zhe L. Lin, Radomı́r Mech, Ersin Yumer, and
Deva Ramanan. Photo-sketching: Inferring contour draw-
ings from images. In IEEE Winter Conference on Applica-
tions of Computer Vision, WACV 2019, Waikoloa Village, HI,
USA, January 7-11, 2019, pages 1403–1412, 2019.

[2] Saining Xie and Zhuowen Tu. Holistically-nested edge de-
tection. International Journal of Computer Vision, 125(1-
3):3–18, 2017.

[3] Patsorn Sangkloy, Nathan Burnell, Cusuh Ham, and James
Hays. The sketchy database: learning to retrieve badly drawn
bunnies. ACM Trans. Graph., 35(4):119:1–119:12, 2016.






