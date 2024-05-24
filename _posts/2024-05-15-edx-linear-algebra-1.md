---
layout: post
title: Linear Algrebra 1
date: 2024-05-15 00:32:13
description: Linear algebra 1, taught in the school of Mathematics at the Georgia Institute of Technology
tags: math linear
categories: research
tabs: true
---

# Module 1: Linear Systems and Span

## Topic 1: Systems of Linear Equations

### Lesson 1: Solutions Sets of Linear Equations

Form of linear equation
a_1x_1 + a_2x_2 + ... + a_nx_n = b

a_1, a_2, ..., a_n = coefficients
b = constant
x_1, x_2, ..., x_n = variables / unknowns

A system of linear equations are set of linear equations.
Solutions sets are set of solutions that solve all linear equations.

There are **3** possible cases:

1. non-parallel lines (1 solution)
2. identical lines (infinitely many solutions)
3. parallel lines (no solution)

Using **row operations** to find the solution

### Lesson 2: Consistent Systems

- augmented matrices : avoid to write variables ( in the matrix form ).
- existence and uniqueness
- consistent : has at least 1 solution.
- row equivalence : if row operations transforms one matrix into the other. also have the same solution set.

## Topic 2: Row Reduction and Echelon Forms

### Lesson 1: Echelon Form and RREF

**row reduced echelon form** : has 1 on the diagonal everything else are zero.

A rectangular matrix is is **echelon form** if:

1. all zero rows (if any) are at the bottom
2. the 1st non-zero entry of a row is to the right of any leading entries in the row above it
3. below leading entry are zero

<div>
  <img src='/assets/img/edx-algebra-1/1.png' width='250'>
</div>

matrix A is **echelon form**.

- all zero entry is at the bottom
- leading entry of row 1 = 2
- leading of row 2 = 5 ( to the right of row 1 )
- below leading entry are zero
  matrix B is not **echelon form**.

A matrix in echelon form is in **row reduced echelon form** if

- leading entries (if any) are 1.
- 1s are the only non-zero entry in their column

<div>
  <img src='/assets/img/edx-algebra-1/2.png' width='250'>
</div>

Matrix A is in RREF.
Matrix B is in echlon form but is not in RREF (not match 2nd condition of RREF criteria).

### Lesson 2: The Row Reduction Algorithm

Tell what row operations used to solve linear system.

- row reduction algorithm :
- pivots and pivot columns :

**pivot position** in a matrix A is the location in A that corresponds to a leading 1 in the RREF of A.
**pivot column** is a column of A that contains a pivot position.

**Row Reduction Algorithm** is used to produced a matrix in RREF by :

1. swapping
2. scaling
3. replacing

### Lesson 3: Existence and Uniqueness

<div>
  <img src='/assets/img/edx-algebra-1/3.png' width='250'>
</div>

- **pivot columns** of A are 1st, 3rd, 5th columns
- Variables (x1, x3, x5) of pivot columns called **basic variables**
- Variables (x2, x4) that are not basic are **free variables**, they can take any values.

if A has n columns, must have n variables (each column, each variable)

1. A linear system is consistent if RREF, DOES NOT have a row of
   (0 0 0 ... 0 | 1)
2. if consistent

- unique solution : no free variables
- infinitely many solutions : parameterized by free variables

## Topic 3: Vector Equations

### Lesson 1: Vectors in $\R^n$

If we think of `R^n` as vector, write as a matrix of n-rows with 1 column.

let's consider `n` as dimension. if n=2, means 2 dimension then it has 2 entries.

### Lesson 2: Linear Combinations

<div>
  <img src='/assets/img/edx-algebra-1/4.png' width='250'>
</div>

each vector has `n` entries
c1, c2, ... called `weight`.

- basically, find weights (c1, c2, ...) to make linear combination works ( equal )

$$
c1v1 + c2v2 + ... = y
$$

### Lesson 3: Span

<div>
  <img src='/assets/img/edx-algebra-1/5.png' width='250'>
</div>

span is related to linear combination. it is set of vectors of linear combination.

# Module 2: Solution Sets and Linear Independence

## Topic 1: The Matrix Equation

### Lesson 1: The Matrix Vector Product

