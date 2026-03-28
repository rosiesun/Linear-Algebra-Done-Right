Linear Algebra Done Right - Chapter 1
================
Rosie Sun
2026-03-23

# 1B Definition of Vector Space

### 1.19 Definition: addition, scalar multiplcation

- An addition on a set $V$ is a function that assigns an element
  $u+v \in V$ to each pair of elements $u,v \in V$.
- A scalar multiplication on a set $V$ is a function that assigns an
  element $\lambda v \in V$ to each $\lambda \in F$ and each $v \in V$.

### 1.20 Definition: vector space

A vector space is a set $V$ along with an addition on $V$ and a scalar
multiplcation on $V$ such that the following properties hold.

- commutativity: $u+v=v+u$ for all $u,v \in V$.
- associativity: $(u+v)+w=u+(v+w)$ and $(ab)v=a(bv)$ for all
  $u,v,w \in V$ and for all $a,b \in F$.
- additive identity: There exists an element $0 \in V$ such that $v+0=v$
  for all $v \in V$.
- additive inverse: For every $v \in V$, there exists $w \in V$ such
  that $v+w=0$.
- multiplicative identity: $1v=v$ for all $v \in V$.
- distributive properties: $a(u+v)=au+av$ and $(a+b)v=av+bv$ for all
  $a,b \in F$ and all $u,v \in V$.

### 1.26 Unique additive identity

A vector space has a unique additive identity.

Proof: Suppose 0 and 0’ are both additive identities for some vector
space $V$. Then

$$0' = 0' + 0 = 0 + 0' = 0$$

where the first equality holds because 0 is an additive identity, the
second equality comes from commutativity, and the third equality holds
because 0’ is an additive identity. Thus $0'=0$ proving that $V$ has
only one additive identity.

### 1.27 Unique additive inverse

Every element in a vector space has a unique additive inverse.

Proof: Suppose $V$ is a vector space. Let $v \in V$. Suppose $w$ and
$w'$ are additive inverses of $v$. Then

