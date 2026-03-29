Linear Algebra Done Right - Chapter 2
================
Rosie Sun <br>
2026-03-28

# 2A Span and Linear Independence

### 2.2 Definition: linear combination
A linear combination of a list $v_1, ..., v_m$ of vectors in $V$ is a vector of the form $a_1 v_1 + ... + a_m v_m$, where $a_1, ..., a_m \in F$.

### 2.4 Definition: span
The set of all linear combinations of a list of vectors $v_1, ..., v_m$ in $V$ is called the span of $v_1, ..., v_m$, denoted by $span(v_1, ..., v_m)$. In other words, $span(v_1, ..., v_m) = \\{ a_v v_1 + ... + a_m v_m: a_1, ..., a_m \in F \\}$. 

The span of the empty list () is defined to be $\\{0\\}$

### 2.6 Span is the smallest containing subspace
The span of a list of vectors in $V$ is the smallest subspace of $V$ containing all vectors in the list.

### 2.7 Definition: spans
If $span(v_1,...,v_m)$ equals $V$, we say that the list $v_1,...,v_m$ spans V.

### 2.9 Definition: finite-dimensional vector space
A vector space is called finite-dimensional if some list of vectors in it spans the space.

### 2.10 Definition: polynomial
A function $p: F \rightarrow F$ is called a polynomial with coefficients in $F$ if there exist $a_0, ..., a_m \in F$ such that $p(z) = a_0 + a_1 z + a_2 z^2 + ... a_m z^m$ for all $z \in F$. $P(F)$ is the set of all polynomials with coefficients in $F$.

### 2.15 Definition: linearly independent
A list $v_1, ..., v_m$ of vectors in $V$ is called linearly independent if the only choice of $a_1,...,a_m \in F$ that makes $a_1 v_1 + ... + a_m v_m = 0$ is $a_1 = ... = a_m = 0$.

### 2.17 Definition: linearly dependent
A list of vectors in $V$ is called linearly dependent if it is not linearly independent. In other words, a list $v_1,..., v_m$ of vectors in $V$ is linearly dependent if there exist $a_1,...,a_m \in F$, not all 0, such that $a_1 v_1 + ... + v_m v_m = 0$.

### 2.19 Linear dependence lemma
Suppose $v_1,...,v_m$ is a linearly dependent list in $V$. Then there exists $k \in \\{1,2,...,m\\}$ such that $v_k \in span(v_1,...,v_{k-1})$. Furthermore, if $k$ satisfies the condition above and the kth term is removed from $v_1,...,v_m$, then the span of the remaining list equals $span(v_1,...,v_m)$.

### 2.22 Length of linearly independent list $\leq$ length of spanning list.
In a finite-dimensional vector space, the length of every linearly indpeendent list of vectors is less than or equal to the length of every spanning list of vectors.

### 2.25 Finite dimensional subspaces
Every subspace of a finite-dimensional vector space is finite-dimensional.


## Exercises

#### (1) Find a list of four distinct vectors in $F^3$ whose span equals $\\{(x,y,z) \in F^3: x+y+z=0 \\}$.
$(1,-1,0), (1,0,-1), (0,1,-1), (1,-2,1)$. 


#### (2) Prove or give a counterexample: If $v_1, v_2, v_3, v_4$ spans $V$, then the list $v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4$ also spans $V$.
Let $v \in V$. Since $v_1, v_2, v_3, v_4$ spans $V$, we have $v = av_1 + bv_2 + cv_3 + dv_4, a,b,c,d \in F$. We can rewrite it as $v=a(v_1-v_2) + (a+b)(v_2-v_3) + (a+b+c)(v_3-v_4) + (a+b+c+d)v_4$. Thus $v \in span(v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4)$, and $V \subseteq span(v_1 - v_2, v_2 - v_3, v_3 - v_4)$. 

