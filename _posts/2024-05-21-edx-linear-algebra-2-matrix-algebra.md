---
layout: post
title: Linear Algrebra 2 - Matrix Algebra
date: 2024-05-21 23:10:15
description: Linear algebra 2
tags: math linear
categories: research
tabs: true
---

# Module 1: Matrices and The Matrix Inverse

## Topic 1: Matrix Operations

### Lesson 1: Matrix Addition and Scalar Multiplication

{% katexmm %}

<b>Zero</b> matrix : all entries are <b>0</b>.

$$
0_{2\times 3}=\begin{pmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
\end{pmatrix}
$$

<b>Identity</b> matrix : square matrix that <b>1</b> on the main diagonal, other entries are <b>0</b>.

$$
I_{3}=\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
$$

Suppose $A$ and $B$ are $m \times n$ matrices.

- $A + B = (a_{i,j} + b_{i,j})$
- $cA = (ca_{i,j}) \enspace ; c \in \R$

I. <u>Properties of matrix addition and scalar multiplication</u>

1. $A + 0 = A$
2. $(A + B) + C = A + (B + C)$
3. $r(A + B) = rA + rB$
4. $(r + s)A = rA + sA$
5. $r(sA) = (rs)A$

$r, s \in \R$ : scalars
$A, B, C$ : $m \times n$ matrices
$0$ : $m \times n$ <b>zero</b>-matrix

### Lesson 2: Matrix Multiplication

Let $A \in \R^{m \times n}$ has rows $\vec a_i$ and $B \in \R^{n \times p}$ has columns $\vec b_j$.

I. <b>Matrix product</b> method : Manipulate <u>column</u> by <u>column</u>

$$
AB
= A(\vec b_1 \space\cdots\space \vec b_p)
= (A\vec b_1 \space...\space A\vec b_p)
$$

II. <b>Row column</b> method : manipulate <u>entry</u> by <u>entry</u>

$$
AB = \vec a_i \cdot \vec b_j
$$

III. <b>Properties</b>

1. Associative : $(AB)C = A(BC)$
2. Distributive : $A(B + C) = AB + AC$
3. Identity : $I_mA = AI_n = A$

$\color{red} \ast \space \text{Warning}$

1. Not commutative : $AB \ne BA$
2. Not cancellation : $AB = AC$ does not mean $B=C$.
3. Zero divisor : $AB = 0$ does not mean either $A=0$ or $B=0$.

### Lesson 3: Matrix Transpose and Powers

$A^T$ swaps between <u>rows</u> and <u>columns</u>.

$$
\begin{pmatrix}
1 & 2 & 3 \\
0 & 1 & 5
\end{pmatrix}^T = \begin{pmatrix}
1 & 0 \\
2 & 1 \\
3 & 5
\end{pmatrix}
$$

I. <u>Property</u>

1. $(A^T)^T = A$
2. $(A + B)^T = A^T + B^T$
3. $(rA)^T = rA^T, r \in \R$
4. $(AB)^T = B^TA^T$

II. <u>Matrix Powers</u>

$$
A^k = \overbrace{AA\cdots A}^{k}
$$

$A$ : $n \times n$ square matrix
$k$ : positive integer

## Topic 2: Inverse of a Matrix

### Lesson 1: The Inverse of a 2x2 matrix

Suppose $A \in \R^{n \times n}$ is <b>invertible ($A^{-1}$).</b>

<b>_ Non singular = invertible!</b>
<u>_ Non square matrix do not have an <b>inverse</b>.</u>

$$
AA^{-1}=A^{-1}A=I_n
$$

I. Inverse of $2 \times 2$ matrix

$$
\begin{pmatrix}
a & b \\
c & d \\
\end{pmatrix}^{-1} =
\frac{1}{ad - bc}\begin{pmatrix}
d & -b \\
-c & a \\
\end{pmatrix}, ad - bc \ne 0
$$

II. Using inverse matrix to solve linear system

$$
3x_1 + 4x_2=7 \\
5x_1 + 6x_2 = 7
$$

1. matrix form

   $$
   A\vec x = \vec b \\
   A=\begin{pmatrix}
   3 & 4 \\
   5 & 6
   \end{pmatrix};
   \vec b = \dbinom{7}{7}
   $$

2. matrix inverse

   $$
   ad - bc = 18-20=-2 \ne 0 \\
   A^{-1}=\frac{1}{-2}\begin{pmatrix}
   6 & -4 \\
   -5 & 3
   \end{pmatrix}
   $$

3. Solve
   $$
   A'A\vec x = A'\vec b \\
   I\vec x = A'\vec b \\
   \vec x = A'\vec b \\
   \vec x = -\frac{1}{2}\begin{pmatrix}
   6 & -4 \\
   -5 & 3
   \end{pmatrix}\begin{pmatrix}
   7 \\
   7
   \end{pmatrix}=\begin{pmatrix}
   -7 \\
   7
   \end{pmatrix}
   $$

### Lesson 2: The Inverse of an $n \times n$ Matrix

$A \in \R^{n \times n}$ has an <b>inverse</b>:

- $A\vec x = \vec b$ has a unique solution
- $\vec x = A^{-1}\vec b$

I. Algorithm

1. RREF $(A|I_n)$
2. If has $(I_n|B)$, then $A$ is <b>invertible</b> and $\bold{A^{-1} = B}$, otherwise, $A$ is <u>NOT invertible.</u>

Example: compute inverse of
$
A=\begin{pmatrix}
0 & 1 & 2 \\
1 & 0 & 3 \\
0 & 0 & 1 \\
\end{pmatrix}
$

1. find $(A|I_n)$

   $$
   \begin{pmatrix}
   0 & 1 & 2 & | & 1 & 0 & 0\\
   1 & 0 & 3 & | & 0 & 1 & 0 \\
   0 & 0 & 1 & | & 0 & 0 & 1 \\
   \end{pmatrix}
   $$

2. RREF
   $$
   \begin{pmatrix}
   1 & 0 & 0 & | & 0 & 1 & -3\\
   0 & 1 & 0 & | & 1 & 0 & -2 \\
   0 & 0 & 1 & | & 0 & 0 & 1 \\
   \end{pmatrix}
   $$

$\therefore$ Therefore

$$
B = A^{-1} = \begin{pmatrix}
0 & 1 & -3\\
1 & 0 & -2 \\
0 & 0 & 1 \\
\end{pmatrix}
$$

$A^{-1}\vec e_i=\vec x_i \to A\vec x_i=\vec e_i$.
which mean, if we multiply matrix $A$ with column $\vec x_i$ of inverse matrix $A^{-1}$, then we will get standard vector $\vec e_i$.

$\bold{I_n = (\vec e_1 \vec e_2 \cdots \vec e_n)}$

### Lesson 3: Elementary Matrices

I. <u>Properties of matrix inverse</u>

1. $(A^{-1})^{-1}=A$
2. $(AB)^{-1}=B^{-1}A^{-1}$
3. $(A^T)^{-1}=(A^{-1})^T$

II. Elementary matrices $E$

An elementary matrix $E$, is one that differ by $I_n$ by <u>one row operation</u>.

<u>Note</u>:

1. <b>invertible</b>
2. <b>square</b>

<u>Example</u>:

$$
E\begin{pmatrix}
1 & 1 & 1 \\
-2 & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}=\begin{pmatrix}
1 & 1 & 1 \\
0 & 3 & 2 \\
0 & 0 & 1 \\
\end{pmatrix}
$$

