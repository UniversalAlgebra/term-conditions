---

## The Problem

- Can we efficiently decide whether a finite algebra $\mathbf{A}$ generates a variety with a difference term? <!-- .element: class="fragment" -->

- We give a positive answer in the idempotent case and describe an algorithm for constructing difference terms. <!-- .element: class="fragment" -->

---

## Definitions

<div class="fragment" align="left">A  <a style="color:#e7ad52">*difference term*</a> for $\mathcal V$ is a term $d$ satisfying,
  <p>
  for all $\mathbf A = \langle A, \dots \rangle \in \mathcal V$ and all $a, b \in A$, 
  </p>
  $$d(a,a,b) = b \quad \text{ and } \quad
  d(a,b,b) \mathrel{[\theta, \theta]} a$$
  </div>
  <br>
  <div class="fragment" align="left">where $\theta$ is any congruence containing $(a,b)$ and $[\cdot, \cdot]$ is the <a style="color:#e7ad52">*commutator*</a>.</div>


<aside class="notes"> When the relations above hold we call $d^{\mathbf{A}}$
a **difference term operation** for $\mathbf{A}$.
</aside>

<aside class="notes"> We make colors <span class="fragment highlight-red">like this</span></aside>

+++

## Problem Statement
<small>
<div class="fragment" align="left">
  Is there a poly-time algorithm that takes a finite
  idempotent algebra $\mathbf{A}$ and decides 
  whether $\mathbb{V}(\mathbf{A})$ has a difference term?
</div>

<p>

<div class="fragment" align="left">
  **Theorem** (Kearnes *J Algebra* 1995) 
  <br>
  <a style="color:#e7ad52">$\mathbb{V}(\mathbf{A})$ has a diff term</a>
  $\Leftrightarrow$ <a style="color:#e7ad52"> $\mathbb{V}(\mathbf{A})$ omits 1's and type 2 tails</a>
</div>

<p>

<div class="fragment" align="left">
  Omitting 1's is poly-time decidable by Valeriote's subtype theorem.
</div>

<p>

<div class="fragment" align="left">
  **Reduced Problem** <br>
  Is there a poly-time algorithm that takes a finite 
  idempotent algebra $\mathbf{A}$ and decides whether 
  $\mathbb{V}(\mathbf{A})$ has type 2 tails?
</div>
</small>

---

## A Related Problem

<div class="fragment" align="left">
**Theorem** (Freese, Valeriote *IJAC* 2009)<br>
  There is a poly-time algorithm that takes a finite
  idempotent algebra $\mathbf{A}$ and decides whether $\mathbb{V}(\mathbf{A})$ is 
  <a style="color:#e7ad52">*congruence-modular*</a>.
</div>

<div class="fragment" align="left">
  **Proof Idea**
  <small>
  <ul> 
    <li>Congruence-modularity is characterized by omitting 1's, 5's, and tails.</li>
    <li> Omitting 1's and 5's is poly-time decidable by the subtype theorem.</li>
    <li> If there is a tail in $\mathbb{V}(\mathbf{A})$, then there is a tail
         "near the bottom".</li>
  </ul>
  </small>
</div>

+++

## What is "near the bottom"?

<div class="fragment" align="left">
**Theorem.** Let $\mathbf{A}$ be a finite idempotent algebra and $T$ an order ideal in the
  lattice of types. Then $\mathbb{V}(\mathbf{A})$ omits $T$ iff $\mathsf{S}(\mathbf{A})$
  does.
  <p>
  For example, $\mathbb{V}(\mathbf{A})$ omits $\{1, 5\}$ iff $\mathsf{S}(\mathbf{A})$ 
  does.
  </p> 
</div>

<div class="fragment" align="left">
Freese and Valeriote prove
  <p>
  If $\mathbb{V}(\mathbf{A})$ omits $\{1, 5\}$, 
  then nontrivial tails occur in $\mathbb{V}(\mathbf{A})$ only if they occur
  in 3-generated subalgebras of $\mathbf{A}^2$.</p>
</div>

---

## Main Theorem