<div>
  <img src='/assets/img/edx-algebra-1/6.png' width='250'>
</div>

Given mxn matrix A, a column vector x
the product of A and x can be written as linear combination.

Columns of A are spans of A, entries of x are `constant` or `weight`.

<div>
  <img src='/assets/img/edx-algebra-1/7.png' width='250'>
</div>
<div>
  <img src='/assets/img/edx-algebra-1/8.png' width='250'>
</div>

### Lesson 2: Existence of Solutions

3 ways to express linear equations

If $\bold{A}$ is $\bold{m \times n}$ matrix with columns $\bold{\vec a_1,...,\vec a_n}$ and $\bold{\vec x \in \R^n}$ and $\bold{\vec b \in \R^m}$ then:

<u>Vector product</u>

$$
A\vec x= \vec b
$$

<u>Vector equation</u>

$$
x_1\vec a_1+...+x_n\vec a_n = \vec b
$$

<u>Augmented matrix</u>

$$
\begin{bmatrix}
\vec a_1 & \vec a_2 & ... & \vec a_n & \vec b
\end{bmatrix}
$$

\*\* Theorem
$\bold{A\vec x=\vec b}$ has solution if/only if $\bold{\vec b}$ is a linear combination of columns of $\bold{A}$.

## Topic 2: Solution Sets of Linear Systems

### Lesson 1: Homogeneous systems

<u>Definition</u>
Linear systems of the form $\bold{A\vec x=\vec 0}$ are <b>Homogeneous</b>.

<u>Homogeneous</u> always have <b>trivial solution</b>, $\bold{\vec x=\vec 0}$.

If, $A\vec x=\vec 0$ has <b>non-trivial solution</b>

1. There is a free variable
2. $A$ has a column with no pivot

<u>Example</u>: A homogeneous system have non-trivial solution because it has free variable.

$$
\begin{align}
x_1+3x_2+x_3=0 \\
2x_1-x_2-5x_3=0 \\
x_1-2x_3=0
\end{align}
$$

1. Augmented matrix

$$
\begin{pmatrix}
1 & 3 & 1 & 0 \\
2 & -1 & -5 & 0 \\
1 & 0 & -2 & 0 \\
\end{pmatrix}
$$

2. RREF

$$
\begin{pmatrix}
\boxed{1} & 0 & -2 & 0 \\
0 & \boxed{1} & 1 & 0 \\
0 & 0 & 0 & 0 \\
\end{pmatrix}
$$

<u>Note</u>: $\vec a_1$ and $\vec a_2$ are <b>Pivot</b>. but, $\vec a_3$ is not. This mean $\bold{x_3}$ is <b>free</b>.

$x_1-2x_3=0  \to x_1 = 2x_3$
$x_2-x_3=0 \to x_2 = -x_3$

$\therefore$ <u>Solution set</u>

$$
\vec x
= \begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}
= \begin{pmatrix}
2x_3 \\
-x_3 \\
x_3
\end{pmatrix}
= x_3\begin{pmatrix}
2 \\
-1 \\
1
\end{pmatrix}
$$

### Lesson 2: Parametric vector forms

<u>Solution to non-homogeneous system</u>

1. Augmented matrix

   $$
   \begin{pmatrix}
   1 & 3 & 1 & 4 \\
   2 & -1 & -5 & 1 \\
   1 & 0 & -2 & 1 \\
   \end{pmatrix}
   $$

2. RREF
   $$
   \begin{pmatrix}
   1 & 0 & -2 & 1 \\
   0 & 1 & 1 & 1 \\
   0 & 0 & 0 & 0 \\
   \end{pmatrix}
   $$

$\therefore$ <u>Solution set</u>

$$
\vec x
= \begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}
= \begin{pmatrix}
1+2x_3 \\
1+-x_3 \\
x_3
\end{pmatrix}
= \begin{pmatrix}
1 \\
1 \\
0
\end{pmatrix} + x_3
\begin{pmatrix}
2 \\
-1 \\
1
\end{pmatrix}
$$

<u>Note:</u> for <b>Homogeneous</b> case:

Suppose $A\vec x=\vec 0$ has free variables $x_k, ..., x_n$.
Then solutions can be written as <b>Parametric form</b>:

