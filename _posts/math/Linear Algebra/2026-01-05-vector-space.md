---
title: 1.2 Vector Spaces
date: 2026-01-05 15:00:00 +0900
categories: [Mathematics, Linear Algebra]
tags: [math, linear algebra, vector space]
math: true
---

## 1. Definition: Vector Space 

**Vector space $V$ over field $F$**는 집합 $V$와 두 가지 연산(Addition, Scalar Multiplication)으로 정의되며, 다음 조건들을 만족해야 한다.

### A. Addition (덧셈)
$\forall u, v, w \in V$에 대하여:
1. **Closed under addition**: $u + v \in V$
2. **Commutative (교환 법칙)**: $u + v = v + u$
3. **Associative (결합 법칙)**: $(u + v) + w = u + (v + w)$
4. **Additive Identity (덧셈에 대한 항등원)**: $\exists 0_v \in V$ s.t. $u + 0_v = u$
5. **Additive Inverse (덧셈에 대한 역원)**: $\forall u \in V, \exists -u \in V$ s.t. $u + (-u) = 0_v$

### B. Scalar Multiplication (스칼라 곱)
$\forall c, d \in F, \forall u, v \in V$에 대하여:
1. **Closed under scalar multiplication**: $cu \in V$
2. **Multiplicative Identity**: $1 \cdot u = u$ (여기서 $1$은 Field $F$의 곱셈 항등원)
3. **Associativity**: $(cd)u = c(du)$
4. **Distributive Law (분배 법칙)**:
    * $c(u + v) = cu + cv$
    * $(c + d)u = cu + du$

---

## 2. Examples (예시)

1.  **n-tuples**: $F^n$ over $F$ (예: $\mathbb{R}^3$ over $\mathbb{R}$)
    * $u = (a_1, \dots, a_n), v = (b_1, \dots, b_n)$ 일 때,
    * $u+v = (a_1+b_1, \dots, a_n+b_n)$

2.  **Matrices**: $M_{m \times n}(F)$ (Matrix of $m \times n$)
    * $A, B \in M_{m \times n}(F), c \in F$
    * Addition: Matrix addition $(A+B)_{ij} = A_{ij} + B_{ij}$
    * Scalar Multiplication: $(cA)_{ij} = cA_{ij}$

3.  **Function Space**: $\mathcal{F}(S, F)$ (Set of all functions from $S$ to $F$)
    * $(f+g)(s) = f(s) + g(s)$
    * $(cf)(s) = c \cdot f(s)$

4.  **Polynomials**: $P(F)$ (Polynomials over field $F$)
    * $f(x) = a_n x^n + \dots + a_1 x + a_0$
    * $g(x) = b_n x^n + \dots + b_1 x + b_0$
    * Addition과 Scalar Multiplication은 다항식의 연산과 동일하게 정의됨.

---

## 3. Non-Example (반례)

$S = \{(a_1, a_2) : a_1, a_2 \in \mathbb{R}\}$ 에 대하여 다음과 같이 연산을 정의하면:
* Sum: $(a_1, a_2) + (b_1, b_2) = (a_1 + b_1, a_2 - b_2)$ (두 번째 성분을 뺌)
* Scalar Mul: $c(a_1, a_2) = (ca_1, ca_2)$

이 경우 **교환 법칙(Commutativity)**이 성립하지 않는다.
$$
(a_1, a_2) + (b_1, b_2) \neq (b_1, b_2) + (a_1, a_2)
$$
따라서 벡터 공간이 아니다.

---

## 4. Theorems (정리)

### Thm 1.1: Cancellation Law for Vector Addition
If $x, y, z \in V$ s.t. $x + z = y + z$, then $x = y$.

**Proof)**
$\exists v \in V$ s.t. $z + v = 0$ (Additive Inverse).
$$
\begin{aligned}
x &= x + 0 = x + (z + v) \\
  &= (x + z) + v \\
  &= (y + z) + v \\
  &= y + (z + v) \\
  &= y + 0 = y
\end{aligned}
$$
$\therefore x = y$

**Corollary 1:**
The vector $0$ (additive identity) and $-u$ (additive inverse of $u$) are **unique**.

### Thm 1.2: Properties
In any vector space $V$:
1.  $0x = 0$ for each $x \in V$
2.  $(-a)x = -(ax) = a(-x)$ for each $a \in F, x \in V$
3.  $a \cdot 0 = 0$ for each $a \in F$

**Proof of (a): $0x = 0$**
$$
0x = (0+0)x = 0x + 0x
$$
$$
0x + 0 = 0x + 0x
$$
By cancellation law (Thm 1.1), $0 = 0x$.

**Proof of (b): $(-a)x = -(ax)$**
We show that $ax + (-a)x = 0$.
$$
ax + (-a)x = (a + (-a))x = 0x = 0
$$
Since the inverse is unique, $(-a)x$ is the additive inverse of $ax$, which is $-(ax)$.