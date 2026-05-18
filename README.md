# ABDC Quantum Computing Session Notebooks

A small collection of beginner-friendly Qiskit notebooks used for an ABDC quantum computing session.

## What This Project Does

This repository contains hands-on Jupyter notebooks that introduce core quantum computing ideas with Qiskit. The notebooks walk through circuit construction, simulation, measurement, and selected IBM Quantum hardware examples.

## Features

- Superposition and entanglement examples
- Quantum teleportation walkthrough
- Bernstein-Vazirani algorithm implementation
- Local simulator examples using Qiskit Aer
- Optional legacy IBM Quantum hardware cells

## Tech Stack

- Python
- Jupyter Notebook
- Qiskit
- NumPy
- Matplotlib

## Folder Structure

```text
.
├── README.md
├── requirements.txt
├── .gitignore
└── notebooks/
    ├── 01_superposition_and_entanglement.ipynb
    ├── 02_quantum_teleportation.ipynb
    └── 03_bernstein_vazirani_algorithm.ipynb
```

## Installation

These notebooks use legacy pre-1.0 Qiskit APIs such as `IBMQ`, `BasicAer`, `execute`, and `qiskit.tools.jupyter`. Python 3.8 to 3.10 is the safest choice for this legacy environment. Python 3.11 may also work if compatible wheels are available for your platform.

Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Run Locally

Start Jupyter Notebook from the repository root:

```bash
jupyter notebook notebooks
```

Then open one of the notebooks in order:

1. `notebooks/01_superposition_and_entanglement.ipynb`
2. `notebooks/02_quantum_teleportation.ipynb`
3. `notebooks/03_bernstein_vazirani_algorithm.ipynb`

## Example Usage

Open the first notebook and run the cells from top to bottom:

```bash
jupyter notebook notebooks/01_superposition_and_entanglement.ipynb
```

Most examples can run locally with the Qiskit simulator. Cells that use IBM Quantum hardware require an IBM Quantum account and may need a currently available backend.

## Environment Variables

No environment variables are required for local simulator runs.

If you use IBM Quantum hardware, configure your IBM Quantum credentials outside this repository. Do not commit API tokens or local credential files.

## Testing and Verification

There is no automated test suite because this project is notebook-based teaching material.

To verify notebook files are valid JSON:

```bash
python -m json.tool notebooks/01_superposition_and_entanglement.ipynb > /dev/null
python -m json.tool notebooks/02_quantum_teleportation.ipynb > /dev/null
python -m json.tool notebooks/03_bernstein_vazirani_algorithm.ipynb > /dev/null
```

To verify the local environment, start Jupyter and run the simulator cells in the notebooks:

```bash
jupyter notebook notebooks
```

## Troubleshooting

### `ImportError` or missing Qiskit APIs

The notebooks use older Qiskit APIs. Install the pinned dependencies from `requirements.txt` rather than the latest Qiskit release.

### IBM Quantum backend errors

Some notebook cells reference legacy IBM Quantum backend names such as `ibmq_16_melbourne`. If a backend is unavailable, choose an available backend from your IBM Quantum account or run the simulator-only cells.

### Jupyter widget or watcher issues

The hardware job watcher uses legacy Jupyter widget integrations. If widgets do not render, the notebook examples can still be followed with simulator cells and standard job output.

## Roadmap

- Update notebooks to the modern Qiskit 1.x API
- Add clean Python script examples alongside the notebooks
- Add optional notebook execution checks with `nbconvert`
- Replace retired IBM Quantum backend names with current examples

## License

No license file is currently included. Add a license before publishing this repository if you want to define how others may use or share the material.
