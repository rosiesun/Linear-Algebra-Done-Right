Linear Algebra Done Right - Chapter 7 <br>
Operators on Inner Product Spaces
================
Rosie Sun <br>
2026-06-01


# 7A Self-Adjoint and Normal Operators

### 7.1 Definition: adjoint
Suppose $T \in L(V, W)$. The adjoint of $T$ is the function $T^*: W \rightarrow V$ such that 

$$<Tv, w> = <v, T^* w>$$

for every $v \in V$ and every $w \in W$.

### 7.4
If $T \in L(V, W)$, then $T^* \in L(W, V)$.

Proof:

### 7.5
Suppose $T \in L(V, W)$. Then

(a) $(S+T)^* = S^* + T^*$ for all $S \in L(V, W)$;

(b) $(\lambda T)^* = \overline{\lambda} T^*$ for all $\lambda \in F$;

(c) $(T^*)^* = T$;

(d) $(ST)^* = T^* S^*$ for all $S \in L(W, U)$ (here $U$ is a finite-dimensional inner product space over $F$);

(e) $I^* = I$, where $I$ is the identity operator on $V$;

(f) if $T$ is invertible, then $T^*$ is invertible and $(T^*)^{-1} = (T^{-1})^*$.

Proof:

### 7.6
Suppose $T \in L(V, W)$. Then 

(a) $null T^* = (range T)^{\perp}$;

(b) $range T^* = (null T)^{\perp}$;

(c) $null T = (range T^*)^{\perp}$;

(d) $range T = (null T^*)^{\perp}$.

Proof:

### 7.7 Definition: conjugate transpose
The conjugate transpose of an m-by-n matrix $A$ is the n-by-m matrix $A^*$ obtained by interchanging the rows and columns and then taking the complex conjugate of each entry. In other words, if $j \in \\{1,...,n\\}$ and $k \in \\{1,...,m\\}$, then 

$$(A^*)_{j, k} = \overline{A_{k, j}}$$

### 7.9


### 7.10 Definition: self-adjoint
An operator $T \in L(V)$ is called self-adjoint if $T = T^*$.

### 7.12
Every eigenvalue of a self-adjoint operator is real.

Proof:

### 7.13
Suppose $V$ is a complex inner product space and $T \in L(V)$. Then

$<Tv, v> = 0$ for every $v \in V$ $\iff T = 0$.

Proof:

### 7.14


### 7.16

### 7.18

### 7.20

### 7.21

### 7.22

### 7.23


## Exercises

#### (1)

#### (2)

#### (3)

#### (4)

#### (5)

#### (6)

#### (7)

#### (10)

#### (15)

#### (17)

#### (18)

#### (20)

#### (22)

#### (29)

#### (30)

#### (32) Suppose $T: V \rightarrow W$ is a linear map. Show that under the standard identification of $V$ with $V'$ and the corresponding identification of $W$ and $W'$, the adjoint map $T*: W \rightarrow V$ corresponds to the dual map $T': W' \rightarrow V'$. More precisely, show that $T'(\phi_w) = \phi_{T* w}$. 

Suppose $v \in V, w \in W$. Then 

$$
\begin{aligned}
T'(\phi_w) (v) &= (\phi_w \circ T) (v) \\
    &= \phi_w (Tv) \\
    &= <Tv, w> \\
    &= <v, T^* w> \\
    &= \phi_{T^* w} (v)
\end{aligned}
$$

for all $v \in V$. 

Thus $T'(\phi_w) = \phi_{T^* w}$.




# 7B Spectral Theorem








# 7C Positive Operators

### 7.34 Definition: positive operator
An operator $T \in L(V)$ is called positive if $T$ is self-adjoint and 

$$<Tv, v> = 0$$

for all $v \in V$.

### 7.36 Definition: square root
An operator $R$ is called a square root of an operator $T$ if $R^2 = T$.

### 7.38
Let $T \in L(V)$. Then the following are equivalent.