$$
\vec x=x_k\vec v_k + x_{k+1}\vec v_{k+1}+...+x_n\vec v_n
$$

## Topic 3: Linear Independence

### Lesson 1: A Definition of Linear Independence

A set of vectors $\{\vec v_1, ..., \vec v_k\}$ in $\R^n$ are <b>linear independent</b> if

$$
c_1\vec v_1 + c_2\vec v_2 + ... + c_k\vec v_k = \vec 0
$$

only the case where $c_1, ..., c_k$ <u>are zero</u>.
has only <b>trivial</b> solution.

$\therefore$ This mean if $\bold{\vec c}$ is <u>not zero</u> and linear combination is <u>zero</u>. Then the vectors are <b>linear dependent</b>.

<u>Example</u>
Given there are 3 vectors

$$
\begin{pmatrix}
1 \\
1 \\
h
\end{pmatrix},
\begin{pmatrix}
1 \\
h \\
1
\end{pmatrix},
\begin{pmatrix}
h \\
1 \\
1
\end{pmatrix}
$$

If <u>independent</u>, then

$$
c_1\begin{pmatrix}
1 \\
1 \\
h
\end{pmatrix} +
c_2\begin{pmatrix}
1 \\
h \\
1
\end{pmatrix} +
c_3\begin{pmatrix}
h \\
1 \\
1
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$

For Only if: $\color{blue}\boxed{c_1=c_2=c_3=0}$

$$
  \begin{pmatrix}
  1 & 1 & h & 0 \\
  1 & h & 1 & 0 \\
  h & 1 & 1 & 0 \\
  \end{pmatrix} \\
  \leadsto \\
  \begin{pmatrix}
  1 & 1 & h & 0 \\
  0 & h-1 & 1-h & 0 \\
  0 & 0 & 2-h-h^2 & 0 \\
  \end{pmatrix}
$$

$\therefore$ Since, $2-h-h^2=0$ then $c_3$ is <b>free</b>. so $c_3$ can be anything other than $0$. hence, vectors are <b>dependent</b>.

So, for vectors to be <b>Independent</b>.

$$
2-h-h^2=0 \\
-(h+2)(h-1)=0 \\
h\ne -2, h \ne 1
$$

### Lesson 2: Linear independence Theorems

Suppose $\vec v_1, \vec v_2 \in \R^n$.
If $\{\vec v_1, \vec v_2\}$ linear <u>dependent</u>. Then,

$$
c_1\vec v_1 + c_2\vec v_2 = \vec 0
$$

Not both $c_1, c_2$ are all zero.

<u>Dependent vectors</u>

1. if $\vec v_1 = \vec 0, c_2=0$ and $c_1\vec v_1 + c_2\vec v_2 = \vec 0$
   Then, $\vec v_1$ and $\vec v_2$ are <b>dependent</b> (regardless $c_1$).
2. if $\vec v_1 \ne \vec 0, \vec v_2 \ne \vec 0$ then $\vec v_2=-\frac{c_1}{c_2}\vec v_1$ so $\vec v_1$ and $\vec v_2$ are multiple of each others. The vectors are <b>parallel</b> (one vector is in the span of the other).
   $$
   \begin{pmatrix}
   1 & 0 & 1 \\
   2 & 1 & 3 \\
   3 & 1 & 4
   \end{pmatrix} \\
   \vec v_1 + \vec v_2 = \vec v_3
   $$

<div>
  <img src='/assets/img/edx-algebra-1/9.png' width='250'>
</div>

<b>Theorem</b>:

1. <u>More vectors than elements:</u> suppose $\vec v_1, ..., \vec v_k$ are vectors in $\R^n$. if $k>n$ then $\{\vec v_1, ...\vec v_k\}$ is <b>linear dependent</b> because to be <b>independent</b> it has to be <b>pivot</b> since <u>number of columns are more than rows</u>, so every columns cannot be pivot.

$$
\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1
\end{pmatrix}
$$

2. <u>Set contains zero vector</u>:if one or more of $\vec v_1, ...\vec v_k$ is $\vec 0$. The same reason as (1.) because not all columns are not <b>pivot</b>.
   $$
   \begin{pmatrix}
   1 & 0  \\
   0 & 0
   \end{pmatrix}
   $$

