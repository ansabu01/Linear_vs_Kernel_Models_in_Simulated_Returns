# Kernel vs. Linear Methods in Simulated Asset Returns

**Main code:** [`src/main.py`](src/main.py)  
**Full report (PDF):** [`paper/main.pdf`](paper/main.pdf)  

This repository presents a fully reproducible simulation study comparing linear regression and kernel ridge regression with an RBF kernel across several nonlinear asset-return data-generating processes. All figures, tables, and outputs in the accompanying LaTeX report are produced directly by the Python code in `src/main.py`.

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
├── src/                        # Python source code
│   ├── images/                 # Generated figures (PDF) used in the paper
│   └── main.py                 # Simulations, models, metrics, plots
│
├── paper/                      # LaTeX report and compiled PDF
│   ├── main.tex                # LaTeX source of the report
│   └── main.pdf                # Compiled report
│
├── requirements.txt            # Python dependencies for full reproducibility
├── LICENSE                     # MIT License for open-source distribution
├── README.md                   # Project overview and usage instructions
└── .gitignore                  # Ignore virtualenvs, caches, LaTeX builds, etc.
```

## 3. How to Reproduce Results

From the project root, run:
```bash
python src/main.py              # Windows / standard usage
python3 src/main.py             # Linux / macOS
```

All generated figures will be saved in:
```text
src/images/
```

These figures are then automatically included in `paper/main.tex`.

## 4. Requirements

The project requires the following Python packages:

- numpy
- pandas
- matplotlib
- scikit-learn

Install with pip:
```bash
pip install -r requirements.txt
```

Install in a conda environment:
```bash
conda create -n kernel-linear python=3.12 -y
conda activate kernel-linear
pip install -r requirements.txt
```

Note: Installing via pip inside the conda environment ensures consistent versions.

## 5. License

This project is released under the MIT License.  
See the `LICENSE` file for details.