The new vectors are linear combinations of the old vectors. $v_1-v_2=1v_1 + (-1)v_2 + 0v_3 + 0v_4$, $v_2-v_3=0v_1 + 1v_2 + (-1)v_3 + 0v_4$, $v_3-v_4=0v_1 + 0v_2 + 1v_3 + (-1)v_4$, $v_4=0v_1 + 0v_2 + 0v_3 + 1v_4$. Thus $v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4 \in V$. Since $V$ is closed under addition and scalar multiplication, $span(v_1 - v_2, v_2 - v_3, v_3 - v_4, v_4) \subseteq V$.


#### (3) Suppose $v_1, ..., v_m$ is a list of vectors in $V$. For $k \in \\{1,...,m\\}$, let $w_k=v_1+...v_k$. Show that $span(v_1, ..., v_m) = span(w_1, ..., w_m)$.
Let $v \in span(v_1, ..., v_m)$. Then $v=a_1 v_1 + ... +a_m v_m, a_1, ..., a_m \in F$. We can rewrite it as $v=a_1 w_1 + a_2 (w_2 - w_1) + a_3 (w_3-w_2) + ... + a_m (w_m-w_{m-1}) = (a_1-a_2)w_1 + (a_2-a_3)w_2 + ... + (a_{m-1}-a_m)w_{m-1} + a_m w_m$. Thus $v \in span(w_1, ..., w_m)$, and $span(v_1, ..., v_m) \subseteq span(w_1, ..., w_m)$. 

Let $w \in span(w_1, ..., w_m)$. Then $w=a_1 w_1 + ... +a_m w_m, a_1, ..., a_m \in F$. We can rewrite it as $w=(a_1+a_2+...+a_m) v_1 + (a_2+...+a_m)v_2 + ... + a_m v_m$. Thus $w \in span(v_1, ..., v_m)$, and $span(w_1, ..., w_m) \subseteq span(v_1, ..., v_m)$. Equality is established as desired.


#### (7a) Show that if we think of $C$ as a vector space over $R$, then the list $1+i, 1-i$ is linearly independent.
Suppose $a(1+i)+b(1-i)=0, a,b \in R$. Then $(a+b) + (a-b)i = 0$. We have $a+b=a-b=0$, which implies $a=b=0$. Thus by (2.15) they are linearly independent.

#### (7b) Show that if we think of $C$ as a vector space over $C$, then the list $1+i, 1-i$ is linearly dependent.
Suppose $(a+bi)(1+i)+(c+di)(1-i)=0, a,b,c,d \in R$. Then $(a-b+c+d)+(a+b-c+d)i=0$. This holds if $a=d=0, b=c=1$. Thus by (2.17) they are linearly dependent.


#### (8) Suppose $v_1, v_2, v_3, v_4$ is linearly in $V$. Prove that the list $v_1-v_2, v_2-v_3, v_3-v_4, v_4$ is also linearly independent.
Suppose $a(v_1-v_2) + b(v_2-v_3) + c(v_3-v_4) + dv_4 =0$. We want to show that $a=b=c=d=0$. We can rewrite the equation as $av_1 + (b-a)v_2 + (c-b)v_3 + (d-c)v_4 = 0$. Given that $v_1, v_2, v_3, v_4$ are linearly independent, we have $a=b-a=c-b=d-c=0$, $a=b=c=d=0$. Thus $v_1-v_2, v_2-v_3, v_3-v_4, v_4$ are linearly independent as desired.


#### (9) Prove or give a counterexample: If $v_1, ..., v_m$ is a linearly independent list of vectors in $V$, then $5v_1-4v_2, v_2, v_3, ..., v_m$ is linearly independent.
Suppose $a_1 (5v_1 -4v_2) + a_2 v_2 + ... + a_m v_m = 0$. We want to show that $a_1=a_2=...=a_m=0$. We can rewrite the equation as $(5a_1)v_1 + (a_2-4a_1) v_2 + a_3 v_3 + ... + a_m v_m = 0$. Given that $v_1, ..., v_m$ are linearly independent, $5a_1 = a_2-4a_1=a_3=...=a_m=0$, which implies that $a_1=0, a_2=0$. Thus $5v_1-4v_2, v_2, ..., v_m$ are linearly independent as desired.


