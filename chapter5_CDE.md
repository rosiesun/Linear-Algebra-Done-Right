Linear Algebra Done Right - Chapter 5 Eigenvalues and Eigenvectors <br>
Section C, D, E
================
Rosie Sun <br>
2026-04-21


# 5C Upper-Triangular Matrices

### 5.39
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Then the following are equivalent.

- The matrix of $T$ with respect to $v_1,...,v_n$ is upper triangular. 
- $span (v_1,...,v_k)$ is invariant under $T$ for each $k = 1,...,n$.
- $Tv_k \in span (v_1,...,v_k)$ for each $k = 1,...,n$

Proof:

First suppose (a) holds. To prove that (b) holds, suppose $k \in \\{1,..,n\\}$. 

If $j \in \\{1,...,n\\}$, then $Tv_j \in span(v_1,...,v_j)$ because the matrix of $T$ with respect to $v_1,...,v_n$ is upper triangular. 

Because $span(v_1,...,v_j) \subseteq span(v_1,...,v_k)$ if $j \leq k$, we see that $Tv_j \in span(v_1,...,v_k)$ for each $j \in \\{1,...,k\\}$. THus $span(v_1,...,v_k)$ is invariant under $T$, completing the proof that (a) implies (b).

Now suppose (b) holds, so $span(v_1,...,v_k)$ is invariant under $T$ for each $k=1,...,n$. In particular, $Tv_k \in span(v_1,...,v_k)$ for each $k=1,...,n$. Thus (b) implies (c).

Now suppose (c) holds, so $Tv_k \in span(v_1,...,v_k)$ for each $k=1,...,n$. This means that when writing each $Tv_k$ as a linear combination of the basis vectors $v_1,...,v_n$, we need to use only the vectors $v_1,...,v_k$. Hence all entries under the diagonal of $M(T)$ are 0. Thus $M(T)$ is an upper-triangular matrix, copmleting the proof (c) implies (a).

We have shown that (a) $\Rightarrow$ (b) $\Rightarrow$ (c) $\Rightarrow$ (a), which shows that (a), (b), and (c) are equivalent.


### 5.40
Suppose $T \in L(V)$ and $V$ has a basis with respect to which $T$ has an upper triangular matrix with diagonal entries $\lambda_1,...,\lambda_n$. Then

$$(T - \lambda_1 I) ... (T - \lambda_n I) = 0$$

Proof:

Let $v_1,...,v_n$ denote a basis of $V$ with respect to which $T$ has an upper-triangular matrix with diagonal entries $\lambda_1,...,\lambda_n$. Then $Tv_1 = \lambda_1 v_1$, which means that $(T - \lambda_1 I) v_1 = 0$, which implies that 

$$(T-\lambda_1 I) ... (T - \lambda_m I) v_1 = 0$$

for $m = 1,...,n$, using the commutativity of each $T - \lambda_j I$ with each $T - \lambda_k I$. 

Note that 

$$(T - \lambda_2 I) v_2 = Tv_2 - \lambda_2 v_2 = a_1 v_1 + \lambda_2 v_2 - \lambda_2 v_2 \in span(v_1)$$

Thus 

$$(T - \lambda_1 I) (T - \lambda_2 I) v_2 = 0$$

by the previous paragraph, which implies that 

$$(T - \lambda_1 I) ... (T - \lambda_m I) v_2 = 0$$

for $m=2,...,n$, using the commutativity of each $T - \lambda_j I$ with each $T - \lambda_k I$. 

Note that 

$$(T - \lambda_3 I) v_3 = T v_3 - \lambda_3 v_3 = a_1 v_1 + a_2 v_2 + \lambda_3 v_3 - \lambda_3 v_3 \in span(v_1, v_2)$$

Thus by the previous paragraph, 

$$(T-\lambda_1 I)(T-\lambda_2 I)(T-\lambda_3 I)v_3 = 0$$

which implies that 

$$(T-\lambda_1 I)... (T-\lambda_m I)v_3 = 0$$

for $m=3,...,n$, using the commutativity of each $T - \lambda_j I$ with each $T - \lambda_k I$. 

Continuing this pattern, we see that $(T-\lambda_1 I)...(T-\lambda_n I)v_k = 0$ for each $k=1,...,n$. Thus $(T-\lambda_1 I)...(T-\lambda_n I)$ is the 0 operator because it is 0 on each vector in a basis of $V$.


### 5.41
Suppose $T \in L(V)$ has an upper-triangular matrix with respect to some basis of $V$. Then the eigenvalues of $T$ are precisely the entries on the diagonal of that upper-triangular matrix.

Proof:

