
# Operators for Qiskit

## Overview

These operators integrates your quantum workloads on OpenShift. It provides a development environment to implement quantum algorithms and runs them either on IBM quantum computers or simulators.

## Getting started

1. Qiskit developer's experience operator
    
    Operator sets up a development environment with an integrated [Jupyter Notebook](https://hub.gke.mybinder.org/user/ipython-ipython-in-depth-azjvu4ak/notebooks/examples/Notebook/Notebook%20Basics.ipynb) and pre-installed dependencies for running quantum circuits on [IBMQ Account](https://quantum-computing.ibm.com/) using [Qiskit](https://qiskit.org/).

    Example notebook implementing [Grover's Search Algorithm](https://qiskit.org/textbook/ch-algorithms/grover.html)

    For getting started guides, installation, deployment and test Qiskit developer's experience operator follow [here](https://github.com/redhat-et/glowing-quantum/tree/qiskit-dev-op/operators-examples/qiskit-dev-operator).

2. Qiskit Runtime Operator
 
   This operator is targeted for personas classified as traditional application architects / developers who will be designing the production pipeline for heterogeneous applications that have both quantum and classical components. The operator has a similar architecture as the tensor flow serving. 
  
   The controller will expose REST API to submit as input quantum circuits and run them IBM quantum backends, choosing least best fit backend depending on number of qubits required, number of jobs already scheduled and proximity/locality of the backend. Job status and results can be queried using REST APIs.

## Contributing

Operators for Qiskit  is a community driven project and we welcome contributions. See Contributing to get started.

## Report a Bug

For filing bugs, suggesting improvements, or requesting new features, please open an  [issue](https://github.com/redhat-et/glowing-quantum/issues)
