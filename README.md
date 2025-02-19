# Boson Sampling

Boson sampling is a simplified model of quantum computation that uses non‐interacting bosons—typically photons—passing through a linear optical network to sample from a probability distribution that is believed to be hard to simulate on classical computers.

## Overview

In this project, I provide a demonstration of boson sampling using a linear optical interferometer. The basic idea is to prepare an input state of single photons, let them evolve through an interferometer described by a unitary matrix, and then measure the output Fock states. The output probabilities are proportional to the squared absolute value of the permanent of submatrices of the unitary, a computation known to be #P-hard.

## Project Structure

- **README.md**: This file.
- **notebooks/**: Jupyter Notebook(s) containing the boson sampling demonstration and simulation code.
- **src/**: Source code modules (if any) for building or simulating the interferometer and measurement.
- **requirements.txt**: A list of required Python packages.

## Theoretical Background

### Input State

The input state is prepared as:
$$
|\psi_{\text{in}}\rangle = |1,1,\dots,1,0,0,\dots,0\rangle,
$$
where the first \( n \) modes each contain one photon and the remaining \( m-n \) modes are in the vacuum state.

### Interferometer

A linear optical interferometer is described by an \( m \times m \) unitary matrix \( U \) that transforms the input creation operators:
$$
\hat{b}_j^\dagger = \sum_{i=1}^m U_{ji}\,\hat{a}_i^\dagger.
$$

### Output and Measurement

After passing through the interferometer, the state becomes:
$$
|\psi_{\text{out}}\rangle = \hat{U}|\psi_{\text{in}}\rangle.
$$
Measuring the photon numbers at the output yields a configuration \( S = (s_1, s_2, \dots, s_m) \) with
$$
\sum_{j=1}^m s_j = n.
$$

### Sampling Probability

The probability of obtaining a particular output configuration \( S \) is given by:
$$
p(S) = \frac{\left|\operatorname{Per}(U_S)\right|^2}{s_1!\,s_2!\,\cdots\,s_m!},
$$
where \( U_S \) is the submatrix of \( U \) corresponding to the detected photons, and \(\operatorname{Per}(U_S)\) is the permanent of that matrix.

## Why Boson Sampling?

- **Computational Hardness:**  
  Calculating the permanent of a matrix is a \(\#P\)-hard problem, meaning that even approximate classical simulation becomes infeasible as the system size grows.

- **Quantum Advantage:**  
  While boson sampling is not universal for quantum computation, its ability to perform this specific sampling task efficiently is a strong candidate for demonstrating quantum supremacy.

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/ShashiQubit/CVQC-Boson_Sampling.git
  
