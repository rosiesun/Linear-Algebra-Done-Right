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

#### (1) Suppose $T \in L(V)$ and $U$ is a subspace of $V$. 
(a) Prove that if $U \subseteq null T$, then $U$ is invariant under $T$.

(b) Prove that if $range T \subseteq U$, thten $U$ is invariant under $T$.


#### (2) Suppose that $T \in L(V)$ and $V_1,...,V_m$ are subspaces of $V$ invariant under $T$. Prove that $V_1 + ... + V_m$ is invariant under $T$.


#### (4) Prove or give a counterexample: If $V$ is finite-dimensional and $U$ is a subspace of $V$ that is invariant under every operator on $V$, then $U=\\{0\\}$ or $U=V$.


#### (5) Suppose $T \in L(R^2)$ is defined by $T(x,y) = (-3y, x)$. Find the eigenvalues of $T$.


#### (6) Define $T \in L(F^2)$ by $T(w,z) = (z,w)$. Find all eigenvalues and eigenvectors of $T$.


#### (7) Define $T \in L(F^3)$ by $T(z_1,z_2,z_3) = (2z_2, 0, 5z_3)$. Find all eigenvalues and eigenvectors of $T$.


#### (8) Suppose $P \in L(V)$ is such that $P^2 = P$. Prove that if $\lambda$ is an eigenvalue of $P$, then $\lambda = 0$ or $\lambda = 1$.


#### (12) Suppose $V = U \oplus W$, where $U$ and $W$ are nonzero subspaces of $V$. Define $P \in L(V)$ by $P(u+w) = u$ for each $u \in U, w \in W$. Find all eigenvalues and eigenvectors of $P$.

#### (13) Suppose $T \in L(V)$. Suppose $S \in L(V)$ is invertible.
(a) Prove that $T$ and $S^{-1} T S$ have the same eigenvalues.

(b) What is the relationship between the eigenvalues of $T$ and the eigenvalues of $S^{-1} T S$?


#### (14) Give an example of an operator on $R^4$ that has no real eigenvalues.


#### (21) Suppose $T \in L(V)$ is invertible.
(a) Suppose $\lambda \in F$ with $\lambda \neq 0$. Prove that $\lambda$ is an eigenvalue of $T$ if and only if $1/\lambda$ is an eigenvalue of $T^{-1}$.

(b) Prove that $T$ and $T^{-1}$ have the same eigenvectors.


#### (26) Suppose $T \in L(V)$ is such that every nonzero vector in $V$ is an eigenvector of $T$. Prove that $T$ is a scalar multiple of the identity operator.


#### (27) Suppose that $V$ is finite-dimensional and $k \in \\{1,...,dimV - 1\\}$. Suppose $T \in L(V)$ is such that every subspace of $V$ of dimension $k$ is invariant under $T$. Prove that $T$ is a scalar multiple of the identity operator.


#### (31) Give an example of $T \in L(R^2)$ such that $T^4 = -I$.


#### (34) Suppose $V$ is finite-dimensional and $v_1,...,v_m \in V$. Prove that the list $v_1,...,v_m$ is linearly independent if and only if there exists $T \in L(V)$ such that $v_1,...,v_m$ are eigenvectors of $T$ corresponding to distinct eigenvalues.


#### (36) Suppose that $\lambda_1,...,\lambda_n$ is a list of distinct positive numbers. Prove that the list $cos(\lambda_1 x), ..., cos(\lambda_n x)$ is linearly independent in the vector space of real-valued functions on $R$.







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