What is the value of $E$?

- To be defined, $E$ must be $3 \times 3$
- must be differ by only 1 row operation from $I$

1. keep $1^{st}$ and $3^{rd}$ the same

$$
E=\begin{pmatrix}
1 & 1 & 1 \\
e & e & e \\
0 & 0 & 1 \\
\end{pmatrix}
$$

2. $2R_1 + R_2\to R_2$ differ from $I$ and replace in $R_2$
   $$
   I=\begin{pmatrix}
   \textcolor{blue}{1} & \textcolor{blue}{0} & \textcolor{blue}{0} \\
   \textcolor{blue}{0} & \textcolor{blue}{1} & \textcolor{blue}{0} \\
   0 & 0 & 1 \\
   \end{pmatrix}\\
   \textcolor{blue}{I(2R_1+R_2)} \rArr \textcolor{red}{E(R_2)}\\
   E=\begin{pmatrix}
   1 & 1 & 1 \\
   \textcolor{red}{2} & \textcolor{red}{1} & \textcolor{red}{0} \\
   0 & 0 & 1 \\
   \end{pmatrix}
   $$

Note:
Differ from $I_3$ by one row operation $2R_1 + R_2$

<b>Matrix inverse</b> is a product of elementary matrices.
$(E_k\cdots E1)A=I$

1. Using $A^{-1}$ to compute linear system
   $$
   A\vec x = \vec b \quad(1)\\
   \vec x = A^{-1}\vec b \quad(2)
   $$

Why do we need elementary matrices?

# Module 2: The Invertible Matrix Theorem and Applications

## Topic 1: Invertible Matrices

### Lesson 1: The Invertible Matrix Theorem

Let $A$ is $n \times n$ matrix.

