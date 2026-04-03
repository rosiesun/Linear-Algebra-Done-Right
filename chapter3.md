Linear Algebra Done Right - Chapter 3
================
Rosie Sun <br>
2026-04-02

# 3A Vector Space of Linear Maps

### 3.1 Definition: linear map
A linear map from $V$ to $W$ is a function $T:V \rightarrow W$ with the following properties. 

Additivity: $T(u+v) = Tu+Tv$ for all $u,v \in V$.

Homogeneity: $T(\lambda v) = \lambda (Tv)$ for all $\lambda in F$ and all $v \in V$.

### 3.2 Notation
- The set of linear maps from $V$ to $W$ is denoted by $L(V,W)$.
- THe set of linear maps from $V$ to $V$ is denoted by $L(V)$. In other words, $L(V,V)=L(V)$.

### 3.4 Linear map lemma
Suppose $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_n \in W$. Then there exists a unique linear map $T:V \rightarrow W$ such taht $T v_k = w_k$ for each $k = 1,...,n$.

### 3.5 Definition: addition and scalar multiplication on $L(V,W)$
Suppose $S, T \in L(V,W)$ and $\lambda \in F$. The sum $S+T$ and the product $\lambda T$ are the linear maps from $V$ to $W$ defined by $(S+T)(v) = Sv + Tv$ and $(\lambda T)(v) = \lambda (Tv)$ for all $v \in V$.

### 3.6 $L(V,W)$ is a vector space
With the operations of addition and scalar multiplication as defined above, $L(V,W)$ is a vector space.

### 3.7 Definition: product of linear maps
If $T \in L(U,V)$ and $S \in L(V,W)$ then the product $ST \in L(U,W)$ is defined by $(ST)(u) = S(Tu)$ for all $u \in U$.

### 3.8 Algebraic properties of products of linear maps
Associativity: $(T_1 T_2)T_3 = T_1 (T_2 T_3)$ whenever $T_1, T_2, T_3$ are linear maps such that the products make sense (meaning $T_3$ maps into the domain of $T_2$ and $T_2$ maps into the domain of $T_1$).

Identity: $TI = IT = T$ whenever $T \in L(V,W)$; here the first $I$ is the identity operator on $V$ and the second $I$ is the identity operator on $W$.

Distributive properties: $(S_1 + S_2) T = S_1 T + S_2 T$ and $S(T_1 + T_2) = ST_1 + ST_2$ whenever $T, T_1, T_2 \in L(U,V)$ and $S, S_1, S_2 \in L(V,W)$. 

### 3.10 Linear maps take 0 to 0
Suppose $T$ is a linear map from $V$ to $W$. Then $T(0)=0$.


## Exercises
#### (5) Prove that $L(V,W)$ is a vector space, as was asserted in 3.6.
Commutativity: Let $S,T \in L(V,W)$, let $v \in V$. 

$$(S+T)(v) = Sv + Tv = Tv + Sv = (T+S)(v)$$ 

by the fact that $W$ is a vector space. 

Associativity: Let $R, S, T \in L(V,W)$, let $v \in V$.

$$((R+S)+T)(v) = (R+S)(v) + Tv = Rv + Sv + Tv = Rv + (S+T)(v) = (R+(S+T))(v)$$

by the fact that $W$ is a vector space.

Additive identity: Defined in 3.3. There exists $0 \in L(V,W)$ where $0v=0$. Let $T \in L(V,W)$. Then

$$(T+0)(v) = Tv + 0(v) = Tv + 0 = Tv$$

Additive inverse: Let $T \in L(V,W)$. Define $(-T) \in L(V,W)$ such that $(-T)(v) = -Tv$. $(-T) \in L(V,W)$ since $(-T)(u+v) = -T(u+v) = (-Tu) + (-Tv) = (-T)(u) + (-T)(v)$, and $(-T)(av) = -T(av) = -aTv = a(-T)(v)$. Thus additivity and homogeneity are satisfied, so $(-T)$ is a linear map. Then 

$$(T+(-T))(v) = Tv + (-T)(v) = Tv + (-Tv) = 0$$