<u>Linear independent</u>

$$
\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
0 & 0 & 1
\end{pmatrix} \\
\text{every columns are pivotal}
$$

# Module 3: Linear Transforms

The same concept as funtion,

## Topic 1: An Introduction to Linear Transforms

### Lesson 1: Domain, Codomain, Range

$$
T:\R^n\to \R^m, T(\vec x)=A\vec x
$$

<u>Matrix transformation</u>:

- A : $m\times n$ matrix
- $\R^n$ : <u>domain</u> of $T$
- $\R^m$ : <u>co-domain</u> of $T$
- $T(\vec x)$ : <b>image</b> of $\vec x$ under $T$
- <b>Range</b> of $T(\vec x)$ : set of possible images of $T(\vec x)$

<u>co-domain</u> : possible set of values
<u>range</u> : actual set of value

<div>
  <img src='/assets/img/edx-algebra-1/10.png' width='250'>
</div>

<u>Example</u>:

$$
A=\begin{pmatrix}
1 & 1 \\
0 & 1 \\
1 & 1
\end{pmatrix},
\vec u = \begin{pmatrix}
3 \\
4
\end{pmatrix} \\
T(\vec x) = A\vec x
$$

1. What is `domain` and `co-domain` of $T$?
   For $A\vec x$ to be <b>defined</b>, $\vec x \in \R^2$
   $\rArr$ domain is $\R^2$ and $A\vec x \in \R^3$
   $\rArr$ co-domain is $\R^3$

2. Compute the image of $\vec u$ under $T$

   $$
   T(\vec u) = \begin{pmatrix}
   1 & 1 \\
   0 & 1 \\
   1 & 1
   \end{pmatrix}
   \begin{pmatrix}
   3 \\
   4
   \end{pmatrix}
   =
   \begin{pmatrix}
   7 \\
   4 \\
   7
   \end{pmatrix}
   $$

3. What is the `range` of $T$?
   $$
   T=A\vec x=x_1\begin{pmatrix}
   1 \\
   0 \\
   1
   \end{pmatrix}+x_1\begin{pmatrix}
   1 \\
   1 \\
   1
   \end{pmatrix}
   $$
   $\rArr$ range is span
   $
\left\{
\begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix},
\begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}
\right\}
$

Interpret of $A\vec x=\vec b$

1. set oof linear equation
2. augmented matrix
3. matrix equation
4. vector equation
5. linear transform equation

### Lesson 2: Geometric Interpretations of Linear Transforms

$T: R^n \to R^m$ is <b>linear</b> if:

- $T(\vec u + \vec v) = T(\vec u) + T(\vec v)$ where $\vec u, \vec v \in \R^n$
- $T(c\vec v) = cT(\vec v)$ where $\vec v \in \R^n, c \in \R$

<b>Principle of Superposition</b>

$$
T(c_1\vec v_1 + ... + c_k\vec v_k) = c_1T(\vec v_1) + ... + c_kT(\vec v_k)
$$

<u>Geometric of linear transformation in $\R^2$</u>

Suppose $T(\vec x) = A\vec x$ is a linear transformation.
$\vec x = \dbinom{a}{b}$

1. $A = \begin{pmatrix}
0 & 1\\ 
1 & 0
\end{pmatrix}
$
   $\rArr T(\vec x) = \dbinom{b}{a}$
   $\rArr$ <u>Reflection</u> through $x = y$

2. $A = \begin{pmatrix}
1 & 0\\ 
0 & 0
\end{pmatrix}
$
   $\rArr T(\vec x) = \dbinom{a}{0}$
   $\rArr$ <u>Projection</u> into x-axis.

3. $A = \begin{pmatrix}
k & 0\\ 
0 & k
\end{pmatrix}
$
   $\rArr T(\vec x) = \dbinom{ka}{kb}$
   $\rArr$ <u>Scale</u> by $k$.

## Topic 2: Linear Transforms

### Lesson 1: Standard Vectors

<b>Standard vector</b>, $\vec e_i$ is a vector in $\R^n$ which every entries are $0$ <u>except entry</u> $i = 1$.

