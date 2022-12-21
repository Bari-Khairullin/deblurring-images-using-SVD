# deblurring-images-using-SVD
This repository consists of the final project for Numerical Linear Algebra course, Skoltech, 2022

## Description
We propose the approach to recover the image data (debluring) by utilizing Singular Value Decomposition ([SVD](https://en.wikipedia.org/wiki/Singular_value_decomposition)). This approach can aid in the denoising of data and the recovery of the original image. 

First, we test blurring an image with symmetric Toeplitz matrices. Let image be an $M\times N$ array. Then we can blur it by matrix-multiplication of the array with Toeplitz matrices from the left (vertical blurring) and the right (horizontal blurring) hand sides:

$$T_1 X T_2 = B.$$

At this stage it is easy to deblur the corresponding image since matrices are invertible:
$$X = T_1^{-1}BT_2^{-1}.$$

However, if we add some random unknown small noise to the blurred image:

$$T_1XT_2=B+E,$$

the initial picture will not be correctly restored, because $T_1^{-1}ET_2^{-1}$ can be big. 

<p align="center" width="100%">
    <img width="70%" src="https://github.com/Bari-Khairullin/deblurring-images-using-SVD/blob/main/Results/result_1.jpg">
</p>

So to reduce the error we use pseudoinverse $T^+$, which doesn't contain inverses of small singular values. Image obtained by restoring with SVD-trancated matrices:

<p align="center" width="100%">
    <img width="20%" src="https://github.com/Bari-Khairullin/deblurring-images-using-SVD/blob/main/Results/result_2.jpg">
</p>


## Requirement
We use `scipy.linalg` as a main library to solve this problem.

## How to run the code and repeat experiment
1. Clone the repository
``` 
git clone https://github.com/Bari-Khairullin/deblurring-images-using-SVD.git
```
2. Run code step by step
