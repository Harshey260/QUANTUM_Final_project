# Grover's Algorithm — How to Run

This notebook implements **Grover's quantum search algorithm** on a 10-qubit system using [Qiskit](https://qiskit.org/) and runs on **Google Colab**. It searches a space of 1,024 states and identifies two marked (target) states using quantum amplitude amplification.

---

## Prerequisites

No local installation is needed. You only need:

- A Google account
- A web browser
- Access to [Google Colab](https://colab.research.google.com)

---

## Steps to Run

### 1. Open the Notebook in Google Colab

1. Go to [https://colab.research.google.com](https://colab.research.google.com)
2. Click **File → Upload notebook**
3. Upload the file `Welcome_to_Colab__16_.ipynb`

> Alternatively, if the notebook is already in your Google Drive, use **File → Open notebook → Google Drive**.

### 2. Enable GPU (Recommended)

The notebook is configured to use a T4 GPU for faster simulation.

1. Go to **Runtime → Change runtime type**
2. Set **Hardware accelerator** to **T4 GPU**
3. Click **Save**

### 3. Run the Notebook

Run all cells in order from top to bottom:

- **Option A:** Click **Runtime → Run all** (`Ctrl+F9` / `Cmd+F9`)
- **Option B:** Run each cell manually with the ▶ button or `Shift+Enter`

> ⚠️ Cells must be run **in order**. Later cells depend on variables and functions defined in earlier ones.

---

## What Each Section Does

| Section | Description |
|---|---|
| **Cell 1 – Install dependencies** | Installs `qiskit`, `qiskit-aer`, `matplotlib`, and `pylatexenc` |
| **Cell 2 – Imports & Config** | Sets up the 10-qubit search space, defines the 2 target states, and calculates the optimal number of Grover iterations (~25) |
| **Task 1 – Superposition** | Applies Hadamard gates to create a uniform superposition; saves circuit and distribution plots |
| **Task 2 – Oracle** | Marks the two target states by flipping their phase; saves circuit and amplitude plots |
| **Task 3 – Diffusion** | Applies the Grover diffusion (inversion about the mean) operator; saves circuit and amplitude plots |
| **Task 4 – Iteration** | Runs the full Grover loop and tracks how probability of finding a target grows over iterations |
| **Task 5 – Measurement** | Simulates the final circuit with 4,096 shots at 1, 3, 5, and 18 iterations; saves histograms |

---

## Configuration (Optional)

You can modify these variables at the top of the notebook before running:

```python
N_QUBITS = 10               # Number of qubits (search space = 2^N_QUBITS)
TARGETS  = ["0110011010",   # Binary strings of the states to search for
             "1101010001"]
SHOTS    = 4096             # Number of measurement shots for simulation
```

> If you change `N_QUBITS` or the number of targets, the optimal iteration count (`OPT_ITERS`) will be recalculated automatically.

---

## Output Files

After the notebook finishes, the following `.png` files will be saved to the Colab session storage:

| File | Description |
|---|---|
| `task1_superposition_circuit.png` | Circuit diagram after Hadamard layer |
| `task1_superposition_distribution.png` | Flat probability distribution |
| `task2_oracle_circuit.png` | Oracle circuit marking target states |
| `task2_oracle_amplitudes.png` | Amplitude plot after oracle |
| `task3_diffusion_circuit.png` | Diffusion operator circuit |
| `task3_diffusion_amplitudes.png` | Amplitude plot after diffusion |
| `task4_iteration_probability.png` | Success probability vs. iteration count |
| `task4_grover_circuit_1iter.png` | Full Grover circuit (1 iteration) |
| `task5_histogram_iters_01/03/05/18.png` | Measurement histograms at each iteration count |
| `task5_combined_histograms.png` | Combined 4-panel histogram comparison |

To download these files, right-click any file in the **Files** panel (left sidebar in Colab) and select **Download**.

---

## Troubleshooting

| Issue | Fix |
|---|---|
| `ModuleNotFoundError: qiskit` | Re-run Cell 1 to install dependencies |
| Cells out of order | Go to **Runtime → Restart and run all** |
| Slow execution | Make sure GPU is enabled (see Step 2) |
| Figures not displaying | Figures are saved as `.png` files; check the Files panel on the left |
