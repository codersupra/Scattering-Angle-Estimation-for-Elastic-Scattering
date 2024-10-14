# Scattering-Angle-Estimation-for-Elastic-Scattering

Project Overview
This project aims to calculate the two-particle elastic scattering phase shift for a short-ranged interaction using a Variational Quantum Eigensolver (VQE) on a quantum computer. Short-ranged interactions, characterized by a large scattering length or a shallow bound state, are essential for understanding systems in atomic, condensed matter, nuclear, and particle physics.

The key goal of this project is to compute the scattering phase shift by evaluating the ground state energy of the interacting particles confined in a harmonic trap. The relaxation method is employed as the classical optimizer within the VQE algorithm to approximate the ground state. This approach leverages Schmidt decomposition to reduce the number of qubits required, minimizing the noise inherent in quantum measurements on NISQ (Noisy Intermediate Scale Quantum) devices.

Background
Scattering experiments are central to studying quantum systems, providing insights into their internal structure. Elastic scattering describes the time evolution of quantum systems under a Hamiltonian associated with the interaction between the scattering particles.

Traditional methods like Lüscher's method, the Busch formula, and the spherical-wall method are commonly used in classical computations to extract scattering phase shifts. However, these methods are often difficult to implement in quantum systems due to limitations in Euclidean-time simulations and the fermionic sign problem. In contrast, quantum computers operate in Minkowski-time, which offers potential advantages for calculating dynamic properties like scattering cross sections.

In this project, we use the Busch formula to measure the energy shift of particles in a harmonic trap due to interaction. The phase shift is extracted from the energy calculation using VQE.


VQE and Relaxation Method
The Variational Quantum Eigensolver (VQE) is a hybrid quantum-classical algorithm designed to find the ground state energy of quantum systems. The relaxation method is used in this project to iteratively improve the trial wave function. The VQE process involves:

Initializing a trial wave function as an equal superposition of 2L qubits.
Applying a variational ansatz that depends on the total energy 
𝐸
total
E 
total
​
 .
Iteratively updating the wave function to minimize the energy, thus converging on the ground state.
Normalizing the wave function and encoding it into a quantum state using Qiskit's QuantumCircuit.
The reduction in qubits through Schmidt decomposition allows for simulating two-particle systems with fewer resources, thus mitigating noise and improving the accuracy of the results.