Suppose $v_1,...,v_n$ is a basis of $V$ with respect to which $T$ has an upper-triangular matrix. Because $Tv_1 = \lambda_1 v_1$, we see that $\lambda_1$ is an eigenvalue of $T$.

Suppose $k = \{{2,...,n\}}$. Then $(T-\lambda_k I) v_k \in span(v_1,...,v_{k-1})$. Thus $T-\lambda_k I$ maps $span(v_1,...,v_k)$ into $span(v_1,...,v_{k-1})$. 

Beacuse $dim span(v_1,...,v_k) = k$ and $dim span(v_1,...,v_{k-1}) = k-1$, this implies that $T-\lambda_k I$ restricted to $span(v_1,...,v_k)$ is not injective, by 3.22. Thus there exists $v \in span(v_1,...,v_k)$ such that $v \neq 0, (T-\lambda_k I)v=0$. Thus $\lambda_k$ is an eigenvalue of $T$. Hence we have shown that every entry on the diagonal of $M(T)$ is an eigenvalue of $T$.

To prove $T$ has no other eigenvalues, let $q$ be the polynomial defined by $q(z)=(z-\lambda_1)...(z-\lambda_n)$. Then $q(T)=0$ by 5.40. Hence $q$ is a polynomial multiple of the minimal polynomial of $T$, by 5.29. Thus every zero of the minimal polynomial of $T$ is a zero of $q$. Because the zeros of the minimal polynomial of $T$ are the eigenvalues of $T$, by 5.27, this implies that every eigenvalue of $T$ is a zero of $q$. Hence the eigenvalues of $T$ are all contained in the list $\lambda_1,...,\lambda_n$.


### 5.44
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$.

Proof:

$\Rightarrow$
First suppose $T$ has an upper-triangular matrix with respect to some basis of $V$. Let $\alpha_1,...,\alpha_n$ denote the diagonal entries of that matrix. 

Define a polynomial $q \in P(F)$ by $q(z) = (z-\alpha_1)...(z-\alpha_n)$. Then $q(T)=0$, by 5.40. Hence $q$ is a polynomial multiple of the minimal polynomial of $T$, by 5.29. Thus the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$ with $\\{\lambda_1,...,\lambda_m\\} \subseteq \\{\alpha_1,...,\alpha_n\\}$.

$\Leftarrow$
Suppose the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some $\lambda_1,...,\lambda_m \in F$. 

We will use induction on m.

To get started, if $m=1$, then $z-\lambda_1$ is the minimal polynomial of $T$, which implies that $T=\lambda_1 I$, which implies that the matrix of $T$ with respect to any basis of $V$ is upper triangular.

Now suppose $m > 1$, and the desired result holds for all smaller positive integers.

Let $U = range (T - \lambda_m I)$. Then $U$ is invariant under $T$ by 5.18. Thus $T|_U$ is an operator on $U$.

If $u \in U$, then $(T-\lambda_m I)v = u$ for some $v \in V$ and

$$(T-\lambda_1 I)...(T-\lambda_{m-1})u = (T-\lambda_1 I)...(T-\lambda_m I)v = 0$$

Hence $(z-\lambda_1)...(z-\lambda_{m-1})$ is a polynomial multiple of the minimal polynomial of $T|_U$, by 5.29. Thus the minimal polynomial of $T|_U$ is the product of at most $m-1$ terms of the form $z-\lambda_k$.

By our induction hypothesis, there is a basis $u_1,...,u_M$ of $U$ with respect to which $T|_U$ has an upper-triangular matrix.

Thus for each $k \in \\{1,...,M\\}$, we have, using 5.39,

$$Tu_k = (T|_U) u_k \in span (u_1,...,u_k)$$

Extend $u_1,...,u_M$ to a basis $u_1,...,u_M, v_1,...,v_N$ of $V$. 

If $k \in \\{1,...,N\\}$, then 

$$Tv_k = (T - \lambda_m I) v_k + \lambda_m v_k$$

The definition of $U$ shows that $(T-\lambda_m I)v_k \in U = span(u_1,...,u_M)$. Thus the equation above shows that 

$$Tv_k \in span(u_1,...,u_M,v_1,...,v_k)$$

We conclude, using 5.39, that $T$ has an upper-triangular matrix with respect to the basis $u_1,...,u_M, v_1,...,v_N$ of $V$.


### 5.47
Suppose $V$ is a finite-dimensional complex vector space and $T \in L(V)$. Then $T$ has an upper-triangular matrix with respect to some basis of $V$.

Proof:

The desired result follows from 5.44 and the second version of the fundamental theorem of algebra (4.13).




## Exercises

