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

## Topic 3: Application: The LU Factorization

### Lesson 1: Solving Linear Systems with the LU Factorization

Recall $A\vec x = \vec b$
$\vec x = A^{-1}\vec b$

<u>problem</u>

1. compute inverse is difficult
2. using gaussian elimination is not efficient

<b>solution</b> : use <u>matrix factorization</u>

I. Matrix factorization / matrix decomposition

1. factor a matrix into a product of matrices.
2. factor into <b>lower</b> or <b>upper</b> triangle matrices.

II. Triangular matrix

1. Upper triangular
   Entries that below main diagonal are <b>zero</b>.
   $$
    \begin{pmatrix}1&5&0\\0&2&4\end{pmatrix},
    \begin{pmatrix}2&1\\0&1\\0&0\end{pmatrix}
   $$
2. Lower triangle
   $$
   \begin{pmatrix}1&0&0\\0&2&0\end{pmatrix},
   \begin{pmatrix}2&0\\0&1\\4&5\end{pmatrix}
   $$

<u>Theorem</u>
If $A$ is an $m\times n$ matrix that can be reduced to echelon form without row exchange, then $A = LU$.
$L$ is a <b>lower triangle</b> $m \times m$ matrix with <u>1's</u> on the diagonal, $U$ is an <u>echelon</u> form of A.

<u>Example</u>: If $A \in \R^{3\times 2}$, the $LU$ factorization has the form:

$$
A=LU=\begin{pmatrix}
1&0&0\\
*&1&0\\
*&*&1
\end{pmatrix}\begin{pmatrix}
*&*\\
0&*\\
0&0
\end{pmatrix}
$$

III. Using the $LU$ Decomposition to solve a Linear system

<b>Goal</b> : given <u>a triangular matrix</u> $A$ and vector $\vec b$ to solve $\vec x$ where $A\vec x = \vec b$.

<u>Algorithm</u>

1. Construct the $LU$ decomposition of $A$ to obtain $L$ and $U$.
2. Set $U\vec x = \vec y$. Forward solve for $\vec y$ in $L\vec y = \vec b$
3. Backward solve for $\vec x$

<u>Example</u> Given $LU$ decomposition, Solve the linear system $A\vec x = \vec b$.

$$
A = LU = \begin{pmatrix}
1&0&0&0\\
1&1&0&0\\
0&2&1&0\\
0&0&1&1
\end{pmatrix} \begin{pmatrix}
1&0&0\\
0&2&1\\
0&0&2\\
0&0&0
\end{pmatrix}, \vec b = \begin{pmatrix}
2\\
3\\
2\\
0
\end{pmatrix}
$$

1. Solve $L\vec y = \vec b$.
   $$
   \begin{pmatrix}
   1&0&0&0\\
   1&1&0&0\\
   0&2&1&0\\
   0&0&1&1
   \end{pmatrix} \begin{pmatrix}y_1\\y_2\\y_3\\y_4\end{pmatrix}=\begin{pmatrix}2\\3\\2\\0\end{pmatrix} \\
   \rArr y=\begin{pmatrix}2\\1\\0\\0\end{pmatrix}
   $$
2. Solve $U\vec x = \vec y$.
   $$
   \begin{pmatrix}
   1&0&0\\
   0&2&1\\
   0&0&2\\
   0&0&0
   \end{pmatrix}\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix}=\begin{pmatrix}2\\1\\0\\0\end{pmatrix} \\
   \rArr \vec x=\begin{pmatrix}2\\\frac{1}{2}\\0\\0\end{pmatrix}
   $$

### Lesson 2: Computing the LU Factorization

<u>Algorithm</u>

1. Reduce $A$ to an echelon form $U$ by a sequence of row replacement operations, if possible.
2. Place entries in $L$ such that the same sequence of row operations reduces $L$ to $I$

<u>Example</u>

Compute the $LU$ factorization of $A$.

$$
A=\begin{pmatrix}
4&-3&-1&5\\
-16&12&2&-17\\
8&-6&-12&22
\end{pmatrix}
$$

