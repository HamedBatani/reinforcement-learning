# HW1 simulation answers

**[Open the notebook](HW1_402101339.ipynb)** · **[Browse saved figures](results/)**

The notebook contains my implementations, experimental results, and written analysis. Its 41 cells include 12 code cells, and its saved outputs contain no recorded error objects. The accompanying 18 PNG figures are organized by assignment question and subpart.

## Run locally

Use Python 3 with NumPy, Matplotlib, and Jupyter. From this directory:

```bash
python -m pip install -r ../../../requirements.txt
python -m jupyterlab HW1_402101339.ipynb
```

Run the cells in order. No external dataset is required: the notebook generates the bandit environments and reward samples. Figures are written to paths relative to this directory under `results/`. Running the notebook can overwrite the copied figure files; use a separate working copy if you want to keep the archived outputs unchanged.

The dependency list is inferred from imports and provides an execution guide, not a recovered environment lockfile. Fixed seeds are included in the notebook, but package versions and the original execution environment were not archived. The notebook has been inspected and its code syntax checked for publication; its experiments have not been freshly rerun as part of that review.
