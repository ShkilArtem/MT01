# MT01 — Logistic Regression and Numerical Optimization

A scientific-computing coursework project investigating binary classification
with regularized logistic regression. The implementation includes an explicit
objective function and gradient, fixed-step gradient descent, and Armijo
backtracking line search.

The project uses a supplied assignment and the Google Creative Lab Quick, Draw!
dataset. Assignment text, data-loading utilities, and interface scaffolding are
course materials rather than original research contributions.

## Methods

- Drawing rasterization, resizing, and centering.
- Binary class selection and training/test partitioning.
- Logistic probabilities and binary cross-entropy with L2 regularization.
- An unregularized bias term.
- Analytic gradients and central finite-difference checks.
- Fixed-step gradient descent and Armijo sufficient-decrease search.
- Classification metrics and a scikit-learn reference classifier.
- A Qt drawing interface for interactive classification experiments.

These items describe implemented functions and intended workflows. The complete
workflow remains partially integrated.

## Files

| File | Purpose |
| --- | --- |
| `Projet_QuickDraw_Sujet.ipynb` | Coursework notebook |
| `Projet_QuickDraw_Sujet.py` | Script-form assignment and implementations |
| `dessin_process.py` | Drawing primitives and image preprocessing |
| `dessin_viewer.py` | Qt drawing interface |

## Environment

The coursework imports NumPy, Matplotlib, Pillow, and scikit-learn. Interactive
drawing requires PyQt5; notebook interaction may additionally require ipympl and
ipywidgets. A pinned dependency specification is not included.

Use an isolated Python environment containing compatible dependencies, then open
the notebook with a Jupyter-compatible editor. Execute cells in order and review
the selected class pair, sample count, random state, and regularization settings.

Dataset-loading cells may download Quick, Draw! records. Review those cells
before execution; the repository does not provide a fully offline dataset setup.

## Optimization and Evaluation

The classifier minimizes regularized binary log loss. The bias is appended as a
constant feature and excluded from the L2 penalty. The gradient is computed
explicitly and can be compared against central finite differences.

The fixed-step and Armijo routines record objective values and gradient norms.
Compare stopping tolerances, iteration limits, and initial parameters consistently
when evaluating their behavior. Accuracy, precision, recall, and confusion
matrices describe classification; they should be computed on data not used for
parameter fitting.

Configured sample counts and displayed notebook outputs should not be treated as
independently reproduced evaluation results.

## Current Status

The optimization functions are implemented, but several analysis and integration
sections remain incomplete. In particular, the optimizer-comparison output loop
retains a placeholder, and `classify_my_bitmap` still contains `float(...)`.
Some gradient-check and plotting cells are commented out.

The complete script should therefore not be presented as a finished command-line
application. End-to-end classification results require a clean execution with
documented data and settings. Timing and function-evaluation counters also require
review before using them for rigorous performance comparisons.
