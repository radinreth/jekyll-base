---
layout: post
title: Elementary Linear Algebra
date: 2024-05-06 14:59:57
categories: research
description: Basic understanding of linear algebra
tags: math linear-algebra
---

### The solutions of linear equation

**Homogeneous equation** is an equation where the result is zero.

**Consistent linear system** is a system that has at least one solution.
**Inconsistent linear system** is a system that has no solution.

**1. One solution**

The solution of linear system with 2 unknowns is the intersection between those lines.

$$
x-y=1
2x+y=6

(7/3, 4/3)
$$

**2. No solution**

$$
x+y=4
3x+3y=6

-3r_1 + r_2 -> r_2

x+y=4
0=-6
$$

1. 2nd equation is **not true / contradictory**.
2. The system has **no solution**.
3. Geometrically, **paralell line**.

**3. Infinitely many solutions**

$$
4x-2y=1
16x-8y=4

-4r_1 + r_2 -> r_2

4x-2y=1
0=0
$$

1. it is called **parameteric equations**.

### Augmented Matrices and Elementary Row Operations

<p>A Convenient way to represent matrix with a lot of unknowns</p>
<div>
  <img src='/assets/img/augmented-matrices/1.png' width='250'>
</div>

<br />

<p>Using matrices</p>
<div>
  <img src='/assets/img/augmented-matrices/2.png' width='250'>
</div>

<br />

<p>example : **augmented matrix** for system of equation</p>
<div>
  <img src='/assets/img/augmented-matrices/3.png' width='250'>
</div>

**Elementary row opertions** is a way to solve linear equations by

1. Multiply row by non-zero constant
2. Swap 2 rows
3. Add a constant times one row to another

By using **Elementary Row Operations**, the augmented matrix is put in **reduced row echelon form** then the solution set can be obtained.

## Gaussian Elimination

procedure for solving system of linear equation

A matrix with **reduced row echelon form** must have

1. lead by 1
2. any rows that entirely zero, must be at the bottom of matrix
3. the leading 1 of the lower row occur farther to the right
4. each column that contain a leading 1 , has 0 everywhere else in that column / must have zero above and below 1.

**1, 2, 3** is said to be in **row echelon form**
**1, 2, 3, 4** is said to be in **reduced row echelon form**

Example: reduced row echelon form

<div>
  <img src='/assets/img/augmented-matrices/4.png' width='250'>
</div>
<div>
  <img src='/assets/img/augmented-matrices/4-1.png' width='250'>
</div>

<br />

Example: row echelon form but not reduced row echelon form

<div>
  <img src='/assets/img/augmented-matrices/5.png' width='250'>
</div>
<div>
  <img src='/assets/img/augmented-matrices/5-1.png' width='250'>
</div>

**free variables** used for infinite number of solution where variable(s) treated at parameter.

(1)

$$
\begin{cases}
x+3z=-1 \\
y-4z=2
\end{cases}
$$

$$
\begin{cases}
x=-1-3z \\
y=2+4z
\end{cases}
$$

`z` is treated as parameter and assigned value `t`.

(-1-3t, 2+4t, t)

##### Definition: 1

A linear system has infinitely many solutions, where solutions obtained by assigning **parameters** called **general solution**.

### Elimination Method

**elimination procedure** used to reduce **any matrix** to **RREF**.

### Homogeneous Linear Systems

**homogeneous** if constant terms are all **zero**.
It always has solution(s) (consistent) called **trivial solution**.
It is possible to have **nontrivial solution** whenever the system has more **unknowns** than number of equations.

**trivial solution** means all zero as solution.

<div>
  <img src='/assets/img/augmented-matrices/6.png' width='250'>
</div>

1. If **homogeneous** has `n` variables, and if RREF has `r` nonzero row, then the system has `n-r` free variables.
2. **homogeneous** has more unknown than equations has infinitely many solutions.

**Gaussian Elimination** suitable for solving small linear system.
for large system use **back-substitution**.

**pivot column** of matrix A are the position of leading 1's.

<div>
  <img src='/assets/img/augmented-matrices/7.png' width='250'>
</div>
<p>The pivot columns are 1, 3, 5.</p>

Computer generally approximate numbers which introduce **roundoff** erros.

# 1.3 Matrices and Matrix Operations

<div>
  <img src='/assets/img/augmented-matrices/8.png'>
</div>
<p>Denote the entry in row `i` and column `j` of matrix A</p>

<div>
  <img src='/assets/img/augmented-matrices/9.png' width='250'>
</div>
<p>Denote for 1xn `row` and mx1 `column` vector</p>

<div>
  <img src='/assets/img/augmented-matrices/10.png' width='250'>
</div>
nxn matrix called **squared matrix** a*{11}, a*{22}, ..., a\_{nn}

**add** or **subtract** between matrices must have the same size.

Multiply a matrix with a number(scalar) is by multiply each entry with that scalar.

Matrix to matrix multiplication works differently.

if A*{m\*r} and B*{r\*n}
=> size of A \* B = m \* n

AB*{ij} = sum( A*{row i} \* B\_{col of j})

To multiply 2 matrices the number of column in first matrix must be equal to
number of row in second matrix, otherwise, **undefined**.

<div>
  <img src='/assets/img/augmented-matrices/11.png' width='250'>
</div>

## Partitioned Matrices

means divide a matric into smaller matrix.

**row vector** has one column.
**column vector** has one row.

**linear combination** is the sum of matrices with the same size multiply by coefficient.

Example : A_1, A_2, A_3 are matrices that has the same size.
c_1, c_2, c_3 are scalars

then linear combination denoted by

$$
c_1A_1 + c_2A_2 + c_3A_3 + ... + cnA_n
$$

if `A` is an m\*n matrix and `x` is nx1 column vector then
`Ax` can express as a linear combination.

<div>
  <img src='/assets/img/augmented-matrices/12.png' width='250'>
</div>
<div>
  <img src='/assets/img/augmented-matrices/13.png' width='250'>
</div>

## Matrices product as linear combination

<div>
  <img src='/assets/img/augmented-matrices/14.png' width='250'>
</div>

## Matrices Form a linear system

Ax = b

the augmented matrix obtained by adjoin `b` to `A`.
A = coefficient matrix
x = variables
b = constants

<div>
  <img src='/assets/img/augmented-matrices/15.png' width='250'>
</div>
<div>
  <img src='/assets/img/augmented-matrices/16.png' width='250'>
</div>

# Transpose of a Matrix

The transpose of m\*n matrix is n\*m matrix
by interchange rows and columns.

<div>
  <img src='/assets/img/augmented-matrices/17.png' width='250'>
</div>

# Trace of a Matrix

For square matrix A, then **trace of A**, denoted by **tr(A)** obtained
by sum of entries on the main diagonal.
return `undefined` if not a square matrix.

<div>
  <img src='/assets/img/augmented-matrices/18.png' width='250'>
</div>

# Inverses; Algebraic Properties of Matrices

### Properties of Matrix addition and Scalar Multiplication

1. Commutative
2. Associative
3. Distributive

[to be continue]