### (1) Prove or give a counterexample: If $T \in L(V)$ and $T^2$ has an upper-triangular matrix with respect to some basis of $V$, then $T$ has an upper-triangular matrix with respect to some basis of $V$.


### (2) Suppose $A$ and $B$ are upper-triangular matrices of the same size, with $\alpha_1, ..., \alpha_n$ on the diagonal of $A$ and $\beta_1, ..., \beta_n$ on the diagonal of $B$.

#### (a) Show that $A + B$ is an upper-triangular matrix with $\alpha_1 + \beta_1, ..., \alpha_n + \beta_n$ on the diagonal.

#### (b) Show that $AB$ is an upper-triangular matrix with $\alpha_1 \beta_1, ..., \alpha_n \beta_n$ on the diagonal.


### (3) 

### (4)

### (5)

### (6)

### (8)

### (9)





--------------------------------------------------------------------------------
# 5D Diagonalizable Operators

### 5.48 Definition: diagonal matrix
A diagonal matrix is a square matrix that is 0 everywhere except possibly on the diagonal.


### 5.50 Definition: diagonalizable
An operator on $V$ is called diagonalizable if the operator has a diagonal matrix with respect to some basis of $V$.


### 5.52 Definition: eigenspace
Suppose $T \in L(V)$ and $\lambda \in F$. The eigenspace of $T$ corresponding to $\lambda$ is the subspace $E(\lambda, T)$ of $V$ defined by

$$E(\lambda, T) = null (T - \lambda I) = \\{v \in V: Tv = \lambda v\\}$$

Hence $E(\lambda, T)$ is the set of all eigenvectors of $T$ corresponding to $\lambda$, along with the 0 vector.


### 5.54
Suppose $T \in L(V)$ and $\lambda_1,...,\lambda_m$ are distinct eigenvalues of $T$. Then 

$$E(\lambda_1, T) + ... + E(\lambda_m, T)$$

is a direct sum. Furthermore, if $V$ is finite-dimensional, then 

$$dim E(\lambda_1, T) + ... + dim E (\lambda_m, T) \leq dim V$$.

Proof:

To show that $E(\lambda_1, T) + ... + E(\lambda_m, T)$ is a direct sum, suppose $v_1 + ... + v_m = 0$, where each $v_k$ is in $E(\lambda_k, T)$. Because eigenvectors corresponding to distinct eigenvalues are linearly independent, by 5.11, this implies that each $v_k$ equals 0. Thus $E(\lambda_1, T) + ... + E(\lambda_m, T)$ is a direct sum by 1.45, as desired.

Now suppose $V$ is finite-dimensional. Then 

$$dim E(\lambda_1, T) + ... + dim E(\lambda_m, T) = dim (E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)) \leq dim V$$

where the first line follows from 3.94 and the second line follows from 2.37.


### 5.55
Suppose $V$ is finite-dimensional and $T \in L(V)$. Let $\lambda_1,...,\lambda_m$ denote the distinct eigenvalues of $T$. Then the following are equivalent:

(a) $T$ is diagonalizable.
(b) $V$ has a basis consisting of eigenvectors of $T$.
(c) $V = E(\lambda_1,T) \oplus ... \oplus E(\lambda_m, T)$
(d) $dim V = dim E(\lambda_1, T) + ... + dim E(\lambda_m, T)$.

Proof:

An operator $T \in L(V)$ has a diagonal matrix with respect to a basis $v_1,...,v_n$ of $V$ if and only if $Tv_k = \lambda_k v_k$ for each $k$. Thus (a) and (b) are equivalent.

Suppose (b) holds; thus $V$ has a basis consisting of eigenvectors of $T$. Hence every vector in $V$ is a linear combination of eigenvectors of $T$, which implies that $V = E(\lambda_1, T) + ... + E(\lambda_m, T)$. 5.54 shows that (c) holds, proving that (b) implies (c).

That (c) implies (d) follows immediately from 3.94.

Suppose (d) holds; thus $dim V = dim E(\lambda_1, T) + ... + E(\lambda_m, T)$. Choose a basis of each $E(\lambda_k, T)$; put all these bases together to form a list $v_1,...,v_n$ of eigenvectors of $T$, where $dim V = n$.

To show that this list is linearly independent, suppose $a_1 v_1 + ... + a_n v_n = 0$, where $a_1,...,a_n \in F$. 

For each $k = 1,...,m$, let $u_k$ denote the sum of all the terms $a_j v_j$ such that $v_j \in E(\lambda_k, T)$. Thus each $u_k$ is in $E(\lambda_k, T)$, and $u_1+...+u_m=0$. 

