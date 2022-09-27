# 2. From Convolutional Neural Network to  Graph Neural Network

## Review on Convolution Operation

In mathematics (in particular, functional analysis), convolution is a mathematical operation on two functions (f and g) that produces a third function ( $f*g$ ) that expresses how the shape of one is modified by the other.

Convolutional Operation means for a given input we re-estimate it as the weighted average of all the inputs around it. We have some weights assigned to the neighbor values and we take the weighted sum of the neighbor values to estimate the value of the current input/pixel.



![Schematic-illustration-of-a-convolutional-operation-The-convolutional-kernel-shifts-over](https://user-images.githubusercontent.com/47760229/192607664-7b328fb0-f2ad-4add-b9c8-918a9c89cc3c.png)


You can get more information about the effect of kernel selection from [this website](https://setosa.io/ev/image-kernels/).

The methods I mentioned, named Matrix factorization, look-up table, and random walk, are not suitable options. The reason for this is as follows.

  - **No parameter sharing:** Computationally expensive
  - **No semantic information:** Feature nodes are not considered
  - **Not inductive:** Cannot predict embedding for unseen data (Inherently transductive)  

There are also challenges for generalizing convolutional operators on graphs, which you can see in the table below.

<table>
<thead>
  <tr>
    <td rowspan="4"><img src="https://user-images.githubusercontent.com/47760229/192498838-cf9d7bab-4fbf-477a-87a8-aedcb744604f.png" width="400" height="300"></td>
    <td colspan="2">Challanges</td>
  </tr>
  <tr>
    <td>Number of neighbor nodes changes</td>
    <td>We may have heterogeneous graph<br></td>
  </tr>
  <tr>
    <td>Distance between node changes</td>
    <td>Node ordering can change (the Homorphism problem)</td>
  </tr>
  <tr>
    <td>Number of attributes can vary(features)</td>
    <td></td>
  </tr>
</thead>
</table>
