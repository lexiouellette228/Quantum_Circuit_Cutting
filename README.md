# Quantum_Circuit_Cutting
# Quantum Circuit Cutting Group Project 

# Below is a description of the project, our demonstration process, and the an explantation of the results of the project. 

# What is Quantum Circuit Cutting? 

Quantum circuit cutting is the process of taking a larger quantum circuit and “cutting” it into smaller subcircuits.
Once these smaller subcircuits have been created, they can then be executed either independently on the same quantum device, or independently across multiple quantum devices.
Once executed, the result of all subcircuits can then be recombined to obtain the original result of the larger quantum circuit  (Using some form of post processing).

Why Do We Need It?
One of the main problems quantum circuit cutting solves is the challenge of executing circuits that are too large for a particular quantum computer. 
Most modern quantum devices are limited by the number of qubits they can support, which significantly restricts not only the size but also the complexity of the circuits they can run.
Continued research into quantum circuit cutting could, theoretically, enhance the capabilities of quantum algorithms for tasks in things like machine learning and cryptography.

Demonstration
Here we have a demonstration of quantum circuit cutting. Using wire cutting, we have taken a 7-qubit circuit and split it into 2 separate 4-qubit circuits. The advantage to this method is that we can split a wider variety of circuits at the cost of increased overhead.
Quantum Wire cutting utilizes a pair of Move instructions that act like a series of swap gates inside the quantum compute. These transfer the inked state between the two halves of the original circuit. This link is facilitated by adding an ancillary circuit to the second cut half where the linked qubit from A will be copied between the two halves by a quantum link inside of the computer.
After the circuits have been decomposed, we set them up to be able to run as a series of sub experiments. These sub experiments construct a Quasiprobability Distribution that will later be used to reconstruct the larger circuit.
For this experiment, we have chosen to run them once on a simulator, and once on an actual quantum computer by utilizing IMBQ’s cloud quantum services.
Once they have ran on their respective backends, we reconstruct the expectation value for each subcircuit's Quasiprobability Distribution and then combine them to get the expectation value for the original 7-qubit circuit.

Discussing the findings
The simulator produced a reconstructed expectation value that closely matched the exact expectation value, with only a small relative error of approximately -12.2%. This shows that in a noise-free environment, circuit cutting can effectively approximate the behavior of a full quantum circuit. 
However, the real quantum computer produced a reconstructed expectation value that deviated slightly more from the correct expectation value, with a relative error of approximately –16.7%. The larger deviation is due to the presence of noise that affects the accuracy of the final measurement.  Resulting in less accurate results. 
The larger discrepancy observed on the real quantum computer is primarily due to several sources of noise, such as gate errors, readout errors, and decoherence. These noise effects are further amplified by the additional operations introduced during circuit wire cutting, including mid-circuit measurements and state preparations. In contrast, the simulator backend does not suffer from these imperfections, leading to reconstructed values that are much closer to the theoretical expectation.

Conclusion
Quantum circuit cutting enables the simulation of large quantum circuits by splitting them into smaller, more manageable subcircuits that can run on limited hardware. 
Our experiment showed that reconstructed expectation values are more accurate on simulators, but less accurate on real quantum computers due to noise. 
Despite these challenges, circuit cutting remains a promising strategy for scaling quantum computers, especially as hardware improves and noise mitigation techniques advance. 
