# Quantum Circuit Builder

An interactive, browser-based quantum circuit simulator. Build circuits by dragging gates onto qubit wires and watch the quantum state update in real time \-- no installation required.

Open `quantum_circuit_builder_1.html` in any modern browser. No server or dependencies needed.

---

## Features

- 7 quantum gates: H, X, Y, Z, S, T, and CNOT  
- 1-4 qubits, configurable on the fly  
- Drag-and-drop interface \-- move gates between cells or drop to trash  
- Real-time statevector simulation  
- Measurement probabilities with complex amplitudes  
- Interactive 3D Bloch sphere per qubit (drag to orbit)  
- Step-by-step circuit analysis with state notation  
- Built-in presets: Bell state, GHZ, Hadamard on all qubits, QFT

---

## How to Use

### Building a circuit

1. Click a gate in the toolbar to select it, or drag it directly onto a qubit wire  
2. Rows are qubits (q0, q1, ...); columns are time steps (t1-t7)  
3. Drag placed gates to move them; hover and click **x** to delete, or drag to the trash zone

### CNOT gate

1. Drag **CX** from the palette onto the control qubit \-- a pulsing dot appears  
2. Drag the dot to another qubit in the same column to place the target

---

## Gates

**H \-- Hadamard** Creates equal superposition. On the Bloch sphere: 180-degree rotation around the X+Z diagonal.

**X \-- Pauli-X** Quantum NOT gate. Flips |0\> and |1\>.

**Y \-- Pauli-Y** Bit flip \+ phase shift.

**Z \-- Pauli-Z** Phase flip only. Leaves |0\> unchanged, flips the sign of |1\>.

**S \-- S Gate** 90-degree phase rotation (equivalent to sqrt(Z)).

**T \-- T Gate** 45-degree phase rotation (equivalent to sqrt(S)). Together with Clifford gates, enables universal quantum computation.

**CX \-- CNOT** Flips the target qubit conditioned on the control. When the control is in superposition, creates entanglement.

---

## Presets

**Bell** \-- 2-qubit maximally entangled Bell state

**GHZ** \-- 3-qubit Greenberger-Horne-Zeilinger state

**H on all** \-- Hadamard on all qubits (uniform superposition)

**QFT** \-- 2-qubit Quantum Fourier Transform

---

## Implementation

Single self-contained HTML file \-- no build step, no external libraries.

- Statevector simulation with complex arithmetic over the full 2^n basis  
- CNOT via direct index mapping  
- Bloch vectors from the reduced density matrix (partial trace)  
- 3D Bloch sphere rendered on canvas with orthographic projection and mouse orbit

