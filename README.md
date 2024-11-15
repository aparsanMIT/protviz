# ProtViz: Protein Structure Comparison Tool

A Python-based tool for comparing experimental PDB structures with AlphaFold predictions, with a focus on alpha helix analysis.

## Overview
ProtViz provides automated structure fetching, geometric analysis, and visualization capabilities to analyze how well AlphaFold predicts secondary structure elements. The tool implements a geometric approach to identify alpha helices based on CA-CA distances and characteristic helical spacing.

## Features
- Fetches structures from PDB and AlphaFold databases
- Identifies alpha helices using geometric criteria:
 - Sequential CA-CA distances (3.0-4.5Å)
 - i to i+3 spacing (4.5-6.5Å)
- Side-by-side 3D visualization of structures
- Statistical analysis of prediction accuracy
- Batch processing of multiple protein pairs

## Installation
```bash
# Create and activate virtual environment
python -m venv protviz_env
source protviz_env/bin/activate  # On Windows: protviz_env\Scripts\activate

# Install required packages
pip install biopython numpy pandas matplotlib py3Dmol requests
```

## Usage
``` bash
# Basic usage
from protviz import HelixComparator

# Initialize comparator
comparator = HelixComparator()

# Analyze a single protein pair
pdb_id = "1AKE"
uniprot_id = "P69441"
results = comparator.analyze_pair(pdb_id, uniprot_id)

# Batch analysis
results_df = comparator.analyze_all_proteins()
```

## Example Output
Analyzing 1AKE - P69441
  PDB helices: 12
  AF helices: 11
  Difference: -1
