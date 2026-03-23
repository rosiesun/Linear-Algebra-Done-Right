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

$0v=0$ for every $v in V$.

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

*(Disclaimer: I spent forever trying to prove “if $v \neq 0$ then $a=0$”
after the first statement. Had to ask Claude for help. Turns out proving
one statement is the same as proving the OR statement. I could be
wrong.)*

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

*(Disclaimer: Had to get a hint from Claude for direction 2. Why is math
so hard. This reminds me why I didn’t like proofs in school. A lot of
times you just had to FEEL what’s the right starting point. Otherwise
you’re just in purgatory.)*

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