Because eigenvectors corresponding to distinct eigenvalues are linearly independent (5.11), this implies that each $u_k$ equals 0. 

Because each $u_k$ is a sum of terms $a_j v_j$ where the $v_j$'s were chosen to be a basis of $E(\lambda_k, T)$, this implies that all $a_j$'s equal 0. Thus $v_1,...,v_n$ is linearly independent and hence is a basis of $V$ by 2.38. 

Thus (d) implies (b), completing the proof.


### 5.58
Suppose $V$ is finite-dimensional and $T \in L(V)$ has $dim V$ distinct eigenvalues. Then $T$ is diagonalizable.

Proof:

Suppose $T$ has distinct eigenvalues $\lambda_1,...,\lambda_{dim V}$. For each $k$, let $v_k \in V$ be an eigenvector corresponding to the eigenvalue $\lambda_k$. Because eigenvectors corresponding to distinct eigenvalues are linearly independent (5.11), $v_1,...,v_{dim V}$ is linearly independent.

A linearly independent list of $dim V$ vectors in $V$ is a basis of $V$ (2.38); thus $v_1,...,v_{dim V}$ is a basis of $V$. With respect to this basis consisting of eigenvectors, $T$ has a diagonal matrix.


### 5.62
Suppose $V$ is finite-dimensional and $T \in L(V)$. Then $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m \in F$.

$\Rightarrow$
Suppose $T$ has diagonalizable. Thus there is a basis $v_1,...,v_n$ of $V$ consisting of eigenvectors of $T$.

Let $\lambda_1,...,\lambda_m$ be the distinct eigenvalues of $T$. Then for each $v_j$, there exists $\lambda_k$ with $(T-\lambda_k I) v_j = 0$. Thus 

$$(T-\lambda_1 I)...(T-\lambda_m I) v_j = 0$$

which implies that the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$.

$\Leftarrow$
Suppose the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m \in F$. Thus

$$(T-\lambda_1 I)...(T-\lambda_m I)=0$$

We will prove that $T$ is diagonalizable by induction on $m$.

To get started, suppose $m=1$. Then $T-\lambda_1 I = 0$, which means that $T$ is a scalar multiple of the identity operator, which implies that $T$ is diagonalizable.

Now suppose $m>1$ and the desired result holds for all smaller values of $m$.

The subspace $range (T-\lambda_m I)$ is invariant under $T$ (5.18). Thus $T$ restricted to $range (T-\lambda_m I)$ is an operator on $range (T-\lambda_m I)$.

If $u \in range(T-\lambda_m I)$, then $(T-\lambda_m I)v = u$ for some $v \in V$, and 

$$(T-\lambda_1 I)...(T-\lambda_{m-1} I)u = (T-\lambda_1 I)...(T-\lambda_m I)v = 0$$

Hence $(z-\lambda_1)...(z-\lambda_{m-1})$ is a polynomial multiple of the minimal polynomial of $T$ restricted to $range (T-\lambda_m I)$ by 5.29. 

Thus by our induction hypothesis, there is a basis of $range (T-\lambda_m I)$ consisting of eigenvectors of $T$.

Suppose $u \in range(T-\lambda_m I) \cap null (T-\lambda_m I)$. Then $Tu = \lambda_m u$. 

$$0 = (T-\lambda_1 I)...(T-\lambda_{m-1} I) u = (\lambda_m - \lambda_1)...(\lambda_m - \lambda_{m-1}) u$$

Because $\lambda_1,...,\lambda_m$ are distinct, the equation above implies that $u=0$. Hence $range (T-\lambda_m I) \cap null (T-\lambda_m I) = \\{0\\}$.

Thus $range (T-\lambda_m I) + null (T-\lambda_m I)$ is a direct sum by 1.46, whose dimension is $dim V$, by 3.94 and 3.21. Hence $range (T-\lambda_m I) \oplus null (T-\lambda_m I) = V$.

Every nonzero vector in $null (T-\lambda_m I)$ is an eigenvector of $T$ with eigenvalue $\lambda_m$.

Earlier in this proof we saw that there is a basis of $range (T-\lambda_m I)$ consisting of eigenvectors of $T$. Adjoining to that basis a basis of $null (T-\lambda_m I)$ gives a basis of $V$ consisting of eigenvectors of $T$. The matrix of $T$ with respect to this basis is a diagonal matrix, as desired.


### 5.65
Suppose $T \in L(V)$ is diagonalizable and $U$ is a subspace of $V$ that is invariant under $T$. Then $T|_U$ is a diagonalizable operator on $U$.


### 5.66 Definition: Gershgorin disks
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Let $A$ denote the matrix of $T$ with respect to this basis. A gershgorin disk of $T$ with respect to the basis $v_1,...,v_n$ is a set of the form 

