# SVD and Linear Regression Project

## **Overview**

This project demonstrates the process of computing the Singular Value Decomposition (SVD) of a matrix manually, reconstructing the matrix, and solving a system of linear equations using SVD-derived coefficients. It also validates the results against Scikit-Learn's `LinearRegression` package, providing a comprehensive example of both numerical linear algebra and machine learning techniques.

---

## **Motivation**

My primary goal of this project was to bridge the gap between theoretical understanding and practical application of SVD. By implementing SVD manually, I gained deeper insights into:

1. **Matrix Decomposition**: Understanding how SVD works beyond library calls.
2. **Numerical Methods**: Highlighting eigenvalues, eigenvectors, and their role in decomposition.
3. **Pseudoinverse and Applications**: Exploring how SVD enables solutions to least-squares problems.
4. **Validation of Results**: Comparing manual computation with a standard library like Scikit-Learn to ensure accuracy and robustness.

---

## **Methodology**

### 1. **Singular Value Decomposition (SVD)**

- **Input Matrix**: The matrix \( A \) is used as the starting point.
- **Step 1**: Compute \( A^T A \), the Gram matrix, to find eigenvalues and eigenvectors.
- **Step 2**: Solve the characteristic polynomial of \( A^T A \) to find its eigenvalues (\( \lambda \)).
- **Step 3**: Compute singular values (\( \sigma \)) as the square root of the eigenvalues.
- **Step 4**: Construct the diagonal \( \Sigma \) matrix from the singular values.
- **Step 5**: Derive eigenvectors of \( A^T A \) to form the \( V \) matrix, normalized to ensure orthonormality.
- **Step 6**: Compute \( U \) from \( A v_i \) for each \( v_i \) and extend to a complete orthonormal basis using the Gram-Schmidt process.

### 2. **Matrix Reconstruction**

Using the computed \( U \), \( \Sigma \), and \( V^T \) to verify the accuracy of the decomposition:

\[
A = U \Sigma V^T
\]

### 3. **Solving for Coefficients**

To solve the system \( A \beta = b \):

- Compute the pseudoinverse of \( A \) as:

\[
A^+ = V \Sigma^{-1} U^T
\]

- Derive the solution \( \beta \) as:

\[
\beta = A^+ b
\]

### 4. **Validation with Scikit-Learn**

Using Scikit-Learn's `LinearRegression` with `fit_intercept=False`, compute the coefficients \( \beta \) and confirm they match the manually derived values.

