# Homework 3

Consider the following 2-D Laplace Equation:

$$
\Delta u = (u_{xx}+u_{yy})=0 \\
$$
with the boundary condition:
$$
&u(0, y ) = 0 \\
&u(2\pi,y) = 0\\
&u(x, 0) = \sin(2x)+\sin(5x)+\sin(7x)\\
&u(x,2\pi)=0
$$
For the discretization, we have 
$$
\frac{u_{i+1,j}-2u_{i,j}+u_{i-1,j}}{\Delta x^2}+\frac{u_{i,j+1}-2u_{i,j}+u_{i,j-1}}{\Delta y^2}=0
$$
Because of the given set of mesh grids $\Delta x = \Delta y = \frac{2\pi}{20}$  , the Jacobi iterative method can be derived as:

$$
u_{i,j}^{k+1} = \frac{u_{i-1,j}^{k}+u_{i+1,j}^{k}+u_{i,j-1}^{k}+u_{i,j+1}^{k}}{4}
$$
The Gauss-Seidel iterative method can be derived as:
$$
u_{i,j}^{k+1} = \frac{u_{i-1,j}^{k+1}+u_{i+1,j}^{k}+u_{i,j-1}^{k+1}+u_{i,j+1}^{k}}{4}
$$
For each grid $$(i,j)$$, the residual can be calculated as (use the Jacobi for example):
$$
r_{i, j}^k=\frac{1}{\Delta x^2}\left(u_{i-1, j}^{k-1}-2 u_{i, j}^{k-1}+u_{i+1, j}^{k-1}\right)+\frac{1}{\Delta y^2}\left(u_{i, j-1}^{k-1}-2 u_{i, j}^{k-1}+u_{i, j+1}^{k-1}\right)
$$
For the SOR iterative method, the iterative equation is shown as follows:
$$
u_{i,j}^{k+1} = (1 - \omega)u_{i,j}^{k} + \omega \tilde{u}
$$
$$\tilde{u}$$ is the updated point obtained by Jacobi or Gauss-Seidel.

The code and results are attached at the end.