1. Find echelon form of $A (U)$
   1.1 $1^{st}$ row operation
   1.1.1 $R_2+4R_1$
   1.1.1 $R_3-2R_1$
   1.2 $2^{nd}$ row operation
   1.2.1 $R_3-5R_2$

   $$
   U=\begin{pmatrix}
   4&-3&-1&5\\
   0&0&-2&3\\
   0&0&0&-3
   \end{pmatrix}
   $$

1. Find $L$ :
   $$
   L=\begin{pmatrix}
   1&0&0\\
   \textcolor{red}{-4}&1&0\\
   \textcolor{red}{2}&\textcolor{red}{5}&1
   \end{pmatrix}
   $$

<b>Note</b> : $-4, 2, 5$ gets from $1.1.1, 1.1.2, 1.2.1$ respectively.

$\ast$ The only row operation we use to construct $L$ and $U$: <u>replace a row with a multiple of row above it</u>.

## Topic 4: Application: The Leontif Input Output Model

### Lesson 1: The Leontif Input-Output Model

I. Output vector

Suppose economy has $N$ sectors with output $\vec x \in \R^n$.

- $\vec x$ = output vector
- $x_i$ = number of units produced by sector $i$

II. Internal Consumption

The <u>consumption matrix, $C$</u> describes how units are consumed by sectors to produce output.

III. Defining entries of $C$
Sector $i$ sends a proportion of its units to sector $j$, called $c_{i, j}x_i$

Entries of $C, c_{ij} \in [0, 1]$ and:

1. $C\vec x$ = units consumed
2. $\vec x - C\vec x$ = units left after internal consumption

<u>Example</u>

An economy contains 3 sectors, $E, W, M$.

For every 100 units of output,

1. $E$ requires $20$ units from $E$, $10$ units from $W$ and $10$ units from $M$.
1. $W$ requires $0$ units from $E$, $20$ units from $W$ and $10$ units from $M$.
1. $M$ requires $0$ units from $E$, $0$ units from $W$ and $20$ units from $M$.

If the <u>output vector</u> is $\vec x=\begin{pmatrix}x_E\\ x_W\\ x_M\end{pmatrix}$, construct the consumption matrix for this economy.

<u>Defining unit consumed</u>

$$
C\vec x=
x_E\begin{pmatrix}0.2\\ 0.1\\ 0.1\end{pmatrix} +
x_W\begin{pmatrix}0\\ 0.2\\ 0.1\end{pmatrix} +
x_M\begin{pmatrix}0\\ 0\\ 0.2\end{pmatrix} \\
C\vec x= \begin{pmatrix}
0.2 & 0 & 0 \\
0.1 & 0.2 & 0 \\
0.1 & 0.1 & 0.2 \\
\end{pmatrix} \vec x
$$

<u>Solution</u> : creating $C$
Our consumption matrix is

$$
C = \frac{1}{10}\begin{pmatrix}
2 & 0 & 0 \\
1 & 2 & 0 \\
1 & 1 & 2 \\
\end{pmatrix}
$$

<u>Note</u>

1. Total output of each sector is the sum along the outgoing edges for each sector, which generate rows of $C$
2. elements of $C$ represent percentage with no units with value between $0$ and $1$.
3. output vector has units.

II. Demand

External demand given by $\vec d \in \R^N$ such that

$$
\vec x - C\vec x=\vec d
$$

can be re-write

$$
(I-C)\vec x = \vec d
$$

This equation called <b>Leontief Input-Output Model</b>.
Solving for $\vec x$ gives the output that meets external demand.

<u>Example</u>

Suppose there is an external demand: what production level is required to satisfy a final demand of $80$ units of $E$, $70$ units of $W$ and $160$ units of $M$?

<div>
<img src='/assets/img/edx-algebra-2/1.png' width='200'>
</div>

- $E$ requires 20% E, 10% W, 10% M
- $W$ requires 0% E, 20% W, 10% M
- $M$ requires 0% E, 0% W, 20% M

