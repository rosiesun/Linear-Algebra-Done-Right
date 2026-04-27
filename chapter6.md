Linear Algebra Done Right - Chapter 6 <br>
Inner Product Spaces
================
Rosie Sun <br>
2026-05-15


# 6A Inner Products and Norms

### 6.1 Definition: dot product
For $x, y \in R^n$, the dot product of $x$ and $y$, denoted by $x \dot y$, is defined by 

$$x \dot y = x_1 y_1 + ... + x_n y_n$$

where $x = (x_1,...,x_n)$ and $y = (y_1, ..., y_n)$.

### 6.2 Definition: inner product
An inner product on $V$ is a function that takes each ordered pair $(u,v)$ of elements of $V$ to a number $<u,v> \in F$ and has the following properties:

- positivity: $<v,v> \geq 0$ for all $v \in V$.
- definiteness: $<v,v>=0$ if and only if $v=0$.
- additivity in the first slot: $<u+v,w> = <u,w> + <v,w>$ for all $u,v,w \in V$.
- homogeneity in first slot: $<\lambda u, v> = \lambda <u,v>$ for all $\lambda in F$ and all $u,v \in V$.
- conjugate symmetry: $<u,v> = \overline{<v,u>}$ for all $u,v \in V$.

### 6.4 Definition: inner product space
An inner product space is a vector space $V$ along with an inner product on $V$.

### 6.6
- 



# 6B Orthonormal Bases

### 6.30
Suppose $e_1,...,e_n$ is an orthonormal basis of $V$ and $u,v \in V$. Then

- $v = <v, e_1>e_1 + ... <v,e_n>e_n$
- $||v||^2 = |<v,e_1>|^2 + ... + |<v,e_n>|^2$
- $<u,v> = <u,e_1>\overline{<v,e_1>} + ... + <u,e_n>\overline{<v,e_n>}$

### 6.35
Every finite-dimensional inner product space has an orthonormal basis.

### 6.36
Suppose $V$ is finite-dimensional. Then every orthonormal list of vectors in $V$ can be extended to an orthonormal basis of $V$.

### 6.37
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some orthonormal basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$.

### 6.38 Schur's theorem
Every operator on a finite-dimensional complex inner product space has an upper-triangular matrix with respect to some orthonormal basis.

### 6.42 Riesz representation theorem
Suppose $V$ is finite-dimensional and $\phi$ is a linear functional on $V$. Then there is a unique vector $v \in V$ such that 

$$\phi(u) = <u, v>$$

for every $u \in V$.



# 6C Orthogonal Complements and Minimization Problems

### 6.46 Definition: orthogonal complement
If $U$ is a subset of $V$, then the orthogonal complement of $U$, denoted by $U^{\perp}$, is the set of all vectors in $V$ that are orthogonal to every vector in $U$:

$$U^{\perp} = \\{v \in V: <u,v>=0 for every u \in U\\}$$


