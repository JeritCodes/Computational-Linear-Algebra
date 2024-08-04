# 1 Python for Linear Algebra
## 1.1 Pseudocode: the new language for algorithm design
Pseudocode is a way to describe algorithms in a structured but plain language. It helps in planning the logic without worrying about the syntax of a specific programming language. we’ll use Python-flavored pseudocode to describe various matrix operations.
> There are varities of approaches in writing pseudocode. Students can adopt any of the standard approach to write pseudocode.
## 1.1.1 Matrix Sum
**Mathematical Procedure:**

To add two matrices $A$ and $B$, both matrices must have the same dimensions. The sum $C$ of two matrices $A$ and $B$ is calculated element-wise:

$$C[i][j] = A[i][j] + B[i][j]$$

**Example:**

Let $A$ and $B$ be two $2 \times 2$ matrices:

$$ A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}, \quad B = \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} $$

The sum $C$ is:


**Pseudocode:**

$$ C = A + B = \begin{bmatrix} 1+5 & 2+6 \\ 3+7 & 4+8 \end{bmatrix} = \begin{bmatrix} 6 & 8 \\ 10 & 12 \end{bmatrix} $$

```python
FUNCTION matrix_difference(A, B):
    # Determine the number of rows and columns in matrix A
    rows = number_of_rows(A)
    cols = number_of_columns(A)
    
    # Create an empty matrix C with the same dimensions as A and B
    C = create_matrix(rows, cols)
    
    # Iterate through each row
    FOR i FROM 0 TO rows-1:
        # Iterate through each column
        FOR j FROM 0 TO cols-1:
            # Calculate the difference for each element and store it in C
            C[i][j] = A[i][j] - B[i][j]
    
    # Return the result matrix C
    RETURN C
END FUNCTION
```
**Explanation:**
1. Determine the number of rows and columns in matrix $A$.
2. Create a new matrix $C$ with the same dimensions.
3. Loop through each element of the matrices and add corresponding elements.
4. Return the resulting matrix $C$.
## 1.1.2 Matrix Difference
**Mathematical Procedure:**

To subtract matrix $B$ from matrix $B$, both matrices must have the same dimensions. The difference $C$ of two matrices $A$ and $B$ is calculated element-wise:

$$C[i][j] = A[i][j] - B[i][j]$$

**Example:**

Let $A$ and $B$ be two $2 \times 2$ matrices:

$$A = \begin{bmatrix} 9 & 8 \\ 7 & 6 \end{bmatrix}, \quad B = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}$$

The difference $C$ is:

$$C = A - B = \begin{bmatrix} 9-1 & 8-2 \\ 7-3 & 6-4 \end{bmatrix} = \begin{bmatrix} 8 & 6 \\ 4 & 2 \end{bmatrix}$$

**Pseudocode:**

```
    FUNCTION matrix_difference(A, B):
    # Determine the number of rows and columns in matrix A
    rows = number_of_rows(A)
    cols = number_of_columns(A)
    
    # Create an empty matrix C with the same dimensions as A and B
    C = create_matrix(rows, cols)
    
    # Iterate through each row
    FOR i FROM 0 TO rows-1:
        # Iterate through each column
        FOR j FROM 0 TO cols-1:
            # Calculate the difference for each element and store it in C
            C[i][j] = A[i][j] - B[i][j]
    
    # Return the result matrix C
    RETURN C
END FUNCTION
```
**In more human readable format the above pseudocode can be written as:**

``` 
FUNCTION matrix_difference(A, B):
    Get the number of rows and columns in matrix A
    Create an empty matrix C with the same dimensions
    FOR each row i:
        FOR each column j:
            Set C[i][j] to the difference of A[i][j] and B[i][j]
    RETURN the matrix C
END FUNCTION
```
**Explanation:**

1. Determine the number of rows and columns in matrix $A$.
2. Create a new matrix $C$ with the same dimensions.
3. Loop through each element of the matrices and subtract corresponding elements.
4. Return the resulting matrix $C$.

## 1.1.3 Matrix Product
**Mathematical Procedure:**

To find the product of two matrices $A$ and $B$, the number of columns in $A$ must be equal to the number of rows in $B$ . The element $C[i][j]$ in the product matrix $C$ is computed as:

$$ C[i][j] = \sum_{k} A[i][k] \cdot B[k][j] $$

**Example:**

Let $A$ be a $2 \times 3$ matrix and $B$ be a $3 \times 2$ matrix:

