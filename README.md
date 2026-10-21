# Exploring a Normal Distribution Dataset with NumPy

## Research Question

How can the descriptive statistics of a two-dimensional numerical dataset —
including its mean, median, variance, and standard deviation — be computed
efficiently using NumPy, and what do those statistics reveal about the shape
and spread of the underlying data?

This project treats the question as both a **methods question** (how to slice,
aggregate, and summarise an array along different axes) and a **data question**
(what the resulting statistics say about the distribution).

## Dataset Source and Usage Permissions

The analysis uses a single file, `normal_distribution.csv`, a comma-separated
numeric dataset containing 24 rows and 8 columns of values drawn from a normal
distribution.

> **[Replace this sentence with the true provenance]** The dataset was provided
> as course material for CISC7204 and is used here for educational purposes
> only. It contains no personal data, no identifiers, and no restricted or
> licensed content. No passwords, API keys, or sensitive information are stored
> in this repository.

If you obtained the file from another source (a public dataset, a textbook
companion site, or a simulation you generated yourself), state that source and
its licence here instead.

## Methods and Tools

- **Language:** Python 3
- **Library:** NumPy (loaded via `import numpy as np`)
- **Loading:** `np.genfromtxt('normal_distribution.csv', delimiter=',')` reads
  the CSV directly into a 2-D `ndarray`.
- **Array selection:** basic slicing and indexing (`dataset[0:2]`,
  `dataset[:, -1]`, `dataset[:, 0:3]`, `dataset[:, -3:]`, `dataset[-2:, 0:2]`)
  is used to isolate rows, columns, and sub-matrices.
- **Aggregation:** `np.mean`, `np.median`, `np.var`, `np.std`, and `np.sum`
  are applied both to whole arrays and along specific axes (`axis=0` for
  column-wise variance, `axis=1` for row-wise sums).

The notebook is organised as twelve numbered steps, each with a short comment
describing the operation being performed, so the analysis can be followed
line by line.

## Key Findings

- **Row-level centrality:** The mean of the third row is approximately
  **100.20**, and the median of the final row is approximately **99.19**,
  both close to the centre expected from a normal distribution centred near 100.
- **Column-level spread:** Column variances range from roughly **16.18** to
  **29.79**, showing that the columns are similarly but not identically
  dispersed.
- **Overall spread:** The standard deviation of the entire dataset is
  approximately **4.84**, indicating that most values sit within a few units
  of the mean.
- **Axis behaviour:** Row-wise sums (`axis=1`) fall in the range of roughly
  **776 to 831**, consistent with eight values averaging near 100 each, and
  the per-column variance output confirms that `axis=0` reduces across rows.

**Limitation:** The dataset is small (24 × 8) and appears to be a single
synthetic draw from a normal distribution. The descriptive statistics therefore
describe this one sample only; no inferential test, confidence interval, or
comparison against a theoretical distribution is performed, so the results
should not be generalised beyond the file analysed.

## Instructions for Running the Analysis

1. **Clone the repository**

   ```bash
   git clone https://github.com/<your-username>/.data-science-project.git
   cd .data-science-project
