# SINDy Implementation

This repository contains a simple implementation of **Sparse Identification of Nonlinear Dynamics (SINDy)** using Python and NumPy.

SINDy discovers governing differential equations directly from data by assuming that the true dynamics contain only a small number of active terms.

For a system


$$\dot{x}=f(x),$$


a library of candidate functions is constructed:

[
\Theta(x)=
\begin{bmatrix}
1 & x & x^2 & x^3 & \cdots
\end{bmatrix}.
]

The algorithm solves

[
\dot{X}=\Theta(X)\Xi,
]

where (\Xi) is a sparse coefficient vector.

## Current Features

* Generate data from a known differential equation
* Construct a polynomial candidate library
* Solve the initial least-squares problem
* Apply Sequential Thresholded Least Squares
* Recover the identified differential equation

The current implementation focuses on systems with a single state variable.

## Example

For

[
\dot{x}=-2x+x^3,
]

SINDy should identify coefficients close to

[
\Xi=
\begin{bmatrix}
0 & -2 & 0 & 1
\end{bmatrix}^{T}.
]

## Requirements

```bash
pip install numpy scipy matplotlib
```

## Project Status

Ongoing. Planned improvements include multidimensional systems, noisy-data experiments, numerical differentiation, and trajectory-based model validation.

## Reference

Brunton, S. L., Proctor, J. L., and Kutz, J. N.,
“Discovering governing equations from data by sparse identification of nonlinear dynamical systems,”
*PNAS*, 2016.
