# deblurring-images-using-SVD
This repository consists of the final project for Numerical Linear Algebra course, Skoltech, 2022


## Description
We propose the approach to recover the image data (debluring) by utilizing Singular Value Decomposition ([SVD](https://en.wikipedia.org/wiki/Singular_value_decomposition)). This approach can aid in the denoising of data and the recovery of the original image. 

First, we utilizing Toeplitz matrix for blurring images. Let $A$ is a $N×N$ matrix, we use the function `scipy.linalg.toeplitz` for creating 2 Toeplitz matrices $P_c$ and $P_r$ which their diagonal values have the maximum value and other values are decreased linearly from the diagonal. Then, we multiply with matrix $A$ as $P_c A P_r^T$. This is the way to blur the image via vertical and horizontal.

Second, we also add noise to the image as $P_c A P_r^T + E$ ; where $E$ represents the random nois and let's see the effect of noise for direct solving equation as 

$$ 
B = P_c A P_r^T + E 
$$

Consider $P_c A P_r^T = B$, we can find 

$$ 
A_1 = A P_r^T = \text{scipy.linalg.solve}(P_c, B)
$$

We have $A_1 = A P_r^T$, then we can solve $P_r A^T = A_1$ with 

$$ 
A_2 = A^T = \text{scipy.linalg.solve}(P_r, A_1^T)
$$

Then, we have the image data with noise as $A = A_2^T$ and can be representd as the following images.

![readme_1](https://github.com/Bari-Khairullin/deblurring-images-using-SVD/blob/main/Results/readme_1.png)


## Requirements
We use `scipy.linalg` as a main library to solve this problem.


## How to run the code and repeat experiment
1. Clone the repository
``` 
git clone https://github.com/Bari-Khairullin/deblurring-images-using-SVD.git
```
2. Run code step by step
