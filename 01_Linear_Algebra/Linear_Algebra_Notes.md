# Linear Algebra Notes

## MIT 18.06SC --- Linear Algebra

These notes summarise the concepts studied from MIT OpenCourseWare and
the calculations practised independently.

------------------------------------------------------------------------

# 1. Matrices

A matrix is a rectangular arrangement of numbers.

For example:

``` text
A = [ 1  2
      3  4 ]
```

A matrix can represent data, a system of equations, or a linear
transformation.

------------------------------------------------------------------------

# 2. Matrix Multiplication

For compatible dimensions, matrix multiplication combines rows of one
matrix with columns of another.

The order matters:

``` text
AB ≠ BA
```

in general.

Matrix multiplication is fundamental to machine learning because
neural-network layers repeatedly use matrix-vector and matrix-matrix
multiplication.

------------------------------------------------------------------------

# 3. Identity Matrix

The identity matrix acts like `1` in ordinary multiplication.

``` text
AI = IA = A
```

For a 3 × 3 matrix:

``` text
I = [ 1 0 0
      0 1 0
      0 0 1 ]
```

------------------------------------------------------------------------

# 4. Inverse Matrix

If a square matrix `A` has an inverse:

``` text
AA⁻¹ = A⁻¹A = I
```

The inverse can be used to solve:

``` text
Ax = b
```

as:

``` text
x = A⁻¹b
```

when the inverse exists.

------------------------------------------------------------------------

# 5. Determinants

The determinant is a scalar associated with a square matrix.

For a 2 × 2 matrix:

``` text
A = [ a b
      c d ]

det(A) = ad - bc
```

A zero determinant indicates that the matrix is singular and its columns
are linearly dependent.

------------------------------------------------------------------------

# 6. LU Decomposition

A matrix can sometimes be written as:

``` text
A = LU
```

where:

-   `L` is lower triangular.
-   `U` is upper triangular.

LU decomposition turns solving a system into two triangular systems:

``` text
Ly = b
Ux = y
```

This is useful because triangular systems can be solved efficiently by
forward and back substitution.

------------------------------------------------------------------------

# 7. Homogeneous Systems: Ax = 0

A homogeneous system has the form:

``` text
Ax = 0
```

The zero vector is always a solution.

There may also be infinitely many non-zero solutions when the system has
free variables.

The complete set of solutions is the **null space** of `A`.

------------------------------------------------------------------------

# 8. Null Space

The null space is:

``` text
N(A) = {x : Ax = 0}
```

It tells us which input vectors are mapped to the zero output.

Example:

If solving `Ax = 0` gives

``` text
x = s[-2, 1, 0, 0] + t[-4, 0, 1, 1]
```

then the null space has a basis consisting of:

``` text
[-2, 1, 0, 0]

[-4, 0, 1, 1]
```

There are two free parameters (`s` and `t`), so:

``` text
nullity(A) = 2
```

The null space is useful for understanding redundancy and information
loss in a linear transformation.

------------------------------------------------------------------------

# 9. Span

The span of a set of vectors is every vector that can be produced using
linear combinations of those vectors.

For vectors `v₁, v₂`:

``` text
span{v₁, v₂}
=
{c₁v₁ + c₂v₂ : c₁,c₂ ∈ R}
```

If one vector can be produced from the others, it does not add a new
direction to the span.

------------------------------------------------------------------------

# 10. Linear Independence

Vectors are linearly independent when the only solution to:

``` text
c₁v₁ + c₂v₂ + ... + cₙvₙ = 0
```

is:

``` text
c₁ = c₂ = ... = cₙ = 0
```

If one vector can be written as a combination of the others, the set is
linearly dependent.

Example:

``` text
v₂ = 2v₁
```

means `v₂` is redundant and the two-vector set is dependent.

------------------------------------------------------------------------

# 11. Basis

A basis is a set of vectors that:

1.  spans the space, and
2.  is linearly independent.

