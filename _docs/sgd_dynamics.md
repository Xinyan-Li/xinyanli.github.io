## SGD Dynamics

This project focused on study the relationship between the Hessian of the loss and the second moment of stochastic gradients (SGs).

### Hessian Decomposition

![Hessian_decomp](http://latex.codecogs.com/gif.latex?H_f%28%5Ctheta_t%29%20%3D%20M_t%20-%20H_p%28%5Ctheta_t%29%7E),

![hessian_guass-10](images/fnn-k10-random0-b5-full-spectrum.jpg)

Figure 1: Eigen-spectrum dynamics of the Hessian Hf, the second moment of SGs, and the residule term Hp. The network is trained on Gauss-10 dataset with small batches containing one twentieth of the training samples (5/100). Hp remains significant even after SGD converges, and is close to -Hf.

### Top Subspaces: Hessian and Second Moment
We assess the overlap between the principal eigen-spaces of Hf and Mt determined by the eigenvectors corresponding to the top (positive) eigenvalues of these matrices during training based on principal angles:

![principal_angles_def](http://latex.codecogs.com/gif.latex?%5Ccos%28%5Cgamma_i%29%20%5Ctriangleq%20u_i%5ET%20v_i%20%3D%20%5Cmax_%7B%5Csubstack%7Bu%20%5Cin%20P%2C%20%5C%7Cu%5C%7C_2%20%3D%201%2C%5C%5C%20u%5ET%5Bu_1%2C%5Cldots%2Cu_%7Bi-1%7D%5D%20%3D%200%7D%7D%7E%7E%20%5Cmax_%7B%5Csubstack%7Bv%20%5Cin%20Q%2C%20%5C%7Cv%5C%7C_2%20%3D%201%2C%5C%5C%20v%5ET%5Bv_1%2C%5Cldots%2Cv_%7Bi-1%7D%5D%20%3D%200%7D%7D%20%7E%7Eu%5ETv%7E.)

![principal_angle_guass](images/fnn-k10-random0-b5-Principal-Angle.jpg)
<p align="center"> (a) [Gauss-10, 0% random labels, 2-layer Relu network, batch size: 5/100] <p>

![principal_angle_mnist](images/mnist-relu-d2-bs64-principle-angles.jpg)
<p align="center"> (b) [MNIST, 0% random labels, 3-layer Relu network, batch size: 64/50,000] <p>

![principal_angle_cifar](images/cifar10-relu-d2-bs256-principle-angles.jpg)
<p align="center"> (c) [CIFAR-10, 0% random labels, 3-layer Relu network, batch size: 256/60,000] <p>

Figure 2: Dynamics of top 15 principal angles between Hf and Mt and corresponding eigenvalues of Hf (middle) and Mt (right). For both synthetic and real datasets, the top 10 principal subspaces are well aligned.
