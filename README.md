# Sparse Matrix Multiply (CSR Conversion)

This project implements a sparse matrix multiplication routine in C that:

1. Converts a dense matrix into CSR (Compressed Sparse Row) format
2. Computes the matrix-vector multiplication:

```text
y = A * x
```

---

# Sparse Multiply

```c
void sparse_multiply(
    int rows,
    int cols,
    const double* A,
    const double* x,
    int* out_nnz,
    double* values,
    int* col_indices,
    int* row_ptrs,
    double* y
);
```

## Parameters

| Parameter | Description |
|---|---|
| `rows` | Number of rows in matrix `A` |
| `cols` | Number of columns in matrix `A` |
| `A` | Dense row-major matrix |
| `x` | Input vector |
| `out_nnz` | Output total non-zero count |
| `values` | CSR non-zero values |
| `col_indices` | CSR column indices |
| `row_ptrs` | CSR row offsets |
| `y` | Output vector result |

---

# CSR Format

The sparse matrix is stored using CSR (Compressed Sparse Row) format.

## Example

Dense matrix:

```text
1 0 0 2
0 3 0 0
4 0 5 0
```

CSR representation:

```text
values      = [1, 2, 3, 4, 5]
col_indices = [0, 3, 1, 0, 2]
row_ptrs    = [0, 2, 3, 5]
```

---

# Build Instructions

## GCC

Compile with:

```bash
gcc -lm -o run challenge.c
```

Run:

```bash
./run
```