<u>Solution</u>

$$
(I-C)\vec x = \vec d \\
\left(\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}-
\begin{pmatrix}
0.2 & 0 & 0 \\
0.1 & 0.2 & 0 \\
0.1 & 0.1 & 0.2
\end{pmatrix}\right)\begin{pmatrix}
x_E\\
x_W\\
x_M\\
\end{pmatrix}=\begin{pmatrix}
80\\
70\\
160\\
\end{pmatrix}
$$

$$
\frac{1}{10}
\begin{pmatrix}
8 & 0 & 0 \\
-1 & 8 & 0 \\
-1 & -1 & 8
\end{pmatrix} \vec x = \begin{pmatrix}
80\\
70\\
160\\
\end{pmatrix}\\
x_E=100; x_W=100; x_M=225
$$

$\therefore$ The output that belance demand with internal consumption $\vec x=\begin{pmatrix}100 \\ 100 \\ 225\end{pmatrix}$

# Module 3: Computer Graphics and Subspaces

## Topic 1: Computer Graphics

### Lesson 1: Homogeneous coordinates

Translation of points in $\R^n$ does not correspond directly to a linear transform. <b>Homogeneous coordinates</b> are used to model translations using matrix multiplication.

Each point $(x, y) \in \R^2$ can be identified with point $(x, y, H), H\ne0$ , on the plane in $\R^3$ that lies $H$ units above the $xy$-plane.

Note : we often set $H=1$

<u>Example</u>

A translation of the form $(x, y) \to (x+h, y+k)$ can be presented as a matrix multiplication with homogeneous coordinates:

$$
\begin{pmatrix}
1&0&h\\
0&1&k\\
0&0&1
\end{pmatrix}\begin{pmatrix}x\\ y\\ 1\end{pmatrix}
=\begin{pmatrix}
x+h\\
y+k \\
1
\end{pmatrix}
$$

I. A Composite Transform with Homogeneous Coordinates

Triangle $S$ is determined by 3 data points $(1,1), (2, 4), (3, 1)$.
Transform $T$ rotates points by $\frac{\pi}{2}$ radians counterclockwise about the point $(0,1)$.

1. Represent the data with a matrix $D$. Use homogeneous coordinates.
2. Use matrix multiplication to determine the image of $S$ under $T$.
3. Sketch $S$ and its image under $T$.

<u>solution</u>

1. Use <u>homogeneous coordinates</u> to present data with matrix $D$

   $$
   D=\begin{pmatrix}
   1 & 2 & 3 \\
   1 & 4 & 1 \\
   \textcolor{red}{1} & \textcolor{red}{1} & \textcolor{red}{1}
   \end{pmatrix}
   $$

   <div>
   <img src='/assets/img/edx-algebra-2/2.png' width='200'>
   </div>

2. Use <u>matrix multiplication</u> to determine the image of $S$ under $T$

$$
\text{Shift 1 unit down}\\
\begin{pmatrix}
1 & 0 & \boxed{ 0} \\
0 & 1 & \boxed{-1} \\
0 & 0 & 1
\end{pmatrix} D_1 =\begin{pmatrix}
1 & 0 & \boxed{ 0} \\
0 & 1 & \boxed{-1} \\
0 & 0 & 1
\end{pmatrix}\begin{pmatrix}
1 & 2 & 3 \\
1 & 4 & 1 \\
\textcolor{red}{1} & \textcolor{red}{1} & \textcolor{red}{1}
\end{pmatrix}\\D_2=
\begin{pmatrix}
1 & 2 & 3 \\
0 & 3 & 0 \\
1 & 1 & 1
\end{pmatrix}
$$

<div>
<img src='/assets/img/edx-algebra-2/3.png' width='200'>
</div>

$$
D_3=\begin{pmatrix}
\boxed{0} & \boxed{-1} & 0 \\
\boxed{1} & \boxed{0} & 0 \\
0 & 0 & 1
\end{pmatrix}D_2=\begin{pmatrix}
0 & -3 & 0 \\
1 & 2 & 3 \\
1 & 1 & 1
\end{pmatrix}
$$