<u>example</u> in $\R^3$

$$
\vec e_1= \begin{pmatrix}
1 \\
0 \\
0
\end{pmatrix}
e_2= \begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}
e_3= \begin{pmatrix}
0 \\
0 \\
1
\end{pmatrix}
$$

A property of the standard vectors

Let $A$ is $m\times n$ matrix with columns $\vec v_1, \vec v_2, ..., \vec v_n$ then

$$
\vec v_i=A\vec e_i
$$

Pull out column $i$ of matrix $A$.

<u>Standard matrix </u> $A=(T(\vec e_1)\enspace T(\vec e_2)\enspace ...\enspace T(\vec e_n))$ for rotation in $\R^2$.

$$
A= \begin{pmatrix}
cos\theta & -sin\theta \\
sin\theta & cos\theta
\end{pmatrix}
$$

There is a proof for that. but now just remember it.

This mean, if we have $\vec v = \dbinom{2}{0}$. and we want to rotate $\theta = \frac{\pi}{2}$, then

$$
A= \begin{pmatrix}
cos\frac{\pi}{2} & -sin\frac{\pi}{2} \\
sin\frac{\pi}{2} & cos\frac{\pi}{2}
\end{pmatrix}=\begin{pmatrix}
0 & -1 \\
1 & 0
\end{pmatrix}
$$

Therefore

$$
T(\vec v)=\begin{pmatrix}
0 & -1 \\
1 & 0
\end{pmatrix}= \begin{pmatrix}
2 \\
0
\end{pmatrix}= \begin{pmatrix}
0 \\
2
\end{pmatrix}
$$

This mean, given a vector $\vec v = \dbinom{2}{0}$ and we want to transform it counter clockwise $\theta = \frac{\pi}{2}$, then result $\vec v' = \dbinom{0}{2}$, but the key is how can we define matrix $A$?

### Lesson 2: Standard Matrices of Linear Transforms

<b>2D Reflection</b>

Note: <u>inflection</u> changes direction, so it changes sign but manitude does not change.

1. reflection through $x_1$ axis

$
\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/11.png' width='200'>
</div>

2. reflection through $x_2$ axis

$
\begin{pmatrix}
-1 & 0 \\
0 & 1
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/12.png' width='200'>
</div>

3. reflection through $x_2=x_1$ axis

$
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/13.png' width='200'>
</div>

4. reflection through $x_2=-x_1$ axis

$
\begin{pmatrix}
0 & -1 \\
-1 & 0
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/14.png' width='200'>
</div>

<b>2D Contractions and Expansions</b>

1. Horizontal

<u>contraction</u> : $|k| < 1$
<u>expansion</u> : $k > 1$

$
\begin{pmatrix}
k & 0 \\
0 & 1
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/15.png' width='200'>
</div>

2. Vertical

<u>contraction</u> : $|k| < 1$
<u>expansion</u> : $k > 1$

$
\begin{pmatrix}
1 & 0 \\
0 & k
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/16.png' width='200'>
</div>

<b>2D shears</b>

1. Horizontal

<u>left</u> : $k < 0$
<u>right</u> : $k > 0$

$
\begin{pmatrix}
1 & k \\
0 & 1
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/17.png' width='200'>
</div>

2. Vertical

<u>down</u> : $k < 0$
<u>up</u> : $k > 0$

$
\begin{pmatrix}
1 & 0 \\
k & 1
\end{pmatrix}
$

<div>
  <img src='/assets/img/edx-algebra-1/18.png' width='200'>
</div>

<b>2D projection</b>

1. projection onto $x_1$ axis

$
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
$

2. projection onto $x_2$ axis

$
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
$

### Lesson 3: Onto and One-to-one

1. <b>onto</b>

Linear transformation $T : \R^n \to \R^m$ is <b>onto</b> if for all $\vec b \in \R^m$ there is a $\vec x \in \R^n$ so that $T(\vec x)=A\vec x=\vec b$.

- has at least 1 solution (consistent)
- every rows are pivotal

2. <b>one-to-one</b>

- has at most 1 solution (possibly no)
- every columns are pivotal