$$ A = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{bmatrix}, \quad B = \begin{bmatrix} 7 & 8 \\ 9 & 10 \\ 11 & 12 \end{bmatrix} $$
**The product $C$ is:**
$$C = A \cdot B = \begin{bmatrix} 58 & 64 \\ 139 & 154 \end{bmatrix}$$
**Pseudocode:**
```
FUNCTION matrix_product(A, B):
    # Get the dimensions of A and B
    rows_A = number_of_rows(A)
    cols_A = number_of_columns(A)
    rows_B = number_of_rows(B)
    cols_B = number_of_columns(B)
    
    # Check if multiplication is possible
    IF cols_A != rows_B:
        RAISE Error("Incompatible matrix dimensions")
    
    # Initialize result matrix C
    C = create_matrix(rows_A, cols_B)
    
    # Calculate matrix product
    FOR each row i FROM 0 TO rows_A-1:
        FOR each column j FROM 0 TO cols_B-1:
            # Compute the sum for C[i][j]
            sum = 0
            FOR each k FROM 0 TO cols_A-1:
                sum = sum + A[i][k] * B[k][j]
            C[i][j] = sum
    
    RETURN C
END FUNCTION
```
A more human readable version of the `pseudocode` is shown below:
```
FUNCTION matrix_product(A, B):
    Get the number of rows and columns in matrix A
    Get the number of columns in matrix B
    Create an empty matrix C with dimensions rows_A x cols_B
    FOR each row i in A:
        FOR each column j in B:
            Initialize C[i][j] to 0
            FOR each element k in the common dimension:
                Add the product of A[i][k] and B[k][j] to C[i][j]
    RETURN the matrix C
END FUNCTION
```
**Explanation:**

1. Determine the number of rows and columns in matrices $A$ and $B$.
2. Create a new matrix $C$ with dimensions $\text{rows}(A)\times \text{columns}(B)$.
3. Loop through each element of the resulting matrix $C[i][j]$ and calculate the dot    product of $i$ the row of $A$ to the $j$ th column of $B$ for each element.
4. Return the resulting matrix $C$.
## 1.1.4 Determinant
**Mathematical Procedure:**

To find the determinant of a square matrix $A$, we can use the Laplace expansion, which involves breaking the matrix down into smaller submatrices. For a $2 \times 2$ matrix, the determinant is calculated as:
$$\text{det}(A) = A[0][0] \cdot A[1][1] - A[0][1] \cdot A[1][0]$$
For larger matrices, the determinant is calculated recursively.
**Example:**

Let $A$ be a $2 \times 2$ matrix:

$A = \begin{bmatrix} 4 & 3 \\ 6 & 3 \end{bmatrix}$

The determinant of $A$ is:

$$\text{det}(A) = (4 \cdot 3) - (3 \cdot 6) = 12 - 18 = -6$$
**Pseudocode:**
```
FUNCTION determinant(A):
    # Step 1: Get the size of the matrix
    n = number_of_rows(A)
    
    # Base case for a 2x2 matrix
    IF n == 2:
        RETURN A[0][0] * A[1][1] - A[0][1] * A[1][0]
    
    # Step 2: Initialize determinant to 0
    det = 0
    
    # Step 3: Loop through each column of the first row
    FOR each column j FROM 0 TO n-1:
        # Get the submatrix excluding the first row and current column
        submatrix = create_submatrix(A, 0, j)
        # Recursive call to determinant
        sub_det = determinant(submatrix)
        # Alternating sign and adding to the determinant
        det = det + ((-1) ^ j) * A[0][j] * sub_det
    
    RETURN det
END FUNCTION

FUNCTION create_sub_matrix(A, row, col):
    sub_matrix = create_matrix(number_of_rows(A)-1, number_of_columns(A)-1)
    sub_i = 0
    FOR i FROM 0 TO number_of_rows(A)-1:
        IF i == row:
            CONTINUE
        sub_j = 0
        FOR j FROM 0 TO number_of_columns(A)-1:
            IF j == col:
                CONTINUE
            sub_matrix[sub_i][sub_j] = A[i][j]
            sub_j = sub_j + 1
        sub_i = sub_i + 1
    RETURN sub_matrix
END FUNCTION
```
A human readable version of the same pseudocode is shown below:
```
FUNCTION determinant(A):
    IF the size of A is 2x2:
        RETURN the difference between the product of the diagonals
    END IF
    Initialize det to 0
    FOR each column c in the first row:
        Create a sub_matrix by removing the first row and column c
        Add to det: the product of (-1)^c, the element A[0][c], and the determinant of the sub_matrix
    RETURN det
END FUNCTION

FUNCTION create_sub_matrix(A, row, col):
    Create an empty sub_matrix with dimensions one less than A
    Set sub_i to 0
    FOR each row i in A:
        IF i is the row to be removed:
            CONTINUE to the next row
        Set sub_j to 0
        FOR each column j in A:
            IF j is the column to be removed:
                CONTINUE to the next column
            Copy the element A[i][j] to sub_matrix[sub_i][sub_j]
            Increment sub_j
        Increment sub_i
    RETURN sub_matrix
END FUNCTION
```
**Explanation:**

1. If the matrix is $2 \times 2$, calculate the determinant directly.
2. For larger matrices, use the Laplace expansion to recursively calculate the determinant.
3. Create submatrices by removing the current row and column.
4. Sum the determinants of the submatrices, adjusted for the sign and the current element.
## 1.1.5 Rank of a Matrix
**Mathematical Procedure:**

The rank of a matrix $$A is the maximum number of linearly independent rows or columns in $A$. This can be found using Gaussian elimination to transform the matrix into its row echelon form (REF) and then counting the number of non-zero rows.

**Example:**
Let $A$ be a $3 \times 3$ matrix:

$$A = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}$$