#### (10) Prove or give a counterexample: If $v_1, v_2, ..., v_m$ is a linearly independent list of vectors in $V$ and $\lambda \in F$ with $\lambda \neq 0$, then $\lambda v_1, \lambda v_2, ..., \lambda v_m$ is linearly independent.
Suppose $a_1 (\lambda v_1) + ... + a_m (\lambda v_m) = 0$. We want to show that $a_1=a_2=...=a_m=0$. We can rewrite the equation as $(a_1 \lambda) v_1 + ... + (a_m \lambda) v_m = 0$. Given that $v_1, ..., v_m$ are linearly independent, $a_1 \lambda =...=a_m \lambda=0$. Since $\lambda \neq 0$, this implies that $a_1= ...= a_m=0$. Thus $\lambda v_1, \lambda v_2, ..., \lambda v_m$ are linearly independent as desired.


#### (11) Prove or give a counterexample: If $v_1, ..., v_m$ and $w_1,...,w_m$ are linearly independent lists of vectors in $V$, then the list $v_1+w_1, ..., v_m+w_m$ is linearly independent.
Counterexample: $(1,0), (0,1) \in R^2$ is linearly independent. $(-1,0), (0,-1) \in R^2$ is also linearly independent. But $(0,0), (0,0)$ is not linearly independent.


#### (12) Suppose $v_1,...,v_m$ is linearly independent in $V$ and $w \in V$. Prove that if $v_1+w, ..., v_m+w$ is linearly dependent, then $w \in span(v_1,...,v_m)$.
By (2.19), if $v_1+w,...,v_m+w$ is linearly dependent, there exist $v_k+w$ such that $v_k+w \in span(v_1+w,...,v_{k-1}+w), k \in \\{1,...,m\\}$. $v_k+w = a_1 (v_1+w) + ... + a_{k-1} (v_{k-1} +w)$. Expanding, we have $(1-a_1-...-a_{k-1}) w = a_1 v_1 + ... + a_{k-1} v_{k-1}$. If $1-a_1-...-a_{k-1} \neq 0$, then $w = 1/(1-a_1-...-a_{k-1}) (a_1 v_1 + ... + a_{k-1} v_{k-1})$, thus $w \in span(v_1,...,v_m)$. If $1-a_1-...-a_{k-1} = 0$, then we have $0 = a_1 v_1 + ... + a_{k-1} v_{k-1}$. Since $v_1,...,v_m$ is linearly independent, $a_1=...=a_{k-1}=0$. So $1-a_1-...-a_{k-1}=1$, which is a contradiction, showing that this case is not possible.


#### (13) Suppose $v_1,...,v_m$ is linearly independent in $V$ and $w \in V$. Show that $v_1,...,v_m,w$ is linearly independent $iff w \notin span(v_1,...,v_m)$.
$\Rightarrow$ <br>
Assume towards contradiction that $w \in span(v_1,...,v_m)$. Then $w=a_1 v_1 + ... + a_m v_m, a_1, ..., a_m \in F$. We have $a_1 v_1 + ... + a_m v_m + (-1)w = 0$, which violates (2.15). Therefore $w \notin span(v_1,...,v_m)$.

$\Leftarrow$ <br>
Assume towards contradiction that $v_1,...,v_m,w$ is linearly dependent. By (2.21), there exist a vector in $v_1,...,v_m,w$ which is a linear combination of the previous vectors. Since $w \notin span(v_1,...,v_m)$, it is not a linear combination of any of the $v$'s that come before it. Then there exist $k \in \\{1,...,m\\}$ such that $v_k \in span(v_1,...,v_{k-1})$. However this violates the fact that $v_1,...,v_m$ is linearly independent. Therefore $v_1,...,v_m,w$ is linearly independent.