(a) $T$ is a positive operator. 

(b) $T$ is self-adjoint and all eigenvalues of $T$ are nonnegative.

(c) With respect to some orthonormal basis of $V$, the matrix of $T$ is a diagonal matrix with only nonnegative numbers on the diagonal.

(d) $T$ has a positive square root.

(e) $T$ has a self-adjoint square root.

(f) $T = R^* R$ for some $R \in L(V)$.

### 7.39
Every positive operator on $V$ has a unique positive square root.

### 7.40 Notation
For $T$ a positive operator, $\sqrt{T}$ denotes the unique positive square root of $T$.

### 7.43
Suppose $T$ is a positive operator on $V$ and $v \in V$ is such that $<Tv, v> = 0$. Then $Tv = 0$.






# 7D Isometries, Unitary Operators, and Matrix Factorization

### 7.44 Definition: isometry
A linear map $S \in L(V, W)$ is called an isometry if 

$$||Sv|| = ||v||$$

for every $v \in V$. In other words, a linear map is an isometry if it preserves norms.

### 7.49
Suppose $S \in L(V, W)$. Suppose $e_1, ..., e_n$ is an orthonormal basis of $V$ and $f_1, ..., f_m$ is an orthonormal basis of $W$. Then the following are equivalent. 

(a) $S$ is an isometry.

(b) $S^* S = I$.

(c) $<Su, Sv> = <u, v>$ for all $u, v \in V$.

(d) $Se_1, ..., Se_n$ is an orthonormal list in $W$.

(e) The columns of $M(S, (e_1, ..., e_n), (f_1, ..., f_m))$ form an orthonormal list in $F^m$ with respect to the Euclidean inner product.

### 7.51 Definition: unitary operator
An operator $S \in L(V)$ is called unitary if $S$ is an invertible isometry.

### 7.53

### 7.58 QR factorization
Suppose $A$ is a square matrix with linearly independent columns. Then there exist unique matrices $Q$ and $R$ such that $Q$ is unitary, $R$ is upper triangular with only positive numbers on its diagonal, and 

$$A = QR.$$

### 7.63 Cholesky factorization
Suppose $B$ is a positive definite matrix. Then there exists a unique upper-triangular matrix $R$ with only positive numbers on its diagonal such that 

$$B = R^* R.$$








# 7E Singular Value Decomposition

### 7.64
Suppose $T \in L(V, W)$. Then

(a) $T^* T$ is a positive operator on $V$;

(b) $null T^* T = null T$;

(c) $range T^* T = range T^*$;

(d) $dim range T = dim range T^* = dim range T^* T$.



### 7.65 Definition: singular values
Suppose $T \in L(V, W)$. The singular values of $T$ are teh nonnegative square roots of the eigenvalues of $T^* T$, listed in decreasing order, each included as many times as the dimension of the corresponding eigenspace of $T^* T$.

### 7.70 Singular value decomposition
Suppose $T \in L(V, W)$ and the positive singular values of $T$ are $s_1,...,s_m$. Then there exist orthonormal lists $e_1,...,e_m$ in $V$ and $f_1,...,f_m$ in $W$ such that 

$$Tv = s_1 <v, e_1> f_1 + ... + s_m <v, e_m> f_m$$

for every $v \in V$.

### 7.80 Matrix version of SVD
Suppose $A$ is a p-by-n matrix of rank m >= 1. Then there exist a p-by-m matrix $B$ with orthonormal columns, an m-by-m diagonal matrix $D$ with positive numbers on the diagonal, and an n-by-m matrix $C$ with orthonormal columns such that 

$$A = B D C^*.$$






# 7F Consequences of Singular Value Decomposition

### 7.86 Definition: norm of a linear map
Suppose $T \in L(V, W)$. Then the norm of $T$, denoted by $||T||$, is defined by

$$||T|| = max \\{||Tv||: v \in V, ||v|| \leq 1 \\}.$$ 


## Exercises