- Suppose $\mathbb{V}(\mathbf A)$ omits type 1 and contains a finite algebra $\mathbf{B}$ with a type 2 prime quotient $\alpha \prec \beta$ such that the $\langle \alpha, \beta \rangle$-minimal sets have non-empty tails. <!-- .element: class="fragment" -->
- Then there exists a 3-generated subalgebra of $\mathbf A \times \mathbf A$
  with this property. <!-- .element: class="fragment" -->
- **Conclusion:** to check for type 2 tails in $\mathbb{V}(\mathbf A)$, it
  suffices to look for them in 3-generated subalgebras of 
  $$\mathbf A \times \mathbf A$$.<!-- .element: class="fragment" -->

+++

## Proof Strategy

- WLOG $\mathbf{B}$ is a subdirect
  product of a finite subcollection of $\mathcal S$.  |
- Choose $n$ minimal such that for some $\mathbf{A}_0$,
  $\dots$, $\mathbf{A}_{n-1}$ in $\mathcal S$, there exists
  $\mathbf{B} \leq_{sd} \prod_{[n]} \mathbf{A}_i$
  with a prime quotient of type 2 whose minimal sets have tails. |
- Assuming $n > 1$, we prove that $n = 2$.

+++

- For this $n$, select the $\mathbf{A}_i$ and $\mathbf{B}$ so that $|B|$ 
  is as small as possible. |
- Let $\alpha \prec \beta$ be a prime quotient of $\mathbf{B}$ 
  of type~2 such that its minimal sets have
  non-empty tails, and choose $\beta$ minimal with this property. |
- By HM, this implies $\beta$ is join 
  irreducible and $\alpha$ is its unique subcover.
  Let $U$ be an $(\alpha, \beta)$-minimal set. 

+++

## Lemma 3.1

If $0$, $1 \in U$ such that $(0,1) \in \beta - \alpha$ and
$t$ be a member of the tail of $U$. Then $\beta$ is the 
congruence of $\mathbf{B}$
generated by the pair $(0,1)$ and $\mathbf{B}$ is generated 
by $\{0, 1, t\}$.

---

For $i \leq n$, let $\rho_i$ 
denote the kernel of the projection of $\mathbf{B}$ onto $\mathbf{A}_i$,
so $\mathbf{B} \cong \mathbf{A}_i/\rho_i$.
For a subset $\sigma \subseteq [n]$, define

$\rho_\sigma := \bigwedge_{j\in \sigma} \rho_j.$

Consequently,

$\rho_{[n]} = \bigwedge_{j\in [n]}\rho_j = 0_{B}$

By minimality of $n$ we know that the intersection of any  proper subset of the
$\rho_i$, $1 \leq i \leq n$ is strictly above $0_B$.  Thus,
$0_B < \rho_\sigma < 1_B$ for all 
$\emptyset \subset \sigma\subset [n]$
(by $\subset$ we mean \emph{proper} subset).

+++

## Lemma 3.2
  For every proper nonempty subset $\sigma \subset [n]$,
  either $\beta \leq \rho_\sigma$ or $\alpha \vee \rho_\sigma = 1_B$.

## Near Permutability Lemma

For all $\sigma \subset [n]$, all $v\in B$, and all $c\in body(U)$, we have
\begin{equation*}(v,c) \in \beta \circ \rho_\sigma \cap \rho_\sigma \circ \beta.\end{equation*}

## Lemma 3.3

1. There exists $0 \leq i < n$ such that $\alpha \vee \rho_i = 1_B$

2. There exists $i$ such that $\alpha \vee \rho_i < 1_B$.

+++

## Theorem 3.4

Let $\mathcal V$ be the variety generated by some finite set $\mathcal S$ of finite,
idempotent algebras that is closed under taking subalgebras. If $\mathcal V$
omits type 1 and some finite member of $\mathcal V$ has a prime quotient 
of type 2 whose minimal sets have non-empty tails, then there is some
3-generated algebra $\mathbf{B}$ with this property that belongs to $\mathcal S$ or 
is a subdirect product of two algebras from $\mathcal S$. 