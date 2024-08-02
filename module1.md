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

**Pseudocode:**


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
