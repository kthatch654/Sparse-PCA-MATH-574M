# R Code for Tuning Sparse PCA Analysis using Index of Sparseness

This R code provides a set of tools for performing and analyzing Sparse Principal Component Analysis (SPCA). It is designed to help in determining the optimal number of principal components, tuning the sparsity parameter (alpha) in SPCA using the Index of Sparseness (IS), and visualizing the results.

## Functions

The package includes the following main functions:

### 1. `create_scree_plot(data)`

Generates a scree plot from a given dataset to help diagnose the number of principal components to use in PCA analysis.

- **Parameters**: 
  - `data`: Numeric matrix or data frame where rows are observations and columns are variables.
- **Returns**: 
  - A scree plot as a `ggplot` object.

### 2. `tune_spca(data, alpha_grid, n_components)`

Performs Sparse PCA (SPCA) tuning using the Index of Sparseness. It iterates over a range of alpha values to find the one that maximizes the IS.

- **Parameters**: 
  - `data`: Numeric matrix or data frame for PCA.
  - `alpha_grid`: A numeric vector of alpha values to be tested.
  - `n_components`: Number of principal components to consider.
- **Returns**: 
  - A list of SPCA results for each alpha value.

### 3. `plot_spca_results(alpha_grid, spca_results)`

Graphs the results of SPCA tuning, showing the relationship between different alpha values and their corresponding Index of Sparseness.

- **Parameters**: 
  - `alpha_grid`: A numeric vector of alpha values that were tested.
  - `spca_results`: The list of results from `tune_spca`.
- **Returns**: 
  - A plot as a `ggplot` object, showing IS vs alpha.

### 4. `find_optimal_spca(alpha_grid, spca_results)`

Finds the optimal IS and alpha values from the list of SPCA results, and returns these quantities along with the optimal SPCA model.

- **Parameters**: 
  - `alpha_grid`: A numeric vector of alpha values that were tested.
  - `spca_results`: The list of results from `tune_spca`.
- **Returns**: 
  - A list containing the optimal alpha value, the optimal IS value, and the optimal SPCA model.
