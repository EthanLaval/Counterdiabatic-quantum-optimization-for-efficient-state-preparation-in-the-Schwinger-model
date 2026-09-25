# Counterdiabatic-quantum-optimization-for-efficient-state-preparation-in-the-Schwinger-model

These code files use python 3.11.14, matplotlib 3.10.7, qiskit 2.2.3, qiskit-aer 0.17.2, and qiskit_algorithms 0.4.0. The code files were ran on jupyter notebook 7.3.2.

Operator_pool_calculator.ipynb - Code that calculates the operator pool A, using the nested commutator approach to calculating the adiabatic gauge potential (arXiv:1904.03209), up to a given order and keeping up to n-body terms, for a given problem Hamiltonian and mixer Hamiltonian (it assumes that H_0 is an adiabatic Hamiltonian of the form H_ad = (1 - λ)H_M + λH_P). It returns A in the form of a list of Pauli operator terms. A term then is chosen from this list and summed over the qubits to get A_DC.

Schwinger_CD_algorithms.ipynb - Code that runs QAOA (arXiv:1411.4028), DC-QAOA (arXiv:2107.02789), CD-inspired (arXiv:2212.13511), CD-mixer (arXiv:2502.15375), and CD-prob for the Schwinger model. It runs the algorithms for a certain number of runs and a range of layers, with different random parameters each time. It then plots the average energy plots, the best energy plots (the run that reached the lowest energy), average approximation ratios, best approximation ratios (the ones closest to one), average state fidelity, and the best state fidelity (the ones closest to one). The average plots for the DC-QAOA, CD-inspired, CD-mixer, and CD-prob only include the runs with the fixed A_DC term.

Schwinger_CD_algorithms-QAOA_initialization.ipynb - Same as Schwinger_CD_algorithms.ipynb but uses the QAOA initialization, described at the end of the results section of the paper, for the variational parameters.

Schwinger_CD_algorithms_resource_estimation.ipynb - Code that takes the ansatz state circuits from running the algorithms in the code Schwinger_CD_algorithms.ipynb and transpiles that through the fake IBM backend FakeAlgiers (https://quantum.cloud.ibm.com/docs/en/api/qiskit-ibm-runtime/fake-provider-fake-algiers) and counts the number of specific operations, the total number of operations, and the depth of the circuit and saves the data into a text file.

qiskit_env.yaml - conda environment that includes the packages needed to run the codes.
