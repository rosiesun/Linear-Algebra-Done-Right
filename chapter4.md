Linear Algebra Done Right - Chapter 4 <br>
Polynomials
================
Rosie Sun <br>
2026-04-19


### 4.5 Definition: zero of a polynomial
A number $\lambda \in F$ is called a zero (or root) of a polynomial $p \in P(F)$ if 

$$p(\lambda)=0$$.


### 4.6
Suppose $m$ is a positive integer and $p \in P(F)$ is a polynomial of degree $m$. Suppose $\lambda \in F$. Then $p(\lambda)=0$ if and only if there exists a polynomial $q \in P(F)$ of degree $m-1$ such that 

$$p(z) = (z - \lambda) q(z)$$

for every $z \in F$.


### 4.8
Suppose $m$ is a positive integer and $p \in P(F)$ is a polynomial of degree $m$. Then $p$ has at most $m$ zeros in $F$.


### 4.9
Suppose that $p, s \in P(F)$, with $s \neq 0$. Then there exist unique polynomials $q, r \in P(F)$ such that 

$$p = sq + r$$

and $deg r < deg s$.


### 4.12
Every nonconstant polynomial with complex coefficients has a zero in $C$.


### 4.13
If $p \in P(C)$ is a nonconstant polynomial, then $p$ has a unique factorization of the form 

$$p(z) = c(z - \lambda_1) ... (z - \lambda_m)$$

where $c, \lambda_1,...,\lambda_m \in C$.


### 4.14
Suppose $p \in P(C)$ is a polynomial with real coefficients. If $\lambda \in C$ is a zero of $p$, then so is $\bar{\lambda}$.


### 4.15
Suppose $b, c \in R$. Then there is a polynomial factorization of the form 

$$x^2 + bx + c = (x - \lambda_1) (x - \lambda_2)$$

with $\lambda_1, \lambda_2 \in R$ if and only if $b^2 \geq 4c$.


### 4.16
Suppose $p \in P(R)$ is a nonconstant polynomial. Then $p$ has a unique factorization (except for the order of the factors) of the form

$$p(x) = c(x - \lambda_1) ... (x - \lambda_m) (x^2 + b_1 x + c_1) ... (x^2 + b_M x + c_M)$$

where $c, \lambda_1, ..., \lambda_m, b_1,...,b_M, c_1,...,c_M \in R$, with $b_k^2 < 4c_k$ for each $k$.
