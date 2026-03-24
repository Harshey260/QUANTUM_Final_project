# 🚀 Grover’s Algorithm — Quantum Search (Qiskit + Colab)

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Qiskit](https://img.shields.io/badge/Qiskit-Latest-purple)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-orange)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Overview
This project demonstrates a **complete implementation of Grover’s Algorithm** using Qiskit.

Grover’s Algorithm provides a **quadratic speedup** for searching an unsorted database.

---

## 🎥 Demo Preview

> Add your screenshots below after running the notebook:

![Circuit](images/circuit.png)
![Histogram](images/histogram.png)

---

## 🧠 How It Works

### 1️⃣ Superposition
All qubits are initialized into equal probability using Hadamard gates.

### 2️⃣ Oracle
Marks the target state by flipping its phase.

### 3️⃣ Diffusion Operator
Amplifies the probability of the marked state.

### 4️⃣ Iterations
Repeats the process to maximize success probability.

---

## 📊 Explanation Diagram

![Grover Flow](images/grover_flow.png)

---

## ⚙️ Installation

```bash
pip install qiskit qiskit-aer matplotlib
```

---

## ▶️ Usage

1. Open notebook in Google Colab  
2. Run all cells sequentially  
3. Observe circuit + histogram outputs  

---

## 🧪 Parameters

| Parameter | Description |
|----------|------------|
| N_QUBITS | Number of qubits |
| TARGETS | Target states |
| ITERATIONS | Number of Grover iterations |

---

## 📈 Results

- Initial: Uniform distribution  
- Final: Peak probability at target state  
- Optimal iterations maximize success  

---

## 📁 Folder Structure

```
project/
│── README.md
│── notebook.ipynb
│── images/
    ├── circuit.png
    ├── histogram.png
    ├── grover_flow.png
```

---

## 🖼️ Adding Screenshots

After running notebook in Colab:

```python
from qiskit.visualization import plot_histogram
plot_histogram(counts).savefig("histogram.png")
```

Upload images into `/images` folder.

---

## 📚 References

- Qiskit Docs  
- Nielsen & Chuang  

---

## 👨‍💻 Author
Grover Algorithm Implementation for learning + visualization.