$$\\{z \in F: |z-A_{j,j}| \leq \sum^n_{k=1, k \neq j} |A_jk| \\}$$

where $j \in \\{1,...,n\\}$.


### 5.67
Suppose $T \in L(V)$ and $v_1,...,v_n$ is a basis of $V$. Then each eigenvalue of $T$ is contained in some Gershgorin disk of $T$ with respect to the basis $v_1,...,v_n$.




## Exercises

### (1) Suppose $V$ is a finite-dimensional complex vector space and $T \in L(V)$.

#### (a) Prove that if $T^4 = I$, then $T$ is diagonalizable.

Suppose $T^4 = I$. Then we have $T^4 - I = 0$. 

Thus $p(z) = z^4 - 1$ is a polynomial multiple of the minimal polynomial of $T$ by 5.29. 

We can factor 

$$p(z) = (z + i) (z - i) (z + 1) (z - 1).$$

By 5.62, $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z - \lambda_1) ... (z - \lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m$. 

Since $p(z)$ is a polynomial multiple of the minimal polynomial, the minimal polynomial satisfies the condition of 5.62. 

Hence $T$ is diagonalizable. 


#### (b) Prove that if $T^4 = T$, then $T$ is diagonalizable.

Suppose $T^4 = T$. Then we have $T^4 - T = 0$. 

Thus $p(z) = z^4 - z$ is a polynomial multiple of the minimal polynomial of $T$ by 5.29. 

We can factor 

$$p(z) = (z - 0) (z - 1) (z- ( (-1+i \sqrt{3})/2)) (z- ( (-1-i \sqrt{3})/2)) .$$ 

By 5.62, $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z-\lambda_1)...(z-\lambda_m)$ for some list of distinct numbers $\lambda_1,...,\lambda_m$. 

Since $p(z)$ is a polynomial multiple of the minimal polynomial, the minimal polynomial satisfies the condition of 5.62. 

Hence $T$ is diagonalizable. 


#### (c) Give an example of an operator $T \in L(C^2)$ such that $T^4 = T^2$ and $T$ is not diagonalizable.

$$
\begin{pmatrix} 
0 & 1 \\ 
0 & 0 
\end{pmatrix}
$$

We verify that $T^4 = T^2 = 0$. 

0 is the only eigenvalue, and $E(0, T) = span(0,1)$. $dim E(0,T) < dim V = 2$. Hence $T$ is not diagonalizable by 5.55.



### (2) Suppose $T \in L(V)$ has a diagonal matrix $A$ with respect to some basis of $V$. Prove that if $\lambda \in F$, then $\lambda$ appears on the diagonal of $A$ precisely $dim E(\lambda, T)$ times.

Suppose $dim V = n$. Let $v_1,...,v_n$ be the basis with respect to which $T$ has a diagonal matrix. 

$Tv_i = \lambda_i v_i, i=1,...,n$, where $\lambda_i$'s are the diagonal entries of $A$.

Let $\lambda \in F$. Let $I_\lambda = \\{i: \lambda_i = \lambda \\}$ be the indices where $\lambda$ appears on the diagonal. Let $d$ be the number of times $\lambda$ appears.

We want to show that $\\{v_i: i \in I_\lambda \\}$ is a basis of $E(\lambda, T)$.

Since $Tv_i = \lambda v_i, i \in I_\lambda$, $v_i \in E(\lambda, T)$.

$v_i, i \in I_\lambda$'s are linearly independent because they are subset of the basis $v_1,...,v_n$.

Let $u \in E(\lambda, T)$. $u = a_1 v_1 + ... + a_n v_n$ for some $a_1,...,a_n$.

$(T-\lambda I) u = 0 = \sum_{i=1}^n a_i (\lambda_i - \lambda) v_i, i \notin I_\lambda$.

For $i \in I_\lambda$, $\lambda_i = \lambda$ so those terms disappear. 

For $i \notin I_\lambda$, $\lambda_i \neq \lambda$, which forces $a_i = 0$. 

So $u = \sum_{i \in I_\lambda} a_i v_i$. Therefore $v_i: i \in I_\lambda$ spans $E(\lambda, T)$.

Thus $\\{v_i: i \in I_\lambda \\}$ is a basis of $E(\lambda, T)$. 

$dim E(\lambda, T) = d$, and $\lambda$ appears on the diagonal $d$ times.



### (3) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that if the operator $T$ is diagonalizable, then $V = null T \oplus range T$.

Suppose $T \in L(V)$ is diagonalizable. We want to show that $V = null T \oplus range T$. 