#### (14) Suppose $v_1,...,v_m$ is a list of vectors in $V$. For $k \in \\{1,...,m\\}$, let $w_k=v_1+...+v_k$. Show that the list $v_1,...,v_m$ is linearly independent if and only if the list $w_1,...,w_m$ is linearly independent.
$\Rightarrow$ <br>
Suppose $a_1 w_1 + ... a_m w_m = 0$. We can rewrite it as $a_1 v_1 + a_2 (v_1+v_2) + ... + a_m (v_1+...v_m)=0$, $(a_1+...+a_m) v_1 + (a_2+...a_m)v_2 + ... + a_m v_m=0$. Given that $v_1,...,v_m$ is linearly independent, we have $a_1+...+a_m=0, a_2+...+a_m=0,..., a_m=0$, which implies that $a_1=a_2=...=a_m=0$. Thus $w_1,...,w_m$ is linearly independent.

$\Leftarrow$ <br>
Suppose $b_1 v_1 + ... b_m v_m = 0$. We can rewrite it as $b_1 w_1 + b_2 (w_2-w_1) + ... + b_m (w_m-w_{m-1})=0$, $(b_1-b_2) w_1 + (b_2-b_3)w_2 + ... + b_m w_m=0$. Given that $w_1,...,w_m$ is linearly independent, we have $b_1-b_2=0, b_2-b_3=0,..., b_m=0$, which implies that $b_1=b_2=...=b_m=0$. Thus $v_1,...,v_m$ is linearly independent.



# 2B Bases

### 2.26 Definition: basis
A basis of $V$ is a list of vectors in $V$ that is linearly independent and spans $V$.

### 2.28 Criterion for basis
A list $v_1,...,v_n$ of vectors in $V$ is a basis of $V$ if and only if every $v \in V$ can be written uniquely in the form $v=a_1 v_1 + ... a_n v_n$, where $a_1,...,a_n \in F$.

### 2.30 Every spanning list contains a basis
Every spanning list in a vector space can be reduced to a basis of the vector space.

### 2.31 Basis of finite-dimensional vector space
Every finite-dimensional vector space has a basis.

### 2.32 Every linearly independent list extends to a basis
Every linearly independent list of vectors in a finite-dimensional vector space can be extended to a basis of the vector space.

### 2.33 Every subspace of $V$ is part of a direct sum equal to $V$
Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$. Then there is a subspace $W$ of $V$ such that $V=U \oplus W$.

## Exercises









# 2C Dimension

### 2.34 Basis length does not depend on basis
Any two bases of a finite-dimensional vector space have the same length.

### 2.35 Definition: dimension
The dimension of a finite-dimensional vector space is the length of any basis of the vector space. The dimension of a finite-dimensional vector space is denoted by $dim V$.

### 2.37 Dimension of a subspace
If $V$ is finite-dimensional and $U$ is a subspace of $V$, then $dim U \leq dim V$.

### 2.38 Linearly independent list of the right length is a basis
Suppose $V$ is finite-dimensional. Then every linearly independent list of vectors in $V$ of length $dim V$ is a basis of $V$.

### 2.39 Subspace of full dimension equals the whole space
Suppose that $V$ is finite-dimensional and $U$ is a subspace of $V$ such that $dim U = dim V$. THen $U = V$.

### 2.42 Spanning list of the right length is a basis
Suppose $V$ is finite-dimensional. Then every list of vectors in $V$ that spans $V$ and has the length $dim V$ is a basis of $V$.

### 2.43 Dimension of a sum
If $V_1$ and $V_2$ are subspaces of a finite-dimensional vector space, then $dim (V_1+V_2) = dim V_1 + dim V_2 - dim(v_1 \cap V_2)$.


## Exercises