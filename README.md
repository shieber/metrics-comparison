# Normalization Methods Interactive Demo

An interactive Jupyter notebook demonstrating different normalization methods for student scores, served as a web application using Voila.

## Run on Binder (no installation required)

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/shieber/metrics-comparison/master?urlpath=voila/render/normalization_interactive_demo.ipynb)

Click the badge above or use this URL:
```
https://mybinder.org/v2/gh/shieber/metrics-comparison/master?urlpath=voila/render/normalization_interactive_demo.ipynb
```

## Run Locally

### Prerequisites

- Python 3.11+
- Conda (recommended) or pip

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/shieber/metrics-comparison.git
   cd metrics-comparison
   ```

2. Create and activate a conda environment:
   ```bash
   conda create -n metrics-comparison python=3.11
   conda activate metrics-comparison
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running with Voila (recommended)

Voila renders the notebook as an interactive web app, hiding all code cells:

```bash
voila normalization_interactive_demo.ipynb
```

Then open http://localhost:8866 in your browser.

### Running with JupyterLab

For development or to see the code:

```bash
jupyter lab normalization_interactive_demo.ipynb
```

Run all cells to see the interactive visualization.

## Project Structure

```
├── normalization_interactive_demo.ipynb  # Main notebook
├── requirements.txt                       # Python dependencies
├── voila.json                             # Voila configuration
└── README.md                              # This file
```

## Technical Notes

### Voila Compatibility

The notebook uses a JavaScript-based approach to initialize the visualization. This is necessary because:

1. Voila executes all Python cells *before* rendering the page
2. Generating matplotlib output inside an ipywidgets `Output` widget during this pre-render phase can block indefinitely
3. The solution uses `requestIdleCallback` to trigger the initial plot after the browser is idle and widgets are fully initialized


