# Corollary 2.11 — Continuation-Logic Proof (Wittgenstein style)

## Game and goal

**Game:** Banach-space distance & decomposition game in a Banach space (E).
**Given:** Closed linear subspaces (G,L \subset E). Assume the hypotheses of Theorem 2.10, in particular **Property (13)** holds.
**Goal:** Prove there exists a constant (K>0) such that for all (x\in E),

$$\operatorname{dist}(x, G\cap L)\ \le\ K\bigl(\operatorname{dist}(x,G)+\operatorname{dist}(x,L)\bigr).
\tag{14}$$

---

## Rules (licensed moves)

**R1 — Infimum approximation (distance rule).**
If $\operatorname{dist}(x,G)=\inf_{g\in G}|x-g|$ and $\varepsilon>0$, then you may choose $a\in G$ with
$$|x-a|\le \operatorname{dist}(x,G)+\varepsilon.$$ 
Likewise for $L$.

**R2 — Property (13) (controlled decomposition rule).**
For every $z\in G+L$, there exist $a'\in G$, $b'\in L$ such that
$$z=a'+b',\qquad |a'|\le C|z|,\qquad |b'|\le C|z|$$
(Here $C$ is the constant from the hypotheses.)

**R3 — Triangle inequality (norm rule).**
$|u+v|\le |u|+|v|$ for all $u,v\in E$.

**R4 — Terminal $\varepsilon$-move.**
If for all $\varepsilon>0$, $A\le B + \alpha\varepsilon$, then $A\le B$.

---

## Proof as forced continuation

Fix $x\in E$ and $\varepsilon>0$.

### Board state after applying R1

By R1, choose:

* $a\in G$ such that $|x-a|\le \operatorname{dist}(x,G)+\varepsilon$,
* $b\in L$ such that $|x-b|\le \operatorname{dist}(x,L)+\varepsilon$.

### Recognize the trigger for R2

Consider
$$z := a-b$$.

Since $a\in G$ and $b\in L$, we have $z\in G+L$, so R2 applies.



### Apply R2 (controlled decomposition)

By R2, there exist $a'\in G$, $b'\in L$ such that
$$a-b = a' + b',\qquad |a'|\le C|a-b|,\qquad |b'|\le C|a-b|.
\tag{*}$$



### Construct an element of $G\cap L$

Rearrange $a-b=a'+b'$ into:
$$a-a' = b+b'.
\tag{**}$$

* Because $a,a'\in G$, we get $a-a'\in G$.
* Because $b,b'\in L$, we get $b+b'\in L$.
* By (**), these are the same vector, hence
  $$
  y := a-a' \in G\cap L.
  $$

### Bound the distance to $G\cap L$ using this candidate

By definition of distance as an infimum and since $y\in G\cap L$,
$$
\operatorname{dist}(x,G\cap L)\le |x-y| = |x-(a-a')|.
\tag{1}
$$

> **Misuse alert (important):**
> From “$y\in G\cap L$” you may conclude $\operatorname{dist}(x,G\cap L)\le |x-y|$,
> but you may **not** conclude $|x-y|\le \operatorname{dist}(x,G\cap L)+\varepsilon$ unless $y$ was chosen by R1 *inside $G\cap L$*. Here $y$ is constructed, not chosen as an $\varepsilon$-minimizer.

Now apply R3:
$$
|x-(a-a')|\le |x-a| + |a'|.
\tag{2}
$$

Using (*) and then R3 again,
$$
|a'|\le C|a-b|
\le C(|a-x|+|x-b|)=C(|x-a|+|x-b|).
\tag{3}
$$

Combine (1)(2)(3):
$$
\operatorname{dist}(x,G\cap L)
\le |x-a| + C(|x-a|+|x-b|)
= (1+C)|x-a| + C|x-b|.
\tag{4}
$$

### Substitute the $\varepsilon$-approximations from R1

By the choices of $a$ and $b$,
$$
|x-a|\le \operatorname{dist}(x,G)+\varepsilon,\qquad
|x-b|\le \operatorname{dist}(x,L)+\varepsilon.
$$

Plug into (4):
$$
\operatorname{dist}(x,G\cap L)
\le (1+C)\bigl(\operatorname{dist}(x,G)+\varepsilon\bigr)

* C\bigl(\operatorname{dist}(x,L)+\varepsilon\bigr).
$$

So
$$
\operatorname{dist}(x,G\cap L)
\le (1+C)\operatorname{dist}(x,G)+C\operatorname{dist}(x,L) + (1+2C)\varepsilon.
\tag{5}
$$


Finally, note that
$$
(1+C)\operatorname{dist}(x,G)+C\operatorname{dist}(x,L)
\le (1+C)\bigl(\operatorname{dist}(x,G)+\operatorname{dist}(x,L)\bigr).
$$

Thus from (5),
$$
\operatorname{dist}(x,G\cap L)
\le (1+C)\bigl(\operatorname{dist}(x,G)+\operatorname{dist}(x,L)\bigr)
* (1+2C)\varepsilon.
\tag{6}
$$





### Terminal move

Since $\varepsilon>0$ was arbitrary, apply R4 to (6) to obtain:
$$
\operatorname{dist}(x,G\cap L)
\le (1+C)\bigl(\operatorname{dist}(x,G)+\operatorname{dist}(x,L)\bigr).
$$

This proves (14) with $K := 1+C$. ∎

---

## Wittgenstein-style notes on why this format is “understanding = knowing how to go on”

* Every step is a **trigger → move** transition (“I see $(a-b)$ with $a\in G, b\in L$ ⇒ R2 applies”).
* We explicitly prevented a common “looks plausible but illegal” step at the distance line (the exact misuse you had).
* The proof becomes a reusable **policy** for a whole class of problems, matching your checklist’s “forced continuation without prompts” criterion .

If you want, next I can compress this into a **template** you can reuse for olympiad proofs (“Board / Rules / Trigger / Move / Misuse alert / Terminal move”), so you can write in this style quickly without it becoming verbose.