1. $A$ is <u>invertible</u> : can reduce to $I_n$
2. row equivalent to $I_n$
3. all columns are pivotal
4. $A\vec x = \vec 0$ has only trivial solution
5. columns are linear <b>independent</b>
6. $A\vec x = \vec b$ has a solution for all $\vec b \in \R^n$
7. columns of A span $\R^n$
8. left inverse $A^{-1}A=I_n$
9. right inverse $AA^{-1}=I_n$
10. $A^T$ is invertible

<u>Example</u> Identify if a matrix is inverse.

$$
\begin{pmatrix}
1 & 0 & -2 \\
3 & 1 & -2 \\
0 & -1 & -1
\end{pmatrix}
$$

1. reduce row and check if all columns are <b>pivotal</b>

## Topic 2: Application: Partitioned Matrices

### Lesson 1: Partitioned Matrices and Matrix Multiplication

I. Partitioned matrix

$$
A=\begin{pmatrix}
3&1&4&1&0 \\
1&6&1&0&1 \\
0&0&0&4&2 \\
\end{pmatrix}
\\
A=\begin{pmatrix}
\begin{pmatrix}3&1&4\\1&6&1\end{pmatrix}
\begin{pmatrix}1&0\\0&1\end{pmatrix}
\\
\begin{pmatrix}0&0&0\end{pmatrix}
\begin{pmatrix}4&2\end{pmatrix}
\end{pmatrix}
=\begin{pmatrix}
A_{1,1} & A_{1,2} \\
A_{2,1} & A_{2,2}
\end{pmatrix}
$$

$\ast$ Partitioned matrix gives succint representation.
Useful when study <b>null space</b> of $A$.

$$
\begin{pmatrix}
1 & 0 & 0 & * & \cdots & * \\
0 & 1 & 0 & * & \cdots & * \\
0 & 0 & 1 & * & \cdots & * \\
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 0 & 0 & \cdots & 0 \\
\end{pmatrix} =
\begin{pmatrix}
I_3 & F \\
0 & 0
\end{pmatrix}
$$

Example:

$$
AB = \begin{pmatrix}
1&0&1\\
0&1&1
\end{pmatrix} \begin{pmatrix}
2&-1 \\
0&-1 \\
0&1
\end{pmatrix} = \begin{pmatrix}
I_3 & X
\end{pmatrix} \begin{pmatrix} U \\ Y \end{pmatrix} \\
$$

$$
I=\begin{pmatrix}1&0\\0&1\end{pmatrix}
X=\begin{pmatrix}1\\1\end{pmatrix}
U=\begin{pmatrix}2&-1\\0&-1\end{pmatrix}
Y=\begin{pmatrix}0&1\end{pmatrix} \\
$$

$\ast$ Solved by using <u>row column method</u>.
$\rArr \bold{I_3U + XY}$

### Lesson 2: Partitioned Matrices and the Matrix Inverse

I. Compute inverse of $\begin{pmatrix}A & B\\0 & C\end{pmatrix}$

$$
\begin{pmatrix}A & B\\0 & C\end{pmatrix}
\textcolor{red}{\begin{pmatrix}W & X\\Y & Z\end{pmatrix}} =
I=\begin{pmatrix}I_n & 0\\0 & I_n\end{pmatrix}
$$

1. $0W+CY=0$
   $CY=0 \\
\to C^{-1}CY=C^{-1}0 \\
\to \boxed{Y=0}$

2. $0X+CZ=I$
   $CZ=I \\
\to C^{-1}CZ=C^{-1}I \\
\to \boxed{Z=C^{-1}}$

3. $AW+BY=I$
   $AW=I \\
\to A^{-1}AW=A^{-1}I \\
\to \boxed{W=A^{-1}}$

4. $AX+BZ=0$
   $AX=-BZ \\
\to A^{-1}AX=-A^{-1}BC^{-1} \\
\to \boxed{X=A^{-1}BC^{-1}}$

$$
\begin{pmatrix}A & B\\0 & C\end{pmatrix}^{-1}=
\textcolor{red}{\begin{pmatrix}
A{-1} & A^{-1}BC^{-1} \\
0 & C^{-1}
\end{pmatrix}}
$$

Topic 3: Application: The LU Factorization
Lesson 1: Solving Linear Systems with the LU Factorization
Lesson 2: Computing the LU Factorization
Topic 4: Application: The Leontif InputOutput Model
Lesson 1: The Leontif Input-Output Model
Module 3: Computer Graphics and Subspaces
Topic 1: Computer Graphics
Lesson 1: Homogeneous coordinates
Lesson 2: 3D Transformations
Topic 2: Subspaces of Rn
Lesson 1: Subsets and Subspaces
Lesson 2: Column Space and Null Space
Lesson 3: Basis of a Subspace
Topic 3: Dimension and Rank
Lesson 1: Coordinate Systems
Lesson 2: The Dimension of a Susbpsace
Lesson 3: Rank and Invertibility

{% endkatexmm %}
