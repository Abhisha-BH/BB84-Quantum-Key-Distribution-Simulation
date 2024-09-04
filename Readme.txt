BB84 Quantum Key Distribution (QKD) Simulation
Overview
This project implements a simulation of the BB84 Quantum Key Distribution (QKD) protocol in Python. The BB84 protocol is one of the first and most well-known quantum cryptographic protocols, designed to securely exchange encryption keys between two parties (Alice and Bob) while detecting any eavesdropping (Eve).

Features
Qubit Simulation: Models the behavior of quantum bits (qubits) using the Hadamard and Pauli-X gates.
Quantum User Interaction: Simulates Alice and Bob's interaction, including key generation, transmission, and reception of qubits.
Eavesdropping Detection: Optionally includes Eve (an eavesdropper) to test the security of the QKD protocol.
Verbose Mode: Provides detailed logs of the QKD process, including basis generation and key exchange.

Usage
Run the BB84 QKD simulation with various options.

Command-Line Arguments
-q, --qubits: Required. Number of qubits to use in the key exchange.
-i, --iterate: Number of iterations to run the simulation (default is 1).
-e, --eve: Include Eve (the eavesdropper) in the simulation.
-v, --verbose: Enable verbose mode to display detailed logs of the QKD process.
Example Commands

Basic QKD Simulation:
python qkd.py --qubits 100

QKD Simulation with Eve:
python qkd.py --qubits 100 --eve

Verbose QKD Simulation with Multiple Iterations:
python qkd.py --qubits 100 --iterate 10 --verbose

How It Works
Alice generates random bits and basis: Alice generates a random sequence of bits and a corresponding random sequence of basis (rectilinear or diagonal).
Alice sends qubits to Bob: Alice encodes her bits using the chosen basis and sends the qubits to Bob.
Eve (optional): If Eve is present, she intercepts the qubits, measures them with a random basis, and sends them to Bob.
Bob measures the qubits: Bob receives the qubits and measures them using his own random basis.
Key Generation: Alice and Bob compare their basis and discard the bits where their basis did not match. The remaining bits form the encryption key.
