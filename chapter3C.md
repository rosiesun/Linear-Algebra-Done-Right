Linear Algebra Done Right - Chapter 3 Linear Maps <br>
3C Matrices
================
Rosie Sun <br>
2026-04-02


We know that if $v_1,...,v_n$ is a basis of $V$ and $T: V \rightarrow W$ is linear, then the values of $Tv_1,...,Tv_n$ determine the values of $T$ on arbitrary vectors in $V$ - see the linear map lemma 3.4. As we will soon see, matrices provided an efficient method of recording the values of the $Tv_k$'s in terms of a basis of $W$.


### 3.29 Definition: matrix
Supppose $m, n$ are nonnegative integers. An m-by-n matrix $A$ is a rectangular array of elements of $F$ with m rows and n columns:

$$
\begin{pmatrix}
A_{1,1} & ... & A_{1,n} \\
... & ... & ... \\
A_{m,1} & ... & A_{m,n}
\end{pmatrix}
$$

The notation $A_{j,k}$ denotes the entry on row j, column k of $A$.


### 3.31 Definition: matrix of a linear map
Suppose $T \in L(V,W)$ and $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_m$ is a basis of $W$. The matrix of $T$ with respect to these bases is the m-by-n matrix $M(T)$ whose entries $A_{j,k}$ are defined by

$$Tv_k = A_{1,k} w_1 + ... + A_{m,k} w_m$$

If the bases $v_1,...,v_n$ and $w_1,...,w_m$ are not clear from the context, then the notation $M(T, (v_1,...,v_n), (w_1,...,w_m))$ is used.


### 3.35 
Suppose $S, T \in L(V,W)$. Then $M(S+T) = M(S) + M(T)$.


### 3.38
Suppose $\lambda \in F$ and $T \in L(V,W)$. Then $M(\lambda T) = \lambda M(T)$.


### 3.39 Notation
For m and n positive integers, the set of all m-by-n matrices with entries in $F$ is denoted by $F^{m,n}$. 


### 3.40
Suppose m and n are positive integers. With addition and scalar multiplication defined as above, $F^{m,n}$ is a vector space of dimension mn. 


### 3.41 Definition: matrix multiplication
Suppose $A$ is a m-by-n matrix and $B$ is an n-by-p matrix. Then $AB$ is defined to be the m-by-p matrix whose entry in row j, column k is given by the equation 

$$(AB)_{j, k} = \sum_{r=1}^n A_{j, r} B_{r, k} .$$

Thus the entry in row j, column k, of $AB$ is computed taking row j of $A$ and column k of $B$, multiplying together corresponding entries, and then summing.


### 3.43
If $T \in L(U,V)$ and $S \in L(V,W)$, then $M(ST) = M(S)M(T)$.


### 3.48
Suppose $A$ is an m-by-n matrix and $B$ is an n-by-p matrix. Then

$$(AB)_{., k} = A B_{., k}$$

if $1 \leq k \leq p$. In other words, column k of $AB$ equals $A$ times column k of $B$.


### 3.50
Suppose $A$ is an m-by-n matrix and $b = (b_1, ..., b_n)$ is an n-by-1 matrix. Then 

$$Ab = b_1 A_{., 1} + ... + b_n A_{., n} .$$

In other words, $Ab$ is a linear combination of the columns of $A$, with the scalars that multiply the columns coming from $b$.


### 3.52 Definition: column rank, row rank
Suppose $A$ is an m-by-n matrix with entries in $F$. 

- The column rank of $A$ is the dimension of the span of the columns of $A$ in $F^{m, 1}$.
- The row rank of $A$ is the dimension of the span of the rows of $A$ in $F^{1, n}$.