First we will show that $null T + range T$ is a direct sum, and then we will show that it is equal to $V$.

Suppose $v_1, ..., v_n$ is a basis of $V$ with respect to which $T$ has a diagonal matrix. Let $\lambda_1, ..., \lambda_n$ be the corresponding eigenvalues. 

Suppose $u \in null T \cap range T$. Then $Tu = 0$ and $Tv = u$ for some $v \in V$. 

We can write $u = a_1 v_1 + ... + a_n v_n$ for some $a_1, ..., a_n \in F$, and $v = b_1 v_1 + ... + b_n v_n$ for some $b_1, ..., b_n \in F$. 

We have

$$
\begin{aligned}
Tu &= T(a_1 v_1 + ... + a_n v_n) \\
    &= a_1 Tv_1 + ... + a_n Tv_n \\
    &= a_1 \lambda_1 v_1 + ... a_n \lambda_n v_n \\
    &= 0
\end{aligned}
$$

Since $v_1, ..., v_n$ is a basis, $a_1 \lambda_1 = ... = a_n \lambda_n = 0$.

We also have

$$
\begin{aligned}
Tv &= T(b_1 v_1 + ... + b_n v_n) \\
    &= b_1 \lambda_1 v_1 + ... b_n \lambda_n v_n \\
    &= u \\
    &= a_1 v_1 + ... a_n v_n
\end{aligned}
$$

Since $v_1, ..., v_n$ is abasis, $b_i \lambda_i = a_i, i = 1, ..., n$.

Assume towards contradiction that $a_i \neq 0$ for some $i \in \\{1,...,n\\}$. 

Since $a_i \lambda_i = 0$, $\lambda_i = 0$. Then $b_i \lambda_i = 0$. But $b_i \lambda_i = a_i \neq 0$, which is a contradiction.

Therefore we conclude $a_1 = ... = a_n = 0$, so $u = 0$. 

Thus $null T \cap range T = \\{0\\}$. By 1.46, $null T + range T$ is a direct sum. 

We have

$$dim (null T \oplus range T) = dim null T + dim range T = dim V$$ 

where the first equality follows from 3.94 and the second equality follows from the fundamental theorem of linear maps (3.21).

Hence $V = null T \oplus range T$ by 2.39.



### (4) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that the following are equivalent. (a) $V = null T \oplus range T$. (b) $V = null T + range T$. (c) $null T \cap range T = \\{0\\}$.

If (a) holds, then (c) holds from 1.46.

Suppose (c) holds. We have 

$$
\begin{aligned}
dim (null T + range T) 
    &= dim null T + dim range T - dim (null T \cap range T) \\
    &= dim null T + dim range T - 0 \\
    &= dim V
\end{aligned}
$$

Therefore $null T + range T = V$ by 2.39, and (b) holds.

Suppose (b) holds. Since $V = null T + range T$, 

$$
\begin{aligned}
dim V &= dim (null T + range T) \\
    &= dim null T + dim range T - dim (null T \cap range T) \\
    &= dim V - dim (null T \cap range T)
\end{aligned}
$$

Therefore $dim (null T \cap range T) = 0$, and (c) holds. (b) and (c) together implies that (a) holds.



### (5) Suppose $V$ is a finite-dimensional complex vector space and $T \in L(V)$. Prove that $T$ is diagonalizable if and only if $V = null (T-\lambda I) \oplus range (T-\lambda I)$ for every $\lambda \in C$.

$\Rightarrow$
Suppose $T$ is diagonalizable. 

By 5.55, $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$ for some distinct eigenvalues $\lambda_1, ..., \lambda_m$.

Let $\lambda \in C$.

Case 1: $\lambda$ is not an eigenvalue. 

Then $T - \lambda I$ is invertible by 5.7. Thus $T$ is injective and surjective by 3.63. We have $range (T - \lambda I) = V$ and $null (T-\lambda I) = \\{0\\}$. 

Therefore 

$$V = null (T-\lambda I) \oplus range (T-\lambda I).$$

Case 2: $\lambda$ is an eigenvalue.

Suppose $\lambda = \lambda_i$ for some $i \in \\{1, ..., m\\}$. Then $null (T - \lambda I) = E(\lambda_i, T)$. 

Let $w \in range (T - \lambda I)$. Then $w = (T - \lambda I) v$ for some $v \in V$. 

Since $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$, we can write $v = e_1 + ... + e_m$, where $e_k \in E(\lambda_k,T), k = 1, ..., m$. 

