# deblurring-images-using-SVD
This repository consists of the final project for Numerical Linear Algebra course, Skoltech, 2022

## Description
We propose the approach to recover the image data (debluring) by utilizing Singular Value Decomposition ([SVD](https://en.wikipedia.org/wiki/Singular_value_decomposition)). This approach can aid in the denoising of data and the recovery of the original image. 

First, we utilizing Toeplitz matrix for blurring images. Let $A$ is a $N×N$ matrix, we use the function `scipy.linalg.toeplitz` for creating 2 Toeplitz matrices $P_c$ and $P_r$ which their diagonal values have the maximum value and other values are decreased linearly from the diagonal. Then, we multiply with matrix $A$ as $P_c A P_r^T$. This is the way to blur the image via vertical and horizontal.

Second, 


## Requirements



## How to run the code and repeat experiment
1. Clone the repository
``` 
git clone https://github.com/Bari-Khairullin/deblurring-images-using-SVD.git
```
2. Run code step by step
