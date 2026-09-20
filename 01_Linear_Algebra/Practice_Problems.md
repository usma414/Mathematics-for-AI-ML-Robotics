# Linear Algebra Practice

## MIT 18.06SC --- Practice Record

These are selected calculation and concept exercises completed while
studying MIT OpenCourseWare Linear Algebra.

------------------------------------------------------------------------

## Practice 1 --- Basis and Span

Given:

``` text
v₁ = [1 2 3]ᵀ
v₂ = [2 4 6]ᵀ
v₃ = [1 0 1]ᵀ
```

### Observation

``` text
v₂ = 2v₁
```

Therefore `v₂` is redundant.

The independent vectors are:

``` text
v₁ and v₃
```

So:

``` text
rank = 2
dimension of span = 2
```

They do not form a basis for `R³` because a basis for `R³` needs 3
independent vectors.

------------------------------------------------------------------------

## Practice 2 --- Rank, Nullity and Free Variables

A `4 × 6` matrix has:

``` text
rank(A) = 3
```

Using rank-nullity:

``` text
rank + nullity = number of columns

3 + nullity = 6

nullity = 3
```

Therefore:

``` text
dimension of column space = 3
dimension of null space = 3
number of free variables = 3
```

------------------------------------------------------------------------

## Practice 3 --- Matrix Calculation

Given:

``` text
A =
[1 2 3
 2 4 6
 1 1 1]
```

Because:

``` text
R₂ = 2R₁
```

there is redundancy.

The matrix has rank 2.

Since there are 3 columns:

``` text
nullity = 3 - 2 = 1
```

Therefore:

``` text
rank = 2
nullity = 1
```

The column space has dimension 2, not 3.

The three columns do not form a basis for `R³`.

------------------------------------------------------------------------

## Practice 4 --- Four Vectors in R⁴

Given:

``` text
v₁ = [1 2 1 3]ᵀ
v₂ = [2 4 2 6]ᵀ
v₃ = [1 0 2 1]ᵀ
v₄ = [2 2 3 4]ᵀ
```

Treating the vectors as rows:

``` text
[1 2 1 3
 2 4 2 6
 1 0 2 1
 2 2 3 4]
```

Elimination gives:

``` text
[1 2 1 3
 0 2 -1 2
 0 0 0 0
 0 0 0 0]
```

There are 2 pivots.

Therefore:

``` text
rank = 2
nullity = 4 - 2 = 2
```

The independent vectors are:

``` text
v₁ and v₃
```

A basis for their span is:

``` text
{v₁, v₃}
```

Dimension:

``` text
2
```

Additional dependency checks:

``` text
v₂ = 2v₁
v₄ = v₁ + v₃
```

------------------------------------------------------------------------

## Practice 5 --- Four Vectors in R⁴

Given:

``` text
v₁ = [1 2 0 1]ᵀ
v₂ = [2 4 1 3]ᵀ
v₃ = [1 1 1 2]ᵀ
v₄ = [3 5 1 4]ᵀ
```

Treating the vectors as rows:

``` text
A =
[1 2 0 1
 2 4 1 3
 1 1 1 2
 3 5 1 4]
```

Elimination gives:

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

The independent original vectors are:

``` text
v₁, v₂, v₃
```

A basis for their span is:

``` text
{v₁, v₂, v₃}
```

Dimension:

``` text
3
```

------------------------------------------------------------------------

## Practice 6 --- Null Space from an Elimination Form

Given:

``` text
A =
[1 2 0 1
 0 1 -1 -1
 0 0 1 1
 0 0 0 0]
```

The matrix has:

``` text
3 pivots
4 columns
```

Therefore:

``` text
number of free variables = 4 - 3 = 1
```

So:

``` text
nullity(A) = 1
```

The next step is to solve:

``` text
Ax = 0
```

and express the solution in parametric vector form.

This is the next null-space calculation to complete.

------------------------------------------------------------------------

# Quick Revision Questions

1.  What does a pivot tell you?
2.  What is the relationship between rank and column-space dimension?
3.  What is the relationship between nullity and free variables?
4.  How many vectors are required for a basis of `R⁴`?
5.  If a `5 × 8` matrix has rank 5, what is its nullity?
6.  If a matrix has 7 columns and 4 free variables, what is its rank?
7.  If `v₂ = 3v₁`, can both vectors belong to the same basis?
8.  What does the null space of `A` contain?
9.  What theorem connects rank and nullity?
10. Why can a set of 4 vectors in `R³` never be linearly independent?

------------------------------------------------------------------------

# Key Formulas

``` text
rank(A) = number of pivots

nullity(A) = number of free variables

rank(A) + nullity(A) = number of columns

dimension of column space = rank(A)

dimension of null space = nullity(A)
```
