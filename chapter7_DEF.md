Linear Algebra Done Right - Chapter 7 <br> 
Operators on Inner Product Spaces
================
Rosie Sun <br> 
2026-06-01



# 7D Isometries, Unitary Operators, and Matrix Factorization

### 7.44 Definition: isometry
A linear map $S \in L(V, W)$ is called an isometry if 

$$||Sv|| = ||v||$$

for every $v \in V$. In other words, a linear map is an isometry if it preserves norms.


### 7.49
Suppose $S \in L(V, W)$. Suppose $e_1, ..., e_n$ is an orthonormal basis of $V$ and $f_1, ..., f_m$ is an orthonormal basis of $W$. Then the following are equivalent. 

(a) $S$ is an isometry.

(b) $S^* S = I$.

(c) $\langle Su, Sv\rangle  = \langle u, v\rangle $ for all $u, v \in V$.

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

(a) $T^* T$ is a positive operator on $V$;

(b) $null T^* T = null T$;

(c) $range T^* T = range T^*$;

(d) $dim range T = dim range T^* = dim range T^* T$.



### 7.65 Definition: singular values
Suppose $T \in L(V, W)$. The singular values of $T$ are teh nonnegative square roots of the eigenvalues of $T^* T$, listed in decreasing order, each included as many times as the dimension of the corresponding eigenspace of $T^* T$.

### 7.70 Singular value decomposition
Suppose $T \in L(V, W)$ and the positive singular values of $T$ are $s_1,...,s_m$. Then there exist orthonormal lists $e_1,...,e_m$ in $V$ and $f_1,...,f_m$ in $W$ such that 

$$Tv = s_1 \langle v, e_1\rangle  f_1 + ... + s_m \langle v, e_m\rangle  f_m$$

for every $v \in V$.

### 7.80 Matrix version of SVD
Suppose $A$ is a p-by-n matrix of rank m \rangle = 1. Then there exist a p-by-m matrix $B$ with orthonormal columns, an m-by-m diagonal matrix $D$ with positive numbers on the diagonal, and an n-by-m matrix $C$ with orthonormal columns such that 

$$A = B D C^*.$$




## Exercises

### (1) 

### (2)

### (3)

### (5)

### (8)

### (9)

### (10)

### (11)

### (13)

### (15)





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


