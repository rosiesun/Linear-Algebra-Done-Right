Linear Algebra Done Right - Chapter 3 Linear Maps <br>
3A Vector Space of Linear Maps
================
Rosie Sun <br>
2026-04-02


### 3.1 Definition: linear map
A linear map from $V$ to $W$ is a function $T:V \rightarrow W$ with the following properties. 

Additivity: $T(u+v) = Tu+Tv$ for all $u,v \in V$.

Homogeneity: $T(\lambda v) = \lambda (Tv)$ for all $\lambda in F$ and all $v \in V$.


### 3.2 Notation
- The set of linear maps from $V$ to $W$ is denoted by $L(V,W)$.
- THe set of linear maps from $V$ to $V$ is denoted by $L(V)$. In other words, $L(V,V)=L(V)$.


### 3.4 Linear map lemma
Suppose $v_1,...,v_n$ is a basis of $V$ and $w_1,...,w_n \in W$. Then there exists a unique linear map $T:V \rightarrow W$ such taht $T v_k = w_k$ for each $k = 1,...,n$.

Proof:

First we show the existence of a linear map $T$ with the desired property. Define $T: V \rightarrow W$ by

$$T(c_1 v_1 + ... + c_n v_n) = c_1 w_1 + ... + c_n w_n$$

where $c_1,...,c_n$ are arbitrary elements of $F$. The list $v_1,...,v_n$ is a basis of $V$. Thus the equation above does indeed define a function $T$ from $V$ to $W$ (because each element of $V$ can be uniquely written in the form $c_1 v_1 + ... + c_n v_n$). 

For each $k$, taking $c_k=1$ and the other $c$'s equal to 0 in the equation above shows that $Tv_k = w_k$.

If $u,v \in V$ with $u=a_1 v_1 + ... + a_n v_n, v=c_1 v_1 + ... + c_n v_n$, then 

$$T(u+v) = T((a_1 + c_1) v_1 + ... (a_n + c_n) v_n) = (a_1 + c_1) w_1 + ... + (a_n + c_n) w_n = (a_1 w_1 + ... + a_n w_n) + (c_1 w_1 + ... + c_n w_n) = Tu + Tv$$

Similarly, if $\lambda \in F$ and $v = c_1 v_1 + ... + c_n v_n$, then 

$$T(\lambda v) = T(\lambda c_1 v_1 + ... + \lambda c_n v_n) = \lambda c_1 w_1 + ... + \lambda c_n w_n = \lambda (c_1 w_1 + ... + c_n w_n) = \lambda Tv$$

Thus $T$ is a linear map from $V$ to $W$.

To prove uniqueness, now suppose that $T \in L(V,W)$ and that $Tv_k = w_k$ for each $k=1,...,n$. Let $c_1,...,c_n \in F$. Then the homogeneity of $T$ implies that $T(c_k v_k) = c_k w_k$ for each $k=1,...,n$. The additivity of $T$ now implies that 

$$T(c_1 v_1 + ... + c_n v_n) = c_1 w_1 + ... + c_n w_n$$

Thus $T$ is uniquely determined on $span(v_1,...,v_n)$ by the equation above. Because $v_1,...,v_n$ is a basis of $V$, this implies that $T$ is uniquely determined on $V$, as desired.


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

Proof:

By additivity, we have

$$T(0) = T(0+0) = T(0) + T(0)$$

Add the additive inverse of $T(0)$ to each side of the equation above to conclude that $T(0) = 0$.




## Exercises

### (4) Suppose $T \in L(V,W)$ and $v_1,...,v_m$ is a list of vectors in $V$ such that $Tv_1,...,Tv_m$ is a linearly independent list in $W$. Prove that $v_1,...,v_m$ is linearly independent.
Let $a_1 v_1 + ... + a_m v_m = 0$.

Applying $T$,

$$T(a_1 v_1 + ... + a_m v_m) = T0 = 0$$

By linearity, 

