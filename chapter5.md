Linear Algebra Done Right - Chapter 5 <br>
Eigenvalues and Eigenvectors
================
Rosie Sun <br>
2026-04-21


# 5A Invariant Subspaces

### 5.1 Definition: operator
A linear map from a vector space to itself is called an operator.


### 5.2 Definition: invariant subspace
Suppose $T \in L(V)$. A subspace $U$ of $V$ is called invariant under $T$ if $Tu \in U$ for every $u \in U$.


### 5.5 Definition: eigenvalue
Suppose $T \in L(V)$. A number $\lambda \in F$ is called an eigenvalue of $T$ if there exists $v \in V$ such that $v \neq 0$ and $Tv = \lambda v$.


### 5.7
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $\lambda \in F$. Then the following are equivalent. 

- $\lambda$ is an eigenvalue of $T$.
- $T - \lambda I$ is not injective.
- $T - \lambda I$ is not surjective.
- $T - \lambda I$ is not invertible.


### 5.8 Definition: eigenvector
Suppose $T \in L(V)$ and $\lambda \in F$ is an eigenvalue of $T$. A vector $v \in V$ is called an eigenvector of $T$ corresponding to $\lambda$ if $v \neq 0$ and $Tv = \lambda v$.


### 5.11 
Suppose $T \in L(V)$. Then every list of eigenvectors of $T$ corresponding to distinct eigenvalues of $T$ is linearly independent.


### 5.12
Suppose $V$ is finite-dimensional. Then each operator on $V$ has at most $dim V$ distinct eigenvalues.


### 5.13 Notation
Suppose $T \in L(V)$ and $m$ is a positive integer.

- $T^m \in L(V)$ is defined by $T^m = T ... T$ ($m$ times).
- $T^0$ is defined to be the identity operator $I$ on $V$.
- If $T$ is invertible with inverse $T^{-1}$, then $T^{-m} \in L(V)$ is defined by

$$T^{-m} = (T^{-1})^m$$


### 5.14
Suppose $T \in L(V)$ and $p \in P(F)$ is a polynomial given by 

$$p(z) = a_0 + a_1 z + a_2 z^2 + ... + a_m z^m$$

for all $z \in F$. Then $p(T)$ is the operator on $V$ defined by

$$p(T) = a_0 I + a_1 T + a_2 T^2 + ... + a_m T^m$$


### 5.16 Definition: product of polynomials
If $p, q \in P(F)$, then $pq \in P(F)$ is the polynomial defined by

$$(pq)(z) = p(z) q(z)$$

for all $z \in F$.


### 5.17
Suppose $p, q \in P(F)$ and $T \in L(V)$. Then

- $(pq)(T) = p(T) q(T)$
- $p(T) q(T) = q(T) p(T)$


### 5.18
Suppose $T \in L(V)$ and $p \in P(F)$. Then $null p(T)$ and $range p(T)$ are invariant under $T$.


## Exercises





# 5B The Minimal Polynomial

### 5.19
Every operator on a finite-dimensional nonzero complex vector space has an eigenvalue.


### 5.21 Definition: monic polynomial
A monic polynomial is a polynomial whose highest-degree coefficient equals 1.


### 5.22
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then there is a unique monic polynomial $p \in P(F)$ of smallest degree such that $p(T) = 0$. Furthermore, $deg p \leq deg V$.


### 5.24 Definition: minimal polynomial
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then the minimal polynomial of $T$ is the unique monic polynomial $p \in P(F)$ of smallest degree such that $p(T) = 0$.


### 5.27
Suppose $V$ is finite-dimensional and $T \in L(V)$.

- The zeros of the minimal polynomial of $T$ are the eigenvalues of $T$.
- If $V$ is a complex vector space, then the minimal polynomial of $T$ has the form 

$$(z - \lambda_1) ... (z - \lambda_m) $$

where $\lambda_1, ..., \lambda_m$ is a list of all eigenvalues of $T$, possibly with repetitions.


### 5.29
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $q \in P(F)$. Then $q(T) = 0$ if and only if $q$ is a polynomial multiple of the minimal polynomial of $T$.


### 5.31
Suppose $V$ is finite-dimensional, $T \in L(V)$, and $U$ is a subspace of $V$ that is invariant under $V$. Then the minimal polynomial of $T$ is a polynomial multiple of the minimal polynomial of $T|_{U}$.


### 5.32
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ is not invertible if and only if the constant term of the minimal polynomial of $T$ is 0.


### 5.33
Suppose $F = R$ and $V$ is finite-dimensional. Suppose also that $T \in L(V)$ and $b, c \in R$ with $b^2 < 4c$. Then $dim null (T^2 + bT + cI)$ is an even number.


### 5.34
Every operator on an odd-dimensional vector space has an eigenvalue.


## Exercises





# 5C Upper-Triangular Matrices

### 5.39
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Then the following are equivalent.

- The matrix of $T$ with respect to $v_1,...,v_n$ is upper triangular. 
- $span (v_1,...,v_k)$ is invariant under $T$ for each $k = 1,...,n$.
- $Tv_k \in span (v_1,...,v_k)$ for each $k = 1,...,n$


### 5.40
Suppose $T \in L(V)$ and $V$ has a basis with respect to which $T$ has an upper triangular matrix with diagonal entries $\lambda_1,...,\lambda_n$. Then

$$(T - \lambda_1 I) ... (T - \lambda_n I) = 0$$


# 5D Diagonalizable Operators



# 5E Commuting Operators



