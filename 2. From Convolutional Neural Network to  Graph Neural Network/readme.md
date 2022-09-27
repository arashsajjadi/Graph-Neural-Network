# 2. From Convolutional Neural Network to  Graph Neural Network

## Review on Convolution Operation

In mathematics (in particular, functional analysis), convolution is a mathematical operation on two functions (f and g) that produces a third function ( $f*g$ ) that expresses how the shape of one is modified by the other.

Convolutional Operation means for a given input we re-estimate it as the weighted average of all the inputs around it. We have some weights assigned to the neighbor values and we take the weighted sum of the neighbor values to estimate the value of the current input/pixel.



![Schematic-illustration-of-a-convolutional-operation-The-convolutional-kernel-shifts-over](https://user-images.githubusercontent.com/47760229/192607664-7b328fb0-f2ad-4add-b9c8-918a9c89cc3c.png)


You can get more information about the effect of kernel selection from [this website](https://setosa.io/ev/image-kernels/).