Multiplicative identity: Let $T \in L(V,W)$.

$$(1T)(v) = 1(Tv) = Tv$$

Distributive properties: Let $S, T \in L(V,W), a,b \in F$. Then 

$$(a(S+T))(v) = a((S+T)(v)) = a(Sv + Tv) = a(Sv) + a(Tv) = (aS)(v) + (aT)(v)$$

And 

$$((a+b)T)(v) = (a+b)(Tv) = a(Tv) + b(Tv) = (aT)(v) + (bT)(v)$$


#### (6) Prove that multiplication of linear maps has the associative, identity, and distributive properties asserted in 3.8.

Associativity: Let $T_3 \in L(U,V), T_2 \in L(V, W), T_1 \in L(W,Z)$. Then 

$$((T_1 T_2)T_3)(u) = (T_1 T_2)(T_3 u) = T_1 (T_2 (T_3 u))$$

and 

$$(T_1(T_2 T_3))(u) = T_1 ((T_2 T_3)(u)) = T_1 (T_2 (T_3 u))$$

Thus $(T_1 T_2) T_3 = T_1 (T_2 T_3)$.

Identity: Let $T \in L(V,W)$. 

$$(TI)(v) = T(Iv) = Tv$$

And

$$(IT)(v) = I(Tv) = Tv$$

Thus $TI = IT = T$.

Distributive properties: 

Let $T, T_1, T_2 \in L(U,V), S, S_1, S_2 \in L(V,W)$. Then 

$$(S(T_1+T_2))(u) = S((T_1+T_2)(u)) = S(T_1 u + T_2 u) = S(T_1 u) + S (T_2 u) = (S T_1)(u) + (S T_2)(u)$$

And

$$((S_1+S_2)T)(u) = (S_1+S_2)(Tu) = S_1(Tu) + S_2(Tu) = (S_1 T)(u) + (S_2 T)(u)$$


#### (11)



#### (13)






# 3B Null Spaces and Ranges

### 3.11 Definition: null space
For $T \in L(V,W)$, the null space of $T$, denoted by $null T$, is the subset of $V$ consisting of those vectors that $T$ maps to 0: $null T = \\{v \in V: Tv = 0\\}$.

### 3.13 The null space is a subspace
Suppose $T \in L(V,W)$. Then $null T$ is a subspace of $V$.

### 3.14 Definition: injective
A function $T:V \rightarrow W$ is called injective if $Tv = Tu$ implies $u=v$.

### 3.15
Let $T \in L(V,W)$. Then $T$ is injective if and only if $null T = \\{0\\}$. 

### 3.16 Definition: range
For $T \in L(V,W)$, the range of $T$ is the subset of $W$ consisting of those vectors that are equal to $Tv$ for some $v \in V$: $range T = \\{Tv: v \in V\\}$.

### 3.18 The range is a subspace
If $T \in L(V,W)$, then $range T$ is a subspace of $W$.

### 3.19 Definition: surjective
A function $T: V \rightarrow W$ is called surjective if its range equals $W$.

### 3.21 Fundamental theorem of linear maps
Suppose $V$ is finite-dimensional and $T \in L(V,W)$. Then $range T$ is finite-dimensional and $dim V = dim null T + dim range T$.

### 3.22 Linear map to a lower-dimensional space is not injective
Suppose $V$ and $W$ are finite-dimensional vector spaces such that $dim V > dim W$. Then no linear map from $V$ to $W$ is injective.

### 3.24 Linear map to a higher-dimensional space is not surjective
Suppose $V$ and $W$ are finite-dimensional vector spaces such that $dim V < dim W$. Then no linear map from $V$ to $W$ is surjective.

### 3.26 Homogeneous system of linear equations
A homogeneous system of linear equations with more variables than equations has nonzero solutions.

### 3.28 System of linear equations with more equations than variables
A system of linear equations with more equations than variables has no solution for some choice of the constant terms.






# 3C Matrices






# 3D Invertibility and Isomorphisms







# 3E Products and Quotients of Vector Spaces







# 3F Duality





