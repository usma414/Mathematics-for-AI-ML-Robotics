# MIT Linear Algebra — Exam 1 Summary

## 1. Rank, Solutions and Free Variables

For an \(m \times n\) matrix:

$$
\boxed{\text{Rank}+\text{Nullity}=n}
$$

Where:

* **Rank** = number of pivots
* **Nullity** = number of free variables

### Exactly One Solution

For \(Ax=b\):

$$
\boxed{\text{rank}=n}
$$

There are no free variables.

### Infinitely Many Solutions

$$
\boxed{\text{Consistent + at least one free variable}}
$$

### No Solution

$$
\boxed{\text{Inconsistent system}}
$$

> **Important:** No solution does **not** mean that the columns are independent.

---

# 2. Homogeneous System \(Ax=0\)

The homogeneous system is:

$$
Ax=0
$$

It is **always consistent** because:

$$
A0=0
$$

### If rank = n

There are no free variables:

$$
\boxed{x=0 \text{ only}}
$$

### If rank < n

There are free variables:

$$
\boxed{\text{Infinitely many solutions}}
$$

including non-zero solutions.

---

# 3. Dimensions of a Matrix

For:

$$
A:m\times n
$$

we always have:

$$
\boxed{\text{rank}(A)\leq\min(m,n)}
$$

And:

$$
\boxed{\text{nullity}=n-\text{rank}}
$$

### Example

If:

$$
A=3\times5
$$

then:

$$
\text{rank}\leq3
$$

If rank = 3:

$$
\text{nullity}=5-3=2
$$

Therefore there are **2 free variables**.

---

# 4. Elementary Matrices and the Inverse

If row operations transform \(A\) into \(I\):

$$
E_k\cdots E_2E_1A=I
$$

then:

$$
\boxed{A^{-1}=E_k\cdots E_2E_1}
$$

Therefore:

$$
AA^{-1}=A^{-1}A=I
$$

### Important

The **order of elementary matrices matters**.

Matrix multiplication is generally not commutative:

$$
AB\neq BA
$$

So always keep track of the order in which row operations are performed.

---

# 5. LU Decomposition

The exam also connects elimination with:

$$
\boxed{A=LU}
$$

Where:

* \(L\) = lower triangular matrix
* \(U\) = upper triangular matrix

The elimination process produces \(U\).

The elimination multipliers are used to construct \(L\).

So remember:

$$
\boxed{\text{Elimination}\rightarrow U}
$$

and:

$$
\boxed{\text{Elimination multipliers}\rightarrow L}
$$

---

# 6. Column Space

The **column space** is the span of the columns of \(A\):

$$
\operatorname{Col}(A)
$$

### Key Rule

$$
\boxed{\text{Pivot columns of the ORIGINAL }A\text{ form a basis for Col}(A)}
$$

> **Important:** When finding a basis for the column space, use the pivot columns from the **original matrix**, not the columns of the RREF.

### Dimension

$$
\boxed{\dim(\operatorname{Col}(A))=\text{rank}(A)}
$$

---

# 7. Nullspace

The nullspace is the set of all solutions to:

$$
Ax=0
$$

### To Find the Nullspace

1. Row-reduce \(A\).
2. Identify the pivot variables.
3. Identify the free variables.
4. Give the free variables parameters.
5. Write the solution in vector form.
6. Extract the basis vectors.

### Number of Free Variables

For an \(m\times n\) matrix:

$$
\boxed{\text{free variables}=n-\text{rank}}
$$

Therefore:

$$
\boxed{\text{nullity}=n-\text{rank}}
$$

### Dimension

$$
\boxed{\dim(\operatorname{Null}(A))=\text{nullity}(A)}
\
$$
