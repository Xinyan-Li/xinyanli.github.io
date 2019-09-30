## SGD Dynamics

This project focused on study the relationship between the Hessian of the loss and the second moment of stochastic gradients (SGs).

### Hessian Decomposition

![Hessian_decomp](http://latex.codecogs.com/gif.latex?H_f%28%5Ctheta_t%29%20%3D%20M_t%20-%20H_p%28%5Ctheta_t%29%7E),

![hessian_guass-10](images/fnn-k10-random0-b5-full-spectrum.jpg)

Figure 1: Eigen-spectrum dynamics of the Hessian Hf, the second moment of SGs, and the residule term Hp. The network is trained on Gauss-10 dataset with small batches containing one twentieth of the training samples (5/100). Hp remains significant even after SGD converges, and is close to -Hf.