<div>
<img src='/assets/img/edx-algebra-2/4.png' width='200'>
</div>

$$
D_4=\begin{pmatrix}
1 & 0 & \boxed{0} \\
0 & 1 & \boxed{1} \\
0 & 0 & 1
\end{pmatrix}D_3=\begin{pmatrix}
0 & -3 & 0 \\
2 & 3 & 4 \\
1 & 1 & 1
\end{pmatrix}
$$

$\ast$ Note : $1^{st}$ matrix is transformer of $2^{nd}$ matrix!

This mean given $H=1$ just like a placeholder of transforming value by $1$.

<u>Example</u> : Given a matrix $A$, and we want to transform $A$

$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & -1 \\
0 & 0 & 1
\end{pmatrix} A
$$

1. $r_1 = 1\quad 0\quad 1$ : keep the value of first row.
2. $r_2 = 0\quad 1\quad -1$ : decrease 2nd row by 3rd row.
3. $r_3 = 0\quad 0\quad 1$ : keep value of 3rd row.
4. $r_1 = 0\quad -1\quad 0$ : 1st row uses negative value of 2nd row.
5. $r_2 = 1\quad 0\quad 0$ : 2nd row uses value from 1st row.

### Lesson 2: 3D Transformations

Homogeneous Coordinates ${(X, Y, Z, 1)}$ for $(x,y,z) \R^3$.

A translation $(x, y, z) \to (x+h, y+k, z+l)$ presents as matrix mulplication with homogeneous coordinates

$$
\begin{pmatrix}
1&0&0&h\\
0&1&0&k\\
0&0&1&l\\
0&0&0&1\\
\end{pmatrix}
\begin{pmatrix}x \\ y \\ z \\ 1\end{pmatrix} =
\begin{pmatrix}x+h\\ y+k \\ z+l \\ 1\end{pmatrix}
$$

I. <u>3D Transformation Matrices</u>

Construct matrices for the following transformations.

1. <u>A translation</u> in $\R^3$ specified by vector $\vec p=\begin{pmatrix}-2\\3\\4\end{pmatrix}$
2. <u></u>A rotation</u> in $\R^3$ about $x_2$-axis by $\pi$ radians
3. <u>A projection</u> onto plane $x_3=4$

<u>Solution</u>

1. A translation by $\vec p$

   $$
   \begin{pmatrix}
   1&0&0&\textcolor{red}{-2}\\
   0&1&0&\textcolor{red}{3}\\
   0&0&1&\textcolor{red}{4}\\
   0&0&0&1
   \end{pmatrix}
   $$

2. A rotation about $x_2$ by $\pi$
   $T = A\vec x, A(a_1\space a_2\space a_3)$
   $T(e_1)=Ae_1=a_1=\begin{pmatrix}-1\\0\\0\end{pmatrix}$
   $T(e_2)=Ae_1=a_2=\begin{pmatrix}0\\1\\0\end{pmatrix}$
   $T(e_3)=Ae_1=a_3=\begin{pmatrix}0\\0\\-1\end{pmatrix}$

   $$
   A=\begin{pmatrix}
   -1&0&0\\
   0&1&0\\
   0&0&-1\\
   \end{pmatrix}
   $$

3. A projection onto plane $x_3=4$

use homogeneous coordinates

