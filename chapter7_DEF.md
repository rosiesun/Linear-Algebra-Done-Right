Linear Algebra Done Right - Chapter 7 <br> 
Operators on Inner Product Spaces
================
Rosie Sun <br> 
2026-06-15



# 7D Isometries, Unitary Operators, and Matrix Factorization

### 7.44 Definition: isometry
A linear map $S \in L(V, W)$ is called an isometry if 

$$\lVert Sv \rVert = \lVert v \rVert$$

for every $v \in V$. In other words, a linear map is an isometry if it preserves norms.


### 7.49 characterization of isometries
Suppose $S \in L(V, W)$. Suppose $e_1, ..., e_n$ is an orthonormal basis of $V$ and $f_1, ..., f_m$ is an orthonormal basis of $W$. Then the following are equivalent. 

(a) $S$ is an isometry.

(b) $S^{\ast} S = I$.

(c) $\langle Su, Sv\rangle  = \langle u, v\rangle $ for all $u, v \in V$.

(d) $Se_1, ..., Se_n$ is an orthonormal list in $W$.

(e) The columns of $M(S, (e_1, ..., e_n), (f_1, ..., f_m))$ form an orthonormal list in $F^m$ with respect to the Euclidean inner product.

Proof:

First suppose (a) holds, so $S$ is an isometry. Note that $I - S^{\ast} S$ is self-adjoint.

If $v \in V$ then 

$$
\begin{aligned}
\langle (I - S^{\ast} S) v, v \rangle 
    &= \langle v, v \rangle - \langle S^{\ast} S v, v \rangle \\
    &= \lvert v \rvert^2 - \langle Sv, Sv \rangle \\
    &= \lvert v \rvert^2 - \lvert Sv \rvert^2 \\
    &= \lvert v \rvert^2 - \lvert v \rvert^2 \\
    &= 0
\end{aligned}
$$

By 7.16, the self-adjoint operator $I - S^{\ast} S$ equals 0. Thus $S^{\ast} S = I$, proving that (a) implies (b).

Now suppose (b) holds, so $S^{\ast} S = I$. If $u, v \in V$, then 

$$\langle Su, Sv \rangle = \langle S^{\ast} S u, v \rangle = \langle Iu, v \rangle = \langle u, v \rangle ,$$

proving that (b) implies (c).

Now suppose that (c) holds, so $\langle Su, Sv \rangle = \langle u, v \rangle$ for all $u, v \in V$. Thus if $j, k \in \\{1, ..., n\\}$, then 

$$\langle Se_j, Se_k \rangle = \langle e_j, e_k \rangle .$$

Hence $Se_1, ..., Se_n$ is an orthonormal list in $W$, proving that (c) implies (d).


### 7.51 Definition: unitary operator
An operator $S \in L(V)$ is called unitary if $S$ is an invertible isometry.


### 7.53 characterization of unitary operators


### 7.58 QR factorization
Suppose $A$ is a square matrix with linearly independent columns. Then there exist unique matrices $Q$ and $R$ such that $Q$ is unitary, $R$ is upper triangular with only positive numbers on its diagonal, and 

$$A = QR.$$


### 7.63 Cholesky factorization
Suppose $B$ is a positive definite matrix. Then there exists a unique upper-triangular matrix $R$ with only positive numbers on its diagonal such that 

$$B = R^{\ast} R.$$





## Exercises

### (1)

### (2)

### (3)

### (4)

### (5)

### (8)

### (9)





--------------------------------------------------------------------------------
# 7E Singular Value Decomposition

### 7.64
Suppose $T \in L(V, W)$. Then

(a) $T^{\ast} T$ is a positive operator on $V$;

(b) $null T^{\ast} T = null T$;

(c) $range T^{\ast} T = range T^{\ast}$;

(d) $dim range T = dim range T^{\ast} = dim range T^{\ast} T$.


### 7.65 Definition: singular values
Suppose $T \in L(V, W)$. The singular values of $T$ are teh nonnegative square roots of the eigenvalues of $T^{\ast} T$, listed in decreasing order, each included as many times as the dimension of the corresponding eigenspace of $T^{\ast} T$.


### 7.70 Singular value decomposition
Suppose $T \in L(V, W)$ and the positive singular values of $T$ are $s_1,...,s_m$. Then there exist orthonormal lists $e_1,...,e_m$ in $V$ and $f_1,...,f_m$ in $W$ such that 

$$Tv = s_1 \langle v, e_1\rangle  f_1 + ... + s_m \langle v, e_m\rangle  f_m$$

for every $v \in V$.


### 7.80 Matrix version of SVD
Suppose $A$ is a p-by-n matrix of rank m \rangle = 1. Then there exist a p-by-m matrix $B$ with orthonormal columns, an m-by-m diagonal matrix $D$ with positive numbers on the diagonal, and an n-by-m matrix $C$ with orthonormal columns such that 

$$A = B D C^{\ast}.$$




## Exercises

### (1) 

### (2)

### (3)

### (5)

### (7) Suppose that $T \in L(V)$ is self-adjoint or that $F = C$ and $T \in L(V)$ is normal. Let $\lambda_1, ..., \lambda_n$ be the eigenvalues of $T$, each included in this list as many times as the dimension of the corresponding eigenspace. Show that the singular values of $T$ are $|\lambda_1|, ..., |\lambda_n|$, after these numbers have been sorted into descending order.



### (8)

### (9) Suppose $T \in L(V, W)$. Show that $T$ and $T^{\ast}$ have the same positive singular values.



### (10) Suppose $T \in L(V, W)$ has singular values $s_1, ..., s_n$. Prove that if $T$ is an invertible linear map, then $T^{-1}$ has singular values $\frac{1}{s_n}, ..., \frac{1}{s_1}$.



### (11)

### (13)

### (14) Suppose $T \in L(V, W)$. Let $s_n$ denote the smallest singular value of $T$. Prove that $s_n \lvert v \rvert \leq \lvert Tv \rvert$ for every $v \in V$.


### (15) Suppose $T \in L(V)$ and $s_1 \geq ... \geq s_n$ are the singular values of $T$. Prove that if $\lambda$ is an eigenvalue of $T$, then $s_1 \geq |\lambda| \geq s_n$.







--------------------------------------------------------------------------------
# 7F Consequences of Singular Value Decomposition

### 7.86 Definition: norm of a linear map
Suppose $T \in L(V, W)$. Then the norm of $T$, denoted by $\lVert T \rVert$, is defined by

$$\lVert T \rVert = max \\{\lVert Tv \rVert: v \in V, \lVert v \rVert \leq 1 \\} $$ 


## Exercises

### (2)


### (3)


### (4)


### (5)


### (6)


### (17)


### (19)


### (20)


### (24)


