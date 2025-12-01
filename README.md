# Kernel vs. Linear Methods in Simulated Asset Returns

**Main code:** [`src/main.ipynb`](src/main.ipynb)  
**Full report (PDF):** [`paper/main.pdf`](paper/main.pdf)  

This repository presents a fully reproducible simulation study comparing linear regression and kernel ridge regression with an RBF kernel across several nonlinear asset-return data-generating processes.

## 1. Project Overview

The study evaluates four scenarios of increasing nonlinear complexity:

- Quadratic Nonlinearity  
- Quadratic + Interaction Effects  
- Quadratic + Interaction + Regime Switching  
- High-Noise Environment  

The objectives are to assess:

- the limitations of linear regression under nonlinear dynamics,  
- the ability of kernel methods to approximate complex factor structures,  
- and the impact of rising idiosyncratic noise on predictive accuracy.

## 2. Repository Structure

```text
Linear_vs_Kernel_Models_in_Simulated_Returns/
│
├── src/                            Python source code
│   ├── images/                     Generated figures (PDF) used in the paper
│   └── main.ipynb                  Simulations, models, metrics, plots
│
├── paper/                          LaTeX report and compiled PDF
│   ├── main.tex                    LaTeX source of the report
│   └── main.pdf                    Compiled report
│
├── requirements.txt                Python dependencies for full reproducibility
├── LICENSE                         MIT License for open-source distribution
├── README.md                       Project overview and usage instructions
└── .gitignore                      Ignore virtualenvs, caches, LaTeX builds, etc.
```

## 3. How to Reproduce Results

From the project root, run:
```bash
jupyter lab src/main.ipynb          # Recommended
jupyter notebook src/main.ipynb     # Classic interface
```

You can also export the notebook as a .py script, and run it:
```bash
jupyter nbconvert --to script src/main.ipynb

python src/main.py                  # Windows/macOS/Linux
python3 src/main.py                 # Alternative command on macOS/Linux
```

All generated figures will be saved in `src/images/`.
These figures are then automatically included in `paper/main.tex`.

## 4. Requirements

Ensure that the following software is installed:

- Python 3.8 or higher (3.12 recommended)
- Jupyter Notebook (recommended) or JupyterLab

#### Python

Download Python from: https://www.python.org/downloads/.

Verify the Python installation:
```bash
python --version                    # Windows/macOS/Linux
python3 --version                   # Alternative command on macOS/Linux
```

#### Jupyter

Install Jupyter Notebook and JupyterLab with pip (recommended):
```bash
pip install notebook jupyterlab
```

Install Jupyter Notebook and JupyterLab in a conda environment (requires Anaconda or Miniconda):
```bash
conda install -c conda-forge notebook jupyterlab
```

Verify the Jupyter installation (works for both pip and conda):
```bash
jupyter notebook --version
jupyter lab --version
```

#### Packages

The project requires the following Python packages:

- numpy
- pandas
- matplotlib
- scikit-learn

Install packages with pip + venv (recommended):
```bash
# Create virtual environment
python -m venv kernel-linear        # Windows/macOS/Linux
python3 -m venv kernel-linear       # Alternative command on macOS/Linux

# Activate environment
kernel-linear\Scripts\activate      # Windows
source kernel-linear/bin/activate   # macOS/Linux

# Install dependencies
pip install -r requirements.txt
```

Install packages in a conda environment (requires Anaconda or Miniconda):
```bash
# Create virtual environment
conda create -n kernel-linear python=3.12 -y

# Activate environment
conda activate kernel-linear

# Install dependencies
pip install -r requirements.txt     # Still use pip for consistent versions
```

Note: Installing the project in a dedicated virtual environment ensures clean dependency isolation and avoids conflicts with system-wide packages.

## 5. License

This project is released under the MIT License.  
See the `LICENSE` file for details.