$$a_1 Tv_1 + ... + a_m Tv_m = 0$$

Since $Tv_1,...,Tv_m$ is linearly independent, $a_1 = ... = a_m = 0$. Therefore $v_1,...,v_m$ is linearly independent in $V$.



### (5) Prove that $L(V,W)$ is a vector space, as was asserted in 3.6.
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



### (6) Prove that multiplication of linear maps has the associative, identity, and distributive properties asserted in 3.8.

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



### (7) Show that every linear map from a one-dimensional vector space to itself is multiplication by some scalar. More precisely, prove that if $dim V = 1$ and $T \in L(V)$, then there exists $\lambda \in F$ such that $Tv=\lambda v$ for all $v \in V$.
Let $v \in V$. Let $e$ be a basis of $V$. 

Since $Te \in V$, we can write $Te = \lambda e$ for some unique $\lambda in F$.

Let $v=ae$ for some $a \in F$.

We have

$$Tv = T(ae) = aTe = a (\lambda e) = \lambda(ae) = \lambda v$$ 

Therefore $T$ is multiplication by $\lambda$.



### (8) Give an example of a function $\phi: R^2 \rightarrow R$ such that $\phi (av) = a \phi(v)$ for all $a \in R$ and $v \in R^2$, but $\phi$ is not linear.
Let $\phi(x,y) = x^2 / y$ if $y \neq 0$, and $\phi(x,y) = 0$ if $y=0$.

When $y \neq 0$, 

$$\phi(ax, ay) = (ax)^2/(ay) = a x^2 /y = a phi(x,y)$$

When $y = 0$, 

$$\phi(ax,ay) = 0 = a phi(x,y)$$

Therefore the function satisfies the homogeneity property.

When $y_1 \neq 0, y_2 \neq 0, y_1 + y_2 \neq 0$,

$$\phi(x_1 + x_2, y_1 + y_2) = (x_1+x_2)^2/(y_1 + y_2)$$

$$\phi(x_1,y_1) + \phi(x_2, y_2) = x_1^2 / y_1 + x_2^2 / y_2 $$

which is not equal to each other.



### (9) Give an example of a function $\phi: C \rightarrow C$ such that $\phi(w+z) = \phi(w) + \phi(z)$ for all $w, z \in C$ but $\phi$ is not linear. 
Let $\phi(z)=Re(z)$. First we show that it satisfies linearity. 

Let $w=a+bi, z=c+di$. We have 

$$\phi(w+z)=Re(a+bi+c+di)= a+c = Re(a+bi)+Re(c+di) = \phi(w) + \phi(z)$$

Now we show that it does not satisfy homogeneity. Let $w=a+bi, \lambda = i$. We have

$$\phi(iw) = Re(-b+ai) = -b$$

$$i \phi(w) = i Re(a+bi) = ai$$

Therefore $\phi$ is not linear.



### (11) Suppose $V$ is finite-dimensional and $T \in L(V)$. Prove that $T$ is a scalar multiple of the identity if and only if $ST=TS$ for every $S \in L(V)$.
$\rightarrow$

Let $T = aI \in L(V), v \in V, S \in L(v)$. Then $Tv = (aI)v = a(Iv) = av$. We have 

$$(ST)(v) = S(Tv) = S(av) = a(Sv)$$

$$(TS)(v) = T(Sv) = aI(Sv) = a(Sv)$$

Thus $ST=TS$ as desired.

$\leftarrow$

Since $V$ is finite-dimensional, let $v_1,...,v_n$ be a basis for $V$. Given that $ST=TS$ for every $S \in L(V)$, define $S$ such that $S(v_j) = v_i, S(v_k)=0, i,j \in \\{1,...,n\\}, k \neq j$. i.e. $S$ sends the $v_j$ to $v_i$ and kills the other dimensions.

$$(ST)(v_j) = S(Tv_j) = S(a_1 v_1 + ... + a_n v_n) = a_i v_i, a_1,...,a_n \in F$$. 

