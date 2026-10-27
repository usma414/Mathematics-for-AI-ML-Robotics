# MIT Linear Algebra — Lecture 17: Orthogonal Matrices and Gram–Schmidt

## 1. Overview

This lecture covers orthogonal matrices, orthonormal vectors, the Gram–Schmidt process, and coordinate transformations.

These concepts are useful in linear algebra, machine learning, computer vision, robotics, and numerical computation.

## 2. Orthogonal Vectors

Two vectors \(u\) and \(v\) are orthogonal if their dot product is zero:

\[
u^T v = 0
\]

For example, let

\[
u=\begin{bmatrix}1\\1\end{bmatrix},
\qquad
v=\begin{bmatrix}1\\-1\end{bmatrix}
\]

Their dot product is

\[
u^Tv=(1)(1)+(1)(-1)=0
\]

Therefore, the vectors are orthogonal.

### Key distinction

- **Orthogonal:** Vectors are perpendicular; their dot product is zero.
- **Orthonormal:** Vectors are mutually perpendicular and each has length \(1\).

The length of a vector is calculated using

\[
\|v\|=\sqrt{v^Tv}
\]

To normalise a nonzero vector:

\[
\hat v=\frac{v}{\|v\|}
\]

## 3. Orthogonal Matrices

A square matrix \(Q\) is orthogonal if

\[
\boxed{Q^TQ=QQ^T=I}
\]

This means its columns form an orthonormal basis.

An important consequence is

\[
\boxed{Q^{-1}=Q^T}
\]

Therefore, the transpose of an orthogonal matrix is also its inverse.

### Example 1: A normalised orthogonal matrix

Consider

\[
Q=\frac{1}{\sqrt{2}}
\begin{bmatrix}
1&1\\
1&-1
\end{bmatrix}
\]

Since the matrix is symmetric,

\[
Q^T=Q
\]

Multiplying the transpose by the matrix gives

\[
Q^TQ=
\frac{1}{2}
\begin{bmatrix}
1&1\\
1&-1
\end{bmatrix}
\begin{bmatrix}
1&1\\
1&-1
\end{bmatrix}
\]

\[
Q^TQ=\frac{1}{2}
\begin{bmatrix}
2&0\\
0&2
\end{bmatrix}
=
\begin{bmatrix}
1&0\\
0&1
\end{bmatrix}=I
\]

Therefore, \(Q\) is an orthogonal matrix.

### Example 2: Rotation matrices

A two-dimensional rotation matrix is

\[
Q=
\begin{bmatrix}
\cos\theta&-\sin\theta\\
\sin\theta&\cos\theta
\end{bmatrix}
\]

Its transpose is

\[
Q^T=
\begin{bmatrix}
\cos\theta&\sin\theta\\
-\sin\theta&\cos\theta
\end{bmatrix}
\]

Using \(\cos^2\theta+\sin^2\theta=1\), we obtain

\[
Q^TQ=I
\]

Thus, rotation matrices are orthogonal.

**Geometric interpretation:** Orthogonal transformations preserve vector lengths and angles. Rotations also preserve orientation, while orthogonal reflections reverse orientation.

## 4. Gram–Schmidt Orthogonalisation

The Gram–Schmidt process converts a set of linearly independent vectors into an orthogonal set spanning the same subspace.

The resulting vectors can then be normalised to form an orthonormal set.

### Step 1: Choose the first vector

Given vectors \(v_1,v_2,\ldots,v_n\),

\[
u_1=v_1
\]

### Step 2: Remove the projection onto the first vector

For the second vector,

\[
u_2=v_2-\operatorname{proj}_{u_1}(v_2)
\]

where

\[
\boxed{
\operatorname{proj}_{u_1}(v_2)
=\frac{u_1^Tv_2}{u_1^Tu_1}u_1
}
\]

This removes the component of \(v_2\) parallel to \(u_1\), leaving a vector perpendicular to \(u_1\).

### Step 3: Continue for additional vectors

For