$$
\begin{aligned}
w &= (T - \lambda I) v \\
    &= (T - \lambda I)(e_1 + ... + e_m) \\
    &= (T - \lambda I) e_1 + ... + (T - \lambda I) e_m \\
    &= (\lambda_1 e_1 - \lambda e_1) + ... + (\lambda_m e_m - \lambda e_m) \\
    &= \sum_{k=1}^m (\lambda_k - \lambda) e_k \\
    &= sum_{k \neq i} (\lambda_k - \lambda) e_k
\end{aligned}
$$

Therefore $w$ can be written as a sum of all the other eigenspaces except $E(\lambda_i, T)$, and

$$range (T-\lambda I) \subseteq E(\lambda_1, T) \oplus ... \oplus E(\lambda_{i-1}, T) \oplus E(\lambda_{i+1}, T) \oplus ... \oplus E(\lambda_m, T) .$$

Note that 

$$
\begin{aligned}
dim range (T-\lambda I) 
    &= dim V - dim null (T - \lambda I) \\
    &= dim V - dim E(\lambda, T) \\
    &= dim E(\lambda_1, T) \oplus ... \oplus E(\lambda_{i-1}, T) \oplus E(\lambda_{i+1}, T) \oplus ... \oplus E(\lambda_m, T)
\end{aligned}
$$

Hence we have

$$range (T-\lambda I) = E(\lambda_1,T) \oplus ... \oplus E(\lambda_{i-1}, T) \oplus E(\lambda_{i+1}, T) \oplus ... \oplus E(\lambda_m, T)$$

Putting everything together, we conclude

$$
\begin{aligned}
V &= E (\lambda_i, T) \oplus range (T - \lambda I) \\
    &= null (T - \lambda_i I) \oplus range (T - \lambda I) \\
    &= null (T - \lambda I) \oplus range (T - \lambda I)
\end{aligned}
$$

$\Leftarrow$
Suppose $V = null (T-\lambda I) \oplus range (T-\lambda I)$ for every $\lambda \in C$. 

We want to show that $T$ is diagonalizable. We use induction on $dim V$.

Base case: $dim V = 1$. Every vector in $V$ is an eigenvector, so $T$ is trivially diagonalizable.

Inductive step: suppose $dim V > 1$ and the desired result holds for all vector spaces of smaller dimension.

Note that $T$ has at least one eigenvalue by 5.19. Let $\lambda$ be an eigenvalue of $T$.

Let $U = range (T - \lambda I)$. Note that $U$ is invariant under $T$ by 5.18.

We want to show that for every $\mu \in C$, 

$$U = null (T|_U - \mu I) \oplus range (T|_U - \mu I).$$

By hypothesis, we have

$$V = null (T - \mu I) \oplus range (T - \mu I)$$

Note that 

$$null (T|_U - \mu I) = null (T - \mu I) \cap U$$

and

$$range (T|_U - \mu I) = (T - \mu I) (U) \subseteq range (T - \mu I).$$

We can see that 

$$null (T|_U - \mu I) \cap range (T|_U - \mu I) = \\{0\\} .$$

By the fundamental theorem of linear maps (3.21),

$$dim U = dim null (T|_U - \mu I) + dim range (T|_U - \mu I).$$

Thus 

$$U = null (T|_U - \mu I) \oplus range (T|_U - \mu I).$$

Since $dim U < dim V$ and $U$ satisfies the condition in the hypothesis, $T|_U$ is diagonalizable. 

By hypothesis we have

$$V = null (T - \lambda I) \oplus range (T - \lambda I) = E(\lambda, T) \oplus U.$$

Adding the eigenvector in $E(\lambda, T)$ to the eigenbasis in $U$ gives us a basis of $V$ which are the eigenvectors of $T$. Hence $T$ is diagonalizable.



### (6) Suppose $T \in L(F^5)$ and $dim E(8,T) = 4$. Prove that $T-2I$ or $T-6I$ is invertible.

Assume towards contradiction that both $T-2I$ and $T-6I$ are not invertible. 

Then $T-2I$ and $T-6I$ are not injective, by 3.65. $null (T-2I) \neq \\{0\\}, null (T-6I) \neq \\{0\\}$. There exists some $u, w \in V$ such that $(T-2I)u = 0$ and $(T-6I)w = 0$. Therefore $u$ is an eigenvector corresponding to eigenvalue 2, and $w$ is an eigenvector corresponding to eigenvalue 6. 

$$dim E(2,T) + dim E(6,T) + dim E(8,T) = \leq dim V = 5$$

by 5.54 and

$$dim E(2,T) + dim E(6,T) + dim E(8,T) \geq 1 + 1 + 4 = 6$$

which is a contradiction. Thus we conclude $T-2I$ or $T-6I$ is invertible.



