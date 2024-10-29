# Quantum-Classical Hybrid Model with Fractal Layers

## Introduction

This project presents a quantum-classical hybrid algorithm that integrates Grover's quantum search algorithm with classical machine learning techniques—specifically, Random Forests and Long Short-Term Memory (LSTM) neural networks. The objective is to evolve a quantum system to match a target sequence of probability vectors, utilizing fractal layering to optimize the search process.

## Overview

- **Quantum System**: A 34-dimensional qudit (\( d = 34 \)) representing quantum states \( |0\rangle \) to \( |33\rangle \).
- **Grover's Algorithm**: Constructs the Hamiltonian guiding the quantum evolution towards the target states.
- **Random Perturbations**: Introduced in the Hamiltonian to promote exploration and prevent the system from getting trapped in local minima.
- **Regressive Coefficients**: Dynamically adjusted values that reinforce or diminish the influence of certain states based on measurement outcomes.
- **Fractal Layers**: Positions in the target sequence are assigned to layers following a fractal pattern, influencing the hierarchical processing order.
- **Machine Learning Models**:
  - **Random Forest Classifier**: Predicts the next probable state based on measurement probabilities, aiding in adjusting regressive coefficients.
  - **LSTM Network**: Captures temporal dependencies in sequences of measurement probabilities to predict future states and refine the quantum evolution.

## Features

- **Hybrid Quantum-Classical Approach**: Combines quantum mechanics with classical machine learning for enhanced performance.
- **Time-Dependent Hamiltonian**: Incorporates target sequences and adjusts dynamically with regressive coefficients and perturbations.
- **Fractal Pattern Processing**: Utilizes fractal layers to structure the search process efficiently.
- **Dynamic Learning**: Continuously trains the Random Forest and LSTM models during the evolution to improve predictions.

## Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/quantum-classical-fractal.git
   cd quantum-classical-fractal
   ```

2. **Create a Virtual Environment** (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

   **Dependencies**:

   - NumPy
   - Pandas
   - QuTiP
   - Matplotlib
   - Scikit-learn
   - TensorFlow (for Keras)
   - Other standard libraries (random, sys, warnings, os, datetime)

## Usage

1. **Prepare Your Data**:

   - Place your target sequence data in a CSV file (e.g., `your_data.csv`).
   - Ensure it has a column containing probability vectors named `Probability_Vector`.

2. **Configure Parameters**:

   - Modify the `main()` function parameters as needed (e.g., dimensions, number of runs).

3. **Run the Program**:

   ```bash
   python your_script_name.py
   ```

4. **Results**:

   - The program will output progress updates, save data to CSV files in the `simulation_results` directory, and display plots if convergence is achieved.

## Detailed Description

### 1. Data Preparation

- **Reading Target Sequence**: The program reads and processes the target probability vectors from a CSV file.
- **Normalization**: Ensures that each probability vector sums to 1.

### 2. Quantum System Initialization

- **Basis States**: Defines the qudit's basis states using QuTiP.
- **Initial State**: Starts with an equal superposition state to represent maximum uncertainty.

### 3. Hamiltonian Construction

- **Projection Operators**: Created for each basis state.
- **Transition Operators**: Facilitate transitions between neighboring states.
- **Time-Dependent Hamiltonian**: Combines transition operators, target operators, regressive coefficients, and random perturbations.

### 4. Solver Configuration

- **Time Evolution**: Uses QuTiP's `sesolve` to simulate the system's time evolution under the defined Hamiltonian.
- **Solver Options**: Configurable parameters for numerical accuracy.

### 5. Machine Learning Integration

- **Random Forest Classifier**:
  - Trained on measurement probabilities and target states.
  - Predicts the next state and influences regressive coefficients.
- **LSTM Network**:
  - Processes sequences of measurement probabilities.
  - Captures temporal patterns to predict future states.
  - Further refines regressive coefficients based on predictions.

### 6. Fractal Layer Assignment

- **Fractal Layers**: Assigns each position in the target sequence to a fractal layer, structuring the search hierarchically.
- **Processing Order**: Lower layers are resolved first, providing a foundation for higher layers.

### 7. System Evolution

- **Iterative Process**: Evolves over multiple runs and iterations until convergence or reaching maximum iterations.
- **Measurement and Adjustment**:
  - Measures the quantum state at each time step.
  - Adjusts regressive coefficients based on machine learning predictions.
- **Convergence Criteria**: Achieved when all positions match the target sequence within the assigned fractal layers.

## Physical Interpretation

- **Time and Rate of Change**: Emulates the symbiotic relationship between time granularity and the system's rate of change.
- **Energy Exchange and Oscillations**: Considers quantum oscillations in energy exchange to inform time step adjustments.
- **Random Perturbations**: Introduces emergent behavior, aiding the system in exploring the state space more thoroughly.

## Applications

- **Quantum Simulation**: Demonstrates a method to augment quantum simulations with classical algorithms.
- **Cryptography**: Potential implications for quantum-resistant cryptographic algorithms through insights into temporal dynamics.
- **Interdisciplinary Research**: Bridges quantum physics, machine learning, and complex systems, highlighting the benefits of interdisciplinary approaches.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgements

- **QuTiP**: Quantum Toolbox in Python for quantum simulations.
- **Scikit-learn and TensorFlow**: For machine learning components.
- **Community Contributions**: Inspired by collaborative discussions and shared knowledge in the quantum computing community.

## Contact

For questions or collaboration inquiries, please contact:

Jon Poplett  
Email: [JonPoplett@JGPTech.net](mailto:JonPoplett@JGPTech.net)

---

**Note**: This README provides a condensed overview of the project. For detailed explanations and documentation, please refer to the accompanying markdown files and comments within the code.
