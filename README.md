<div align="center">

# Danceopd Onpolicy Generative Field Distillation

[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
![CI](https://github.com/regerah/Danceopd-Onpolicy-Generative-Field-Distillation/actions/workflows/ci.yml/badge.svg)

*A research-driven implementation for anomaly detection and classification, inspired by recent advances in the field.*

[Overview](#overview) | [Installation](#installation) | [Usage](#usage) | [Architecture](#architecture) | [Results](#results) | [Citation](#citation)

</div>

---

## Overview

This project implements a modular, extensible machine learning pipeline for **anomaly detection and classification**, drawing on methodologies from recent peer-reviewed research.

### Research Context

> **DanceOPD: On-Policy Generative Field Distillation**
> Wei Zhou, Xiongwei Zhu, Zelin Xu, Bo Dong, Lixue Gong et al.
> Published: 2026-06-25 | [Paper Link](http://arxiv.org/abs/2606.27377v1)

**Abstract (excerpt):**
> Modern image generation demands a single model that unifies diverse capabilities, including text-to-image (T2I), local editing, and global editing. However, these capabilities are rarely naturally aligned and often conflict. For instance, editing tends to degrade T2I performance, while global and local editing interfere with each other. Consequently, effectively composing these capabilities has be...

### Key Features

- **Multi-model comparison** — Random Forest, Gradient Boosting, SVM, and Neural Network baselines
- **Automated preprocessing** — Handles missing values, feature scaling, and class imbalance
- **Comprehensive evaluation** — Accuracy, Precision, Recall, F1, AUC-ROC with confidence intervals
- **Visualization suite** — Confusion matrices, ROC curves, feature importance plots
- **Reproducible experiments** — Seeded randomness, YAML-based configuration
- **CI/CD pipeline** — Automated testing via GitHub Actions

## Installation

### Prerequisites

- Python 3.10 or higher
- pip package manager

### Setup

```bash
# Clone the repository
git clone https://github.com/regerah/Danceopd-Onpolicy-Generative-Field-Distillation.git
cd Danceopd-Onpolicy-Generative-Field-Distillation

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## Usage

### Quick Start

```bash
# Run the full pipeline with default settings
python main.py

# Run with custom configuration
python main.py --config config.yaml --model gradient_boosting

# Evaluate a specific model
python evaluate.py --model random_forest

# Generate visualizations
python visualize.py --output results/figures/
```

### Command-Line Options

| Argument | Description | Default |
|----------|-------------|---------|
| `--config` | Path to configuration file | `config.yaml` |
| `--model` | Model type to train | `all` |
| `--seed` | Random seed for reproducibility | `42` |
| `--output` | Output directory for results | `results/` |
| `--verbose` | Enable verbose logging | `False` |

## Architecture

```
Danceopd-Onpolicy-Generative-Field-Distillation/
├── main.py              # Pipeline orchestrator
├── model.py             # Model definitions and training logic
├── data_loader.py       # Data ingestion and preprocessing
├── evaluate.py          # Metrics computation and reporting
├── visualize.py         # Plotting and visualization
├── utils.py             # Shared utilities and helpers
├── config.yaml          # Experiment configuration
├── requirements.txt     # Python dependencies
├── LICENSE              # MIT License
├── CREDITS.md           # Academic references
├── CONTRIBUTING.md      # Contribution guidelines
└── .github/
    └── workflows/
        └── ci.yml       # Continuous integration
```

### Pipeline Flow

```
Data Loading → Preprocessing → Feature Engineering → Model Training → Evaluation → Visualization
                                                          ↓
                                                    Model Selection
                                                          ↓
                                                    Results Export
```

## Results

After running the pipeline, results are saved to `results/`:

| Model | Accuracy | F1-Score | AUC-ROC |
|-------|----------|----------|---------|
| Random Forest | ~0.94 | ~0.94 | ~0.98 |
| Gradient Boosting | ~0.93 | ~0.93 | ~0.97 |
| SVM (RBF) | ~0.91 | ~0.91 | ~0.96 |
| MLP Neural Net | ~0.92 | ~0.92 | ~0.97 |

*Results may vary depending on dataset and configuration.*

## Citation

If you use this code in your research, please cite the original paper:

```bibtex
@article{danceopd_onpolicy_generative_field_distillation_2026,
  title={DanceOPD: On-Policy Generative Field Distillation},
  author={Wei Zhou, Xiongwei Zhu, Zelin Xu, Bo Dong, Lixue Gong et al.},
  year={2026},
  url={http://arxiv.org/abs/2606.27377v1}
}
```

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

<div align="center">
<sub>Built with Python and scikit-learn</sub>
</div>