### (8)

### (13)


### (16) Suppose that $T \in L(V)$ is diagonalizable. Let $\lambda_1, ..., \lambda_m$ denote the distinct eigenvalues of $T$. Prove that a subspace $U$ of $V$ is invariant under $T$ if and only if there exist subspaces $U_1, ..., U_m$ of $V$ such that $U_k \subseteq E(\lambda_k, T)$ for each $k$ and $U = U_1 \oplus ... \oplus U_m$.

$\Leftarrow$
Suppose there exist subspaces $U_1, ..., U_m$ of $V$ such that $U_k \subseteq E(\lambda_k, T)$ for each $k$ and $U = U_1 \oplus ... \oplus U_m$.

Suppose $u \in U$. Then $u = u_1 + ... + u_m \in U_1 \oplus ... \oplus U_m$. 

$$
\begin{aligned}
Tu &= T(u_1 + ... + u_m) \\
    &= Tu_1 + ... + Tu_m \\
    &= \lambda_1 u_1 + ... + \lambda_m u_m \\
    &\in U_1 \oplus ... \oplus U_m \\
    &= U
\end{aligned}    
$$

where the third equality follows because $u_k \in U_k \subseteq E(\lambda_k, T)$ is an eigenvector.

Hence $U$ is invariant under $T$.

$\Rightarrow$
Suppose $U$ is invariant under $T$.

Define $U_k = U \cap E(\lambda_k, T)$ for $k = 1, ..., m$. The intersection of two subspaces is a subspace.

By 5.11 eigenvectors corresponding to distinct eigenvalues are linearly independent, thus $U_1 + ... + U_m$ is a direct sum. 

By construction, $U_k \subseteq U$, thus $U_1 \oplus ... \oplus U_m \subseteq U$. 

Now we want to show that $U \subseteq U_1 \oplus ... \oplus U_m$.

Suppose $u \in U$. Since $T$ is diagonalizable, $V = E(\lambda_1, T) \oplus ... \oplus E(\lambda_m, T)$ by 5.55. We can write 

$$u = u_1 + ... + u_m$$

where

$$u_k \in E(\lambda_k, T), k = 1, ..., m.$$

For each $k = 1, ..., m$, define a polynomial 

$$p_k(z) = \frac{q_k(z)}{s_k}$$

where 

$$q_k(z) = \prod_{j \neq k} (z - \lambda_j) $$

and

$$s_k = \prod_{j \neq k} (\lambda_k - \lambda_j) .$$

Since $\lambda_1, ..., \lambda_k$ are distinct eigenvalues, $s_k \neq 0$.

By 5.17, the order does not matter in taking products of polynomials of a single operator. Since $u_k \in E(\lambda_k, T)$, $(T - \lambda_k) u_k = 0$. Thus $q_k(T)$ is used to eliminate the $u_j$ terms where $j \neq k$.

$$
\begin{aligned}
q_k(T) u 
    &= q_k(T) (u_1 + ... + u_m) \\
    &= q_k(T) u_1 + ... + q_k(T) u_m \\
    &= \sum_{k=1}^m \prod_{j \neq k} (T - \lambda_j) u_k \\
    &= \prod_{j \neq k} (T - \lambda_j) u_k
    &= q_k(T) u_k
\end{aligned}
$$

Once we isolate $u_k$, we see that 

$$q_k(T) u_k = \prod_{j \neq k} (T - \lambda_j) v_k = \prod_{j \neq k} (\lambda_k - \lambda_j) u_k$$

thus the definition of $q_k(z)$ and $s_k$ make sense and

$$p_k(T) u = u_k.$$

Since $U$ is invariant, $Tu \in U$. We claim that $U$ is invariant under $p(T)$ for any polynomial $p$. Note that $U$ is invariant under powers of $T$ ($T^a$ for positive interger $a$). Since $U$ is a subspace, it is closed under addition and scalar multiplication. Thus 

$$u_k = p_k(T) u \in U.$$ 

Since $u_k \in E(\lambda_k, T)$ and $u_k \in U$, 

$$u_k \in U \cap E(\lambda_k, T) = U_k.$$

Hence we have written $u = u_1 + ... + u_m$ where $u_k \in U_k$, $k = 1, ..., m$. 

We have $U \subseteq U_1 \oplus ... \oplus U_m$, and we conclude 

$$U = U_1 \oplus ... \oplus U_m$$

where $U_k \subseteq E(\lambda_k, T)$.


### (17)

### (20)

### (22)




--------------------------------------------------------------------------------
# 5E Commuting Operators



### 5.74


### 5.75


### 5.76


### 5.78


### 5.80


### 5.81