$$w = w + 0 = w + (v+w') = (w+v)+w' = 0 + w' = w'$$

Thus $w=w'$, as desired.

### 1.30 The number 0 times a vector

$0v=0$ for every $v \in V$.

Proof: For $v \in V$, we have

$$0v = (0+0)v = 0v + 0v$$

Adding the additive inverse of $0v$ to both sides gives

$$0v + (-0v) = 0v + 0v + (-0v)$$

$$0 = 0v$$

as desired.

### 1.31 A number times the vector 0

$a0=0$ for every $a \in F$.

Proof: For $a \in F$, we have

$$a0 = a(0+0) = a0 + a0$$

Adding the additive inverse of $a0$ to both sides gives

$$a0 + (-a0) = a0 + a0 + (-a0)$$

$$0 = a0$$

as desired.

### 1.32 The number -1 times a vector

$(-1)v = -v$ for every $v \in V$.

Proof: For $v \in V$, we have

$$v + (-1)v = 1v + (-1)v = (1+(-1))v = 0v = 0$$

This equation says that $(-1)v$, when added to $v$, gives 0. Thus
\$(-1)v is the additive inverse of $v$, as desired.

## Exercises

#### 1) Prove that $-(-v)=v$ for every $v \in V$.

From (1.32) which states $(-1)v=-v$ for every $v \in V$,

$$-(-v) = (-1)(-v) = (-1)(-1)v = 1v = v$$

The last equality comes from multiplicative identity.

#### 2) Suppose $a \in F, v \in V$, and $av=0$. Prove that $a=0$ or $v=0$.

*(I spent forever trying to prove “if $v \neq 0$ then $a=0$” after the
first statement. Had to ask Claude for help. Turns out proving one
statement is the same as proving the OR statement. I could be wrong.)*

Assume $a \neq 0$. Then

$$av=0$$

$$(1/a) av = (1/a) 0$$

$$1v = 0$$

by associativity on the left side, (1.31) on the right side. Hence

$$v=0$$

as desired.

#### 4) The empty set is not a vector space. The empty set fails to satisfy only one of the requirements listed in the definition of a vector space (1.20). Which one?

The empty set it does not satisfy the additive identity condition
because it’s an existence statement. The empty set satisfies the other
conditions vacuously.

#### 5) Show that in the definition of a vector space (1.20), the additive inverse condition can be replaced with the condition that $0v=0$ for all $v \in V$.

*(Had to get a hint from Claude for direction 2. A lot of times you just
had to FEEL what’s the right starting point. Otherwise you’re just in
purgatory.)*

Direction 1: Any space satisfying the original axioms (with additive
inverse) also satisfies $0v=0$ for all $v$.

The proof of the first direction comes from (1.30). For $v \in V$,

$$0v = (0+0)v = 0v + 0v$$ by distributive properties.

$$0v + (-0v) = 0v + 0v + (-0v)$$

$$0 = 0v$$ by additive inverse on both sides.

Direction 2: Any space satisfying the modified axioms (with $0v=0$ for
all $v$ instead of additive inverse) actually does have additive
inverse.

$$0=0v=(1+(-1))v = 1v + (-1)v = v+(-v)$$

The second equality comes from distributive properties. The third
equality comes from multiplicative inverse and (1.32). Since $v+(-v)=0$,
$(-v)$ must be the additive inverse of $v$.

#### 6)

Let $\infty$ and $-\infty$ denote two distinct objects, neither of which
is in $R$. Define an addition and scalar multiplication on
$R \cup \{\infty, -\infty \}$ as you could guess from the notation.
Specifically, the sum and product of two real numbers is as usual, and
for $t \in R$ define

$t \infty = -\infty$ if $t<0$

$t \infty = 0$ if $t=0$

$t \infty = \infty$ if $t>0$

$t (-\infty) = \infty$ if $t<0$

$t (-\infty) = 0$ if $t=0$

$t (-\infty) = -\infty$ if $t>0$

$$t + \infty = \infty + t = \infty + \infty = \infty$$

$$t + (-\infty) = (-\infty) + t = (-\infty) + (-\infty) = -\infty$$

$$\infty + (-\infty) = (-\infty) + \infty = 0$$

With these operations of addition and scalar multiplication, is
$R \cup \{-\infty, \infty \}$ a vector space? Explain.

It is not a vector space. Commutativity, additive inverse, additive
identity, multiplicative identity are satisfied from the definitions. We
give an counter-example for associativity.

Let $t \in R$ and we have

$$(t + \infty) + (-\infty) = \infty + (-\infty)$$

$$t + (\infty + (-\infty)) = t + 0 = t$$

$$(t + \infty) + (-\infty) \neq t + (\infty + (-\infty))$$

Associativity is not satisfied.

#### 7) Suppose $S$ is a nonempty set. Let $V^S$ denote the set of functions from $S$ to $V$. Define a natural addition and scalar multiplication on $V^S$, and show that $V^S$ is a vector space with these definitions.

Addition and scalar multiplication are defined as follows: for
$f, g \in V^S$, $(f+g)(x) = f(x) + g(x)$ for all $x \in S$; for
$a \in F$ and $f \in V^S$, $(af)(x) = af(x)$.

The proof for each condition invokes the the fact that $V^S$ maps to $V$
which is a vector space.

Communitativity:

$$(f+g)(x) = f(x) + g(x) = g(x) + f(x) = (g+f)(x)$$

The second equality comes from the fact that $g(x), f(x) \in V$.

Associativity:

$$((f+g)+h)(x) = (f+g)(x) + h(x) = (f(x) + g(x)) + h(x) = f(x) + (g(x) + h(x)) = f(x) + (g+h)(x) = (f+(g+h))(x)$$

Additive identity: define $0(x) = 0_V, 0 \in V^S$. Therefore for
$f \in V^S$,

$$(f+0)(x) = f(x) + 0(x) = f(x) + 0_V = f(x)$$

Additive inverse: define $(-f)(x) = -f(x), -f \in V^S$.

$$(f+(-f))(x) = f(x) + (-f)(x) = f(x) + (-f(x)) = 0_V$$

Multiplicative identity:

$$(1f)(x) = 1 f(x) = f(x)$$

Distributive properties: for $a, b \in F$ and $f, g \in V^S$,

$$(a(f+g))(x) = a (f+g)(x) = a(f(x)+g(x)) = af(x) + ag(x) = (af)(x) + (ag)(x)$$

$$((a+b)f)(x) = (a+b)f(x) = af(x) + bf(x) = (af)(x) + (bf)(x)$$

------------------------------------------------------------------------

# 1C Subspaces

### 1.33 Definition: subspace

A subset $U$ of $V$ is called a subspace of $V$ if $U$ is also a vector
space with the same additive identity, addition, and scalar
multiplication as on $V$.

### 1.34 Conditions for a subspace

A subset $U$ of $V$ is a subspace of $V$ if and only if $U$ satisfies
the following three conditions.

- additive identity: $0 \in U$.
- closed under addition: $u, w \in U$ implies $u + w \in U$.
- closed under scalar multiplication: $a \in F$ and $u \in U$ implies
  $au \in U$.

### 1.36 Definition: Sum of subspaces

Suppose $V_1, ..., V_m$ are subspaces of $V$. The sum of $V_1, ..., V_m$
denoted by $V_1 + ... + V_m$, is the set of all possible sums of
elements of $V_1, ..., V_m$. More precisely,

$$V_1 + ... +V_m = \{v_1 + ... + v_m: v1 \in V_1, ..., v_m \in V_m\}$$

### 1.40 Sum of subspaces is the smallest containing subspace

Suppose $V_1, ..., V_m$ are subspaces of $V$. Then $V_1 + ... + V_m$ is
the smallest subspace of $V$ containing $V_1, ..., V_m$.

### 1.41 Definition: Direct sum $\oplus$

Suppose $V_1, ..., V_m$ are subspaces of $V$. The sum $V_1 + ... V_m$ is
called a direct sum if each element of $V_1 + ... V_m$ can be written in
only one way as a sum $v_1 + ... + v_m$, where each $v_k \in V_k$.

### 1.45 Conditions for a direct sum

Suppose $V_1, ..., V_m$ are subspaces of $V$. Then $V_1 + ... + V_m$ is
a direct if and only if the only way to write 0 as a sum
$v_1 + ... + v_m$, where each $v_k \in V_k$, is by taking each $v_k$
equal to 0.

### 1.46 Direct sum of two subspaces

Suppose $U$ and $W$ are subspaces of V. Then $U + W$ is a direct sum
$\iff U \cap W = \{0\}$.

## Exercises

#### 1 For each of the following subsets of $F^3$, determine whether it is a subsapce of $F^3$.

#### (a)

$U = \{(x_1, x_2, x_3) \in F^3: x_1 + 2x_2 + 3x_3 = 0\}$

$(0, 0, 0) \in U$.

Let $u \in U, w \in U$ and $u=(x_1, x_2, x_3), w=(y_1, y_2, y_3)$. We
want to show that $u+w = (x_1+y_1, x_2+y_2, x_3+y_3) \in U$.

$$(x_1+y_1) + 2(x_2+y_2) + 3(x_3+y_3) = x_1+y_1+2x_2+2y_2+3x_3+3y_3 = (x_1+2x_2+3x_3) + (y_1+2y_2+3y_3)=0+0=0$$

Hence $U$ is closed under addition.

Let $u \in U, a \in F$, and $u=(x_1, x_2, x_3)$. We want to show that
$au = (ax_1, ax_2, ax_3) \in U$.

$$(ax_1) + 2(ax_2) + 3(ax_3) = a(x_1+2x_2+3x_3) = a0 = 0$$

Hence $U$ is closed under scalar multiplication. By (1.34) $U$ is a
subspace.

#### (b)

$U = \{(x_1, x_2, x_3) \in F^3: x_1 + 2x_2 + 3x_3 = 4\}$

It is not a subspace because $(0,0,0) \notin U$.

#### (c)

$U = \{(x_1, x_2, x_3) \in F^3: x_1 x_2 x_3 = 0\}$

It is not a subspace because it is not closed under addition.

Counterexample: let $u=(1,0,0) \in U, w=(0,1,1) \in U$.
$u+w=(1,1,1) \notin U$.

#### (d)

$U = \{(x_1, x_2, x_3) \in F^3: x_1 = 5x_3\}$

$(0, 0, 0) \in U$.

Let $u \in U, w \in U$ and $u=(x_1, x_2, x_3), w=(y_1, y_2, y_3)$. We
want to show that $u+w = (x_1+y_1, x_2+y_2, x_3+y_3) \in U$.

$$(x_1+y_1) - 5(x_3+y_3) = (x_1 - 5x_3) + (y_1 - 5y_3)= 0+0=0$$

Hence $U$ is closed under addition.

Let $u \in U, a \in F$, and $u=(x_1, x_2, x_3)$. We want to show that
$au = (ax_1, ax_2, ax_3) \in U$.

$$ax_1 - 5ax_3 = a(x_1 - 5x_3) = a0 = 0$$

Hence $U$ is closed under scalar multiplication. By (1.34) $U$ is a
subspace.

#### 5) Is $R^2$ a subspace of the complex vector space $C^2$?

$R^2$ is a subspace of the complex vector space $C^2$ because it is not
closed under complex scalar multiplication.
$i (1,1) = (i, i) \notin R^2$.

#### 6 (a) Is $U=\{(a,b,c) \in R^3: a^3=b^3\}$ a subspace of $R^3$?

$$a^3 = b^3 \iff a=b$$

Another way to write $U$ is $U=\{(a,a,c): a,c \in R\}$.

$(0,0,0) \in U$.

Let $u=(a,a,c), w=(x,x,y)$. Then $u+w = (a+x, a+x, c+y) \in U$. Hence
$U$ is closed under addition.

Let $u=(a,a,c), \lambda \in F$. Then
$\lambda u = (\lambda a, \lambda a, \lambda c) \in U$. Hence $U$ is
closed under scalar multiplication. By (1.34) $U$ is a subspace.

#### 6 (b) Is $U=\{(a,b,c) \in C^3: a^3=b^3\}$ a subspace of $C^3$?

Counterexample: let $u=(1, 1, 0), w=(1, (-1+\sqrt(3)i)/2, 0)$. Then
$u+w=(2, (1+\sqrt(3)i)/2, 0)$.

$((1+\sqrt(3)i)/2)^3 = -1 \neq 8$, therefore $U$ is not closed under
addition.

#### 7) Prove or give a counterexample: If $U$ is a nonempty subset of $R^2$ such that $U$ is closed under addition and under taking additive inverses, then $U$ is a subspace of $R^2$.

Counterexample: $U=Z^2$. $(0,0) \in U$ and for each $(a,b), a,b\in Z$,
$(-a,-b) \in Z$ by the definition of integers. It is not closed under
scalar multiplication, e.g. $0.5 (1, 1) \notin Z^2$.

#### 8) Give an example of a nonempty subset $U$ of $R^2$ such that $U$ is closed under scalar multiplication, but $U$ is not a subspace of $R^2$.

*(This was a tough one! I guess I simply lack imagination (which means I
cannot be a mathematician). Had to ask Claude.)*

Counterexample: $U= \{(x,0): x \in R\} \cup \{(0,y): y \in R\}$,
i.e. the two axis lines. It is closed under scalar multiplication. It is
not closed under addition, e.g. $(1,0) + (0,1) = (1,1) \notin U$.

#### 10) Suppose $V_1$ and $V_2$ are subspaces of $V$. Prove that the intersection $V_1 \cap V_2$ is a subspace of $V$.

The proof is based on the fact that both $V_1$ and $V_2$ are subspaces.

$0 \in V_1$ and $0 \in V_2$, therefore $0 \in V_1 \cap V_2$.

Let $u,w \in V_1 \cap V_2$. We have $u \in V_1, w \in V_1, u+w \in V_1$,
$u \in V_2, w \in V_2, u+w \in V_2$. Therefore $u+w \in V_1 \cap V_2$.

Let $u \in V_1 \cap V_2, a \in F$. We have $u \in V_1, au \in V_1$,
$u \in V_2, au \in V_2$. Therefore $au \in V_1 \cap V_2$.

By (1.34) $V_1 \cap V_2$ is a subspace.

#### 12) Prove that the union of two subspaces of $V$ is a subspace of $V$ if and only if one of the subspaces is contained in the other.

Let $V_1, V_2$ be two subspaces of $V$.

Note that the argument is symmetric. Assume $V_1 \subset V_2$. Then
$V_1 \cup V_2 = V_2$. Since $V_2$ is a subspace $V_1 \cup V_2$ is a
subspace.

Assume $V_1 \cup V_2$ is a subspace. Assume towards contradiction that
neither subspace contains the other. Let $u, w \in V_1 \cup V_2$. Assume
$u \in V_1$ and $u \notin V_2$, $w \in V_2$ and $w \notin V_1$.

Since $V_1 \cup V_2$ is a subspace, $u+w \in V_1 \cup V_2$.

If $u+w \in V_1$, and $-u \in V_1$, $u+w+(-u) = w \in V_1$, which is a
contradiction.

If $u+w \in V_2$, and $-w \in V_2$, $u+w+(-w) = u \in V_2$, which is a
contradiction.

Therefore one subspace has to be contained in the other.

#### 15) Suppose $U$ is a subspace of $V$. What is $U+U$?

$U+U = \{u_1 + u_2: u_1 \in U, u_2 \in U\}$. By definition
$u_1 + u_2 \in U$ because $U$ is closed under addition. Therefore
$U+U \subset U$.

Let $u \in U$. $u=u+0$, since $u \in U$ and $0 \in U$, $U \subset U+U$
trivially. Thus $U=U+U$ as desired.

#### 16) Is the operation of addition on the subspaces of $V$ commutative? In other words, if $U$ and $W$ are subspaces of $V$, is $U+W=W+U$?

The operation is commutative, which comes from the fact that $V$ is a
vector space. $U+W=\{(u+w): u \in U, w \in W\}$.
$W+U= \{(w+u): w \in W, u \in U\}$. Since $u+w=w+u$ for all $u,w \in V$,
every element of $U+W$ is an element of $W_U$ and vice versa, hence
$U+W=W+U$.

#### 17) Is the operation of addition on the subspaces of $V$ associative? In other words, if $V_1$, $V_2$, $V_3$ are subspaces of $V$, is $(V_1+V_2)+V_3 = V_1+(V_2+V_3)$?

The operation is associative, which comes from the fact that $V$ is a
vector space. Same argument as Ex.16.
$(V_1 + V_2) + V_3 = \{(v_1+v_2)+v_3: v_1 \in V_1, v_2 \in V_2, v_3 \in V_3\}$.
$V_1 + (V_2 + V_3) = \{v_1+(v_2+v_3): v_1 \in V_1, v_2 \in V_2, v_3 \in V_3\}$.

#### 18) Does the operation of addition on the subspaces of $V$ have an additive identity? Which subspaces have additive inverses?

The operation has an additive identity $\{0\}$. Let $U$ be a subspace of
$V$. $U+\{0\} = \{(u+0): u \in U, 0 \in \{0\}\} = U$.

Only $\{0\}$ has additive inverse $\{0\}$. For any subspace
$U \neq \{0\}$, there does not exist $W$ such that $U+W=\{0\}$. We have
$U \subseteq U+W$, since for any $u \in U$, $u=u+0 \in U+W$. Then
$U+W \supseteq U \neq \{0\}$.

#### 19) Prove or give a counterexample: If $V_1$, $V_2$, $U$ are subspaces of $V$ such that $V_1+U=V_2+U$, then $V_1=V_2$.

Counterexample: $V_1=\{(x,0): x \in R\}$, $V_2=\{(0,y): y \in R\}$,
$U=R^2$.

#### 20) Suppose $U=\{(x,x,y,y) \in F^4: x,y\in F\}$. Find a subspace $W$ of $F^4$ such that $F^4=U \oplus W$.

$W=\{(0,x,0,y): x,y \in F\}$.

#### 21) Suppose $U=\{(x,y,x+y,x-y, 2x) \in F^5: x,y\in F \}$. Find a subspace $W$ of $F^5$ such that $F^5=U \oplus W$.

$W=\{(0,0,x,y,z): x,y,z \in F\}$.

#### 22) Suppose $U=\{(x,y,x+y,x-y, 2x) \in F^5: x,y\in F \}$. Find three subspaces $W_1, W_2, W_3$ of $F^5$, none of which equals $\{0\}$, such that $F^5=U \oplus W_1 \oplus W_2 \oplus W_3$.

$W_1=\{(0,0,x,0,0): x \in F\}$, $W_2=\{(0,0,0,x,0): x \in F\}$,
$W_3=\{(0,0,0,0,x): x \in F\}$.

#### 23) Prove or give a counterexample: If $V_1, V_2, U$ are subspaces of $V$ such that $V=V_1 \oplus U$ and $V=V_2 \oplus U$, then $V_1=V_2$.

Counterexample from Ex. 20: 
$$V_1=\{(x,x,y,y) \in F^4: x,y\in F \}$$,
$$V_2=\{(x,0,y,0) \in F^4: x,y\in F \}$$,
$$U=\{(0,x,0,y) \in F^4: x,y\in F \}$$
