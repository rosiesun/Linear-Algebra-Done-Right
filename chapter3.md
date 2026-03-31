Linear Algebra Done Right - Chapter 3
================
Rosie Sun <br>
2026-04-03

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

### 3.6 $L(V,W) is a vector space$
With the operations of addition and scalar multiplication as defined above, $L(V,W)$ is a vector space.

### 3.7 Definition: product of linear maps
If $T \in L(U,V)$ and $S \in L(V,W)$ then the product $ST \in L(U,W)$ is defined by $(ST)(u) = S(Tu)$ for all $u \in U$.

### 3.8 Algebraic properties of products of linear maps
Associativity: $(T_1 T_2)T_3 = T_1 (T_2 T_3)$ whenever $T_1, T_2, T_3$ are linear maps such that the products make sense (meaning $T_3$ maps into the domain of $T_2$ and $T_2$ maps into the domain of $T_1$).

Identity: $TI = IT = T$ whenever $T \in L(V,W)$; here the first $I$ is the identity operator on $V$ and the second $I$ is the identity operator on $W$.

Distributive properties: $(S_1 + S_2) T = S_1 T + S_2 T$ and $S(T_1 + T_2) = ST_1 + ST_2$ whenever $T, T_1, T_2 \in L(U,V)$ and $S, S_1, S_2 \in L(V,W)$. 

### 3.10 Linear maps take 0 to 0
Suppose $T$ is a linear map from $V$ to $W$. Then $T(0)=0$.








# 3B Null Spaces and Ranges








# 3C Matrices






# 3D Invertibility and Isomorphisms







# 3E Products and Quotients of Vector Spaces







# 3F Duality