A basis contains exactly the independent directions needed to describe
the space without redundancy.

For `R³`, a basis contains 3 linearly independent vectors.

For `R⁴`, a basis contains 4 linearly independent vectors.

------------------------------------------------------------------------

# 12. Dimension

The dimension of a vector space is the number of vectors in any basis of
that space.

Examples:

``` text
dim(R²) = 2
dim(R³) = 3
dim(R⁴) = 4
```

A subspace can have a smaller dimension than the surrounding space.

For example, two independent vectors in `R⁴` span a 2-dimensional
subspace of `R⁴`.

------------------------------------------------------------------------

# 13. Rank

The rank of a matrix is the dimension of its column space.

Equivalently, it is the number of pivot columns.

For example, if elimination gives:

``` text
[ 1 2 0
  0 1 3
  0 0 0 ]
```

there are two pivots, so:

``` text
rank(A) = 2
```

------------------------------------------------------------------------

# 14. Nullity

Nullity is the dimension of the null space.

For a matrix with `n` columns:

``` text
nullity(A) = n - rank(A)
```

It is also the number of free variables in `Ax = 0`.

------------------------------------------------------------------------

# 15. Rank--Nullity Theorem

The central relationship is:

``` text
rank(A) + nullity(A) = number of columns of A
```

Example:

If `A` has 6 columns and rank 3:

``` text
3 + nullity = 6

nullity = 3
```

Therefore:

-   3 pivot variables
-   3 free variables
-   column-space dimension = 3
-   null-space dimension = 3

------------------------------------------------------------------------

# 16. Basis from Elimination

When vectors are treated as rows, row reduction can identify which rows
are independent.

Example:

``` text
v₁ = [1 2 1 3]
v₂ = [2 4 2 6]
v₃ = [1 0 2 1]
v₄ = [2 2 3 4]
```

Since:

``` text
v₂ = 2v₁
v₄ = v₁ + v₃
```

only `v₁` and `v₃` are needed.

A basis for their span is therefore:

``` text
{v₁, v₃}
```

and the dimension is:

``` text
2
```

------------------------------------------------------------------------

# 17. Four-Vector Practice Result

For:

``` text
v₁ = [1 2 0 1]
v₂ = [2 4 1 3]
v₃ = [1 1 1 2]
v₄ = [3 5 1 4]
```

the row-reduction calculation gave:

``` text
[1 2 0 1
 0 1 -1 -1
 0 0 1 1
 0 0 0 0]
```

There are 3 pivots.

Therefore:

``` text
rank = 3
nullity = 4 - 3 = 1
```

The three independent original vectors are:

``` text
v₁, v₂, v₃
```

so a basis for their span is:

``` text
{v₁, v₂, v₃}
```

------------------------------------------------------------------------

# 18. Connection to AI, ML and Robotics

Linear algebra appears throughout AI and robotics.

### Machine Learning

Data is commonly represented as matrices:

``` text
X = data matrix
```

Model parameters can be vectors or matrices.

Matrix multiplication is used throughout neural networks.

### Computer Vision

An image can be represented as a matrix of pixel values. Transformations
such as rotation and scaling can be represented using matrices.

### Robotics

Robot positions, orientations, coordinate transformations and kinematics
use vectors and matrices.

### Information loss

If different input vectors produce the same output, a transformation may
have a non-trivial null space.

The null space therefore helps identify directions that a matrix
transformation ignores.

------------------------------------------------------------------------

# 19. Core Mental Model

A useful way to connect the ideas is:

``` text
Vectors
   ↓
Linear combinations
   ↓
Span
   ↓
Remove redundancy
   ↓
Linear independence
   ↓
Basis
   ↓
Dimension
```

For a matrix:

``` text
Columns
   ↓
Pivot columns
   ↓
Column space
   ↓
Rank

Ax = 0
   ↓
Free variables
   ↓
Null space
   ↓
Nullity
```

And both sides connect through:

``` text
rank + nullity = number of columns
```