$$(TS)(v_j) = T(Sv_j) = T(v_i)$$. 

Then $Tv_i = a_i v_i$. Since $i$ is arbitrary, $T v_i = a_i v_i, i = 1,...,n$.

Reapplying the linear maps, we have 

$$(ST)(v_j) = S(Tv_j) = S(a_j v_j) = a_j v_i$$

$$(TS)(v_j) = T(Sv_j) = T(v_i) = a_i v_i$$

Then $a_i = a_j, i,j=1,...,n$. Hence $T = aI$.



### (12) Suppose $U$ is a subspace of $V$ with $U \neq V$. Suppose $S \in L(U,W)$ and $S \neq 0$. Define $T: V \rightarrow W$ by $Tv = Sv$ if $v \in U$ and $Tv = 0$ if $v \in V, v \notin U$. Prove that $T$ is not a linear map on $V$.
Since $S \neq 0$, $Su \neq 0$ for some $u \in U$. Let $v \in V, v \notin U$. Then $v+u \notin U$. $T(v+u) = 0$. However, $Tu + Tv = Su + 0$. Then $T(v+u) \neq Tu + Tv$. Hence $T$ is not a linear map on $V$.



### (13) Suppose $V$ is finite-dimensional. Prove that every linear map on a subspace of $V$ can be extended to a linear map on $V$. In other words, show that if $U$ is a subspace of $V$ and $S \in L(U,W)$, then there exists $T \in L(V,W)$ such that $Tu = Su$ for all $u \in U$.
Let $u_1,...,u_m$ be a basis for $U$, and extend it to a basis $u_1,...,u_m, v_1,...,v_n$ for $V$. By 3.4, there exists a unique linear map $T: V \rightarrow W$ such that $T u_k = S u_k$ for each $k = 1,...,m$ and $T v_j = 0$ for each $j = 1,...,n$.

Let $u \in U$. Then 

$$Tu = T(a_1 u_1 + ... a_m u_m) = T(a_1 u_1) + ... + T(a_m u_m) = a_1 Tu_1 + ... + a_m Tu_m = a_1 Su_1 + ... a_m Su_m = S(a_1 u_1) + ... + S(a_m u_m) = S(a_1 u_1 + ... + a_m u_m) = S(u)$$. 



### (15) Suppose $v_1,...,v_m$ is a linearly dependent list of vectors in $V$. Suppose also that $W \neq \\{0\\}$. Prove that there exist $w_1,...,w_m \in W$ such that no $T \in L(V,W)$ satisfies $Tv_k = w_k$ for each $k=1,...,m$.  
Suppose $v_1,...,v_m$ be a list of linearly dependent list of vectors in $V$. $Assume towards contradiction that there exist $T \in L(V, W)$ such that $Tv_k = w_k$ for each $k=1,...,m$.

Since $v_1,...,v_m$ is a linearly dependent list of vectors, there exist scalars $a_1,...,a_m$, not all 0, such that $a_1 v_1 + ... + a_m v_m = 0$. Let $j$ be an index such that $a_j \neq 0$. 

Let $w_1,...,w_m \in W$ such that $w_j = w \neq 0$, and $w_i=0$ for all $i \neq j$.

Applying $T$, we have $T(0) = 0$, but

$$0 = T(a_1 v_1 + ... + a_m v_m) = a_1 Tv_1 + ... a_m Tv_m = a_j w \neq 0$$

which is a contradiction. 



### (16) Suppose $V$ is finite-dimensional with $dim V > 1$. Prove that there exist $S,T \in L(V)$ such that $ST \neq TS$.
Let $V=P_3(F)$. Let $p(z) \in V$. 

Define differentiation map and multiplication map $Dp=p', Mp = zp(z)$. Then 

$$(DM)(p) = D (z p(z)) = p + z p'$$

$$(MD)(p) = M (p') = z p'$$

Thus $DM \neq MD$.