$$
\begin{pmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&1&4\\
0&0&0&1
\end{pmatrix}
\begin{pmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&0&0\\
0&0&0&1
\end{pmatrix}
\begin{pmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&1&-4\\
0&0&0&1
\end{pmatrix}
$$

## Topic 2: Subspaces of $\R^n$

### Lesson 1: Subsets and Subspaces

A <b>subset of $\R^n$</b> is any collection of vectors that are in $\R^n$.

<u>Example</u>

- the span of the columns of a $3\times 4$ matrix is a subset of $\R^3$
- the set of all vectors of the form $\dbinom{1}{k}$ is a subset of $\R^2$

I. Subspace

A subset $H$ of $\R^n$ is a <b>subspace</b>. For any $c \in \R$ and $\vec u, \vec v \in H$

1. $c\vec u \in H$
2. $\vec u + \vec v \in H$

<u>Example</u>

1. the unit square

<div>
<img src='/assets/img/edx-algebra-2/5.png' width='200'>
</div>

- if $c=\begin{pmatrix}\frac{1}{2}\\ \frac{1}{2}\end{pmatrix}$, $c\vec u$ not in subset for all $c$.

2. a lign passing through the origin

<div>
<img src='/assets/img/edx-algebra-2/6.png' width='200'>
</div>

- $\vec u, \vec v$ are in subset, $c\vec u$ and $\vec u + \vec v$ are also in subset. therefore, it has a <b>subspace</b>.

3. a lign that does not pass through the origin

<div>
<img src='/assets/img/edx-algebra-2/7.png' width='200'>
</div>

- $c\vec u$ does not in subset, therefore : not a subspace.

II. Set builder notation

$$
V = \begin{Bmatrix}\dbinom{a}{b} \in \R^2 | ab = 0 \end{Bmatrix}
$$

1. Give an example of at least 2 vectors that are in $V$
2. Give an example of at least 2 vectors that are not in $V$
3. Is the zero vector in V?
4. is V a subspace?

<u>solution</u>

1. $\dbinom{1}{0}, \dbinom{0}{1}, \dbinom{0}{0}, ...$
2. $\dbinom{1}{1}, \dbinom{3}{1}, \begin{pmatrix}1\\2\\3\end{pmatrix}, ...$
3. yes
4. if $u=\dbinom{1}{0}, v=\dbinom{0}{1}$ in $V$
   but $u+v$ not in $V$, so not a subspace

### Lesson 2: Column Space and Null Space

For $\vec v_1, \cdots, \vec v_p \in \R^n$, $\bold{Span\{\vec v_1, \cdots, \vec v_p\}}$ is sets of all possible linear combinations of the vectors $\vec v_j$.

This is subspace spanned by $\vec v_1, \cdots, \vec v_p$

<u>Definition</u>

Given an $m \times n$ matrix $A=[\vec a_1, \cdots, \vec a_n]$

- <b>Column space</b> of $A$, <b>Col $A$</b>, is the subspace of $\R^m$ spanned by $\vec a_1, \cdots, \vec a_n$
- <b>Null space</b> of $A$, <b>Null $A$</b>, is the subspace of $\R^n$ spanned by the set of all vectors $\vec x$ that solve $A\vec x=\vec 0$.

<u>Example</u>: Column space

Is $\vec b$ in the column space of A?

$$
A=\begin{pmatrix}
1&-3&-4\\
-4&6&-2\\
-3&7&6
\end{pmatrix}, \vec b=\begin{pmatrix}3\\3\\-4\end{pmatrix}
$$

If $\vec b \in Col A$, then $\vec b \in Span\{ columns\ of\ A \}$

$$
\begin{pmatrix}
1&-3&-4&|&3\\
-4&6&-2&|&3\\
-3&7&6&|&-4
\end{pmatrix}
$$

- Implement row reduce

$$
\begin{pmatrix}
1&-3&-4&|&3\\
0&-6&-18&|&15\\
0&0&0&|&0
\end{pmatrix}
$$

- The system is <b>consistent</b>.

$\rArr \vec b \in Col\ A$

<u>Example</u>: Null space

Is $\vec v$ in the null space of $A$?

$$
A=\begin{pmatrix}
1&-3&-4\\
-4&6&-2\\
-3&7&6
\end{pmatrix}, \vec v=\begin{pmatrix}-5\lambda\\-3 \lambda\\ \lambda\end{pmatrix}, \lambda \in \R
$$

<u>Solution</u>

If $\vec v \in Null\ A$, then $A\vec v = \vec 0$.

$$
A\vec v = \begin{pmatrix}
1&-3&-4\\
-4&6&-2\\
-3&7&6
\end{pmatrix}\begin{pmatrix}-5\lambda\\-3 \lambda\\ \lambda\end{pmatrix}=\lambda\begin{pmatrix}0\\0\\ 0\end{pmatrix}
$$

$\rArr \vec v \in Null\ A$.

<b>Note</b>

1. if matrix A, has column space, then any column of A can be reduced and result in consistent.
2. To find nullspace $\vec x$ of A, it must be $A\vec x = 0$

### Lesson 3: Basis of a Subspace

A basis of a subspace $H$ is a set of linear independent vectors in $H$ that span $H$.

<u>Example</u>

The set $\vec x \in \R^4 | x_1-3x_2-5x_3+7x_4=0$ is a subspace.

1. $H$ is a null space for what matrix $A$?
2. Construct basis of $H$

<u>solution</u>

1. $x_1-3x_2-5x_3+7x_4=\begin{pmatrix}1&-1&-5&7\end{pmatrix}\begin{pmatrix}x_1\\x_2\\x_3\\x_4\end{pmatrix}=A\vec x=0$

2. to construct a basis for $H$, use parametric vector form:
   $$
   x_1-3x_2-5x_3+7x_4=0\\
   \vec x= \begin{pmatrix}x_1\\x_2\\x_3\\x_4\end{pmatrix}=\begin{pmatrix}
   3x_2+5x_3-7x_7\\
   x_2\\
   x_3\\
   x_4
   \end{pmatrix}\\=
   x_2\begin{pmatrix}3\\1\\0\\0\end{pmatrix}+
   x_3\begin{pmatrix}5\\0\\1\\0\end{pmatrix}+
   x_4\begin{pmatrix}-7\\0\\0\\1\end{pmatrix}
   $$

basis is the set

$$
\begin{Bmatrix}
\begin{pmatrix}3\\1\\0\\0\end{pmatrix},
\begin{pmatrix}5\\0\\1\\0\end{pmatrix},
\begin{pmatrix}-7\\0\\0\\1\end{pmatrix}
\end{Bmatrix}
$$

<u>Example</u> Construct a basis for Null A and a basis for Col A.

$$
A=\begin{pmatrix}
-3&6&-1&0\\
1&-2&2&0\\
2&-4&5&0\\
\end{pmatrix}\\
\thicksim \begin{pmatrix}
1&-2&0&0\\
0&0&1&0\\
0&0&0&0\\
\end{pmatrix}
$$

$\ast$ <u>Basis for Null A</u>

$A\vec x=\vec 0$ can be written as

$$
\begin{pmatrix}
1&-2&0&0\\
0&0&1&0\\
0&0&0&0\\
\end{pmatrix}\rArr \begin{cases}
   x_1 &\text{= } 2x_2\\
   x_3 &\text{= } 0\\
   x_2,x_4 &\text{= } free
\end{cases}
$$

parametric vector form:

$$
\vec x=\begin{pmatrix}x_1\\ x_2\\ x_3\\ x_4\end{pmatrix}
= x_2\begin{pmatrix}2\\ 1\\ 0\\ 0\end{pmatrix}+
x_4\begin{pmatrix}0\\ 0\\ 0\\ 1\end{pmatrix}
$$

$\therefore$ Basis for Null A

$$
\begin{Bmatrix}
\begin{pmatrix}2\\1\\0\\0\end{pmatrix},
\begin{pmatrix}0\\0\\0\\1\end{pmatrix}
\end{Bmatrix}
$$

$\ast$ <u>Basis for Column A</u>
Because row operation does not change the location of pivot columns $a_1, a_3$ in this case.

$\therefore$ Basis for Col A given by pivotal columns of $A$: $\begin{pmatrix}\begin{pmatrix}-3\\ 1\\ 2\end{pmatrix},\begin{pmatrix}-1\\ 2\\ 5\end{pmatrix}\end{pmatrix}$

[need review]

## Topic 3: Dimension and Rank

### Lesson 1: Coordinate Systems

I. Coordinate vector

Let $B=\{\vec b_1, \cdots, \vec b_p\}$ be a basis for subspace $H$. if $\vec x$ is in $H$, then coordinates of $\vec x$ relative $B$ are the weights(scalars) $c_1, \cdots, c_p$ so that

$$
\vec x=c_1\vec b_1+ \cdots + c_p\vec b_p
$$

And

$$
[x]_B=\begin{bmatrix}
c_1 \\
\vdots \\
c_p
\end{bmatrix}
$$

is the coordinates vector of $\vec x$ relative to $B$, or $B$-coordinate vector of $\vec x$.

<u>Example</u>

Let $\vec v_1=\begin{bmatrix}1\\ 0\\ 1\end{bmatrix}, \vec v_2=\begin{bmatrix}1\\ 1\\ 1\end{bmatrix}$ and $\vec x=\begin{bmatrix}5\\ 3\\ 5\end{bmatrix}$

1. verify that $\vec x$ is in the span of $B=\{v_1, v_2\}$
2. calculate $[x]_B$

<b>solution</b>

1. If $\vec x$ is in $Span\{\vec v_1, \vec v_2\}$, then $c_1\vec v_1 + c_2\vec v_2 = \vec x$

$$
\begin{pmatrix}
1&1&|&5\\
0&1&|&3\\
1&1&|&5
\end{pmatrix}\\
\thicksim
\begin{pmatrix}
1&0&|&2\\
0&1&|&3\\
0&0&|&0
\end{pmatrix}
$$

The system is <b>consistent</b>, means $\vec x$ is in the span of $\vec v_1$ and $\vec v_2$.

2. $[x]_B=\begin{bmatrix}2\\ 3\end{bmatrix}$

### Lesson 2: The Dimension of a Subspace

<u>Definition</u>

The Dimension of non-zero subspace $H$, $\bold{dim\ H}$, is the number of vectors in a basis of $H$. $dim\{\vec 0\}=0$

1. zero vector cannot be a basis vector.
2. the dimension of the set that only contains the zero vector is <u>zero</u>

<u>Example</u>
The dimension of the column space for each matrix is 2

$$
A=\begin{pmatrix}
1&0&0\\
0&0&1
\end{pmatrix}, B=\begin{pmatrix}
1&0\\
0&1\\
0&0
\end{pmatrix}, C=\begin{pmatrix}
1&0&1\\
0&1&1\\
0&0&0
\end{pmatrix}
$$

1. $dim\ \R^n = n$

### Lesson 3: Rank and Invertibility

Rank of a matrix is the dimension of its column space.

<u>Example</u>
Compute Rank(A) and dim(Nul(A))

$$
A=\begin{pmatrix}
2&5&-3&-4&8\\
4&7&-4&-3&9\\
6&9&-5&2&4\\
0&-9&6&5&-6\\
\end{pmatrix} \thicksim \begin{pmatrix}
2&5&-3&-4&8\\
0&-3&2&5&-7\\
0&0&0&4&-6\\
0&0&0&0&0\\
\end{pmatrix}
$$

$1st, 2nd, 4th$ columns are pivotal.
$\rArr Rank(A) = 3$.

<u>Rank theorem</u>
If a matrix $A$ has $n$ columns, then $Rank(A)+dim(Nul(A))=n$

<u>Example</u> : construction

Give an example of $2 \times 3$ matrix A, in RREF that

1. rank(A)=3 : not possible cos at most have 2 pivots
2. rank(A)=2 : any matrices with 2 pivot
3. dim(NullA)=2 : need 2 non-pivots and 1 pivot
4. NullA={$\vec 0$} not possible cos [need-review]

<b>Invertibility</b>

Let $A$ be an $n \times n$ matrix. These conditions are equivalent.

1. A is invertible
2. Columns of A are a basis for $\R^n$
3. ColA = $\R^n$
4. rank A = $dim(ColA)=n$
5. NulA = {$\vec 0$}

{% endkatexmm %}
