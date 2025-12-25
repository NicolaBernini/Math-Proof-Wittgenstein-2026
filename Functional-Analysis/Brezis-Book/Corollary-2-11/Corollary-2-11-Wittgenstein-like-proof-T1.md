# Corollary 2.11 - Wittgenstein like Proof


# Proof

## Start 

Start by listing the elements core elements

- Banach Space $E$ inside which we have

  - points $x \in E$
  - closed linear subspaces $G, L \subset E$
  - Distance
- Property 13 that states that $\forall z \in G + L$ admits a decomposition of this kind $\exists x \in G, \exists y \in L, \exists C > 0 : z = x + y \quad ||x|| \le C || z ||, ||y|| \le C ||z||$


Recall that we have 2 different types of distance

- Point to Point distance: $d(x,y)$ and
- Point to Space distance: $d(x, G$)

  - Recall that in infinite dimensions the point to space distance requires the infimum, not the minimum like in finite dimensions

    - NOTEs

      - Practically, it means that it might not exist $a \in G$ such that $d(x, G) = || x - a ||$ (which would be the case if the minimum was used instead of the infimum) but it means that given a $\epsilon > 0$ then $\exists a \in G : d(x, G) \le || x - a || \le d(x, G) + \epsilon$
      - This is true because $d(x, G)$ is defined as the infimum amomg all points in $G$
      - This is key since it defines one of the "legal moves" in the proof


## Step 1

We know the proof is about distance so let's develop distance relationship

Let's use the infimum distance aspect mentioned above so we have this sequence of legal moves


S1) Pick $x \in E$

S2) Pick $\epsilon > 0$ then

S3) Use the relationship above

S3.1) $\exists a \in G : || x - a || \le d(x, G) + \epsilon$

S3.2) $\exists b \in L : || x - b || \le d(x, L) + \epsilon$ 



## Step 2

We now have 2 new elements $a,b$ and we need to understand how to continue on them

We can study their difference $z = a - b$

We recognize $z \in G + L$ and because of this we recognize that we can apply Property 13 to it and this allows us to introduce some new elements from the related decomposition, that are

$z = a' + b' \quad a' \in G, b' \in L \quad || a' || \le C || z ||, || b' || \le C || z ||$


The new elements are $a', b', C$


Let's continue with them


## Step 3

Let's study the $a', b'$ new elements now

Let's write them in one relationship we have them

$ z = a - b = a' + b'$


Can we now create new elements and continue on them?

Yes, by manipulating this new relationship



## Step 4

Let's manipulate the last equation to create new elements

$\Delta a = a - a' = b + b'$


How can we continue?

Let's analyse what sub-space it belongs to


## Step 5

Since $a \in G, a' \in G$ then $(a - a') \in G$ and

Since $b \in L, b' \in L$ then $(a - a') \in L$


Interestingly we found that $(a - a') \in G \cap L$


Also we notice this is part of what we need to prove

How can we continue on $(a - a')$ ?

The most natural next step is to study the relationship with the element that is part of the thereom claim, meaning the relationshi between $(a - a')$ and $d(x, G \cap L)$



## Step 6

Since we know that $(a - a') \in G \cap L$ and we recall the notion of distance in infinite space involves the infimum then we use it again here

$d(x, G \cap L) \le || x - (a - a') || \le d(x, G \cap L) + \epsilon$


Let's focus on the left term since it is the one in the Proof Claim, so we break the norm 

$d(x, G \cap L) \le || x - (a - a') || \le || x - a || + || a' ||$


How do we continue here?

We recall that we have an equation for $|| a' ||$ and specifically $|| a' || \le C ||a-b||$ so putting this altogether 

$d(x, G \cap L) \le || x - a || + C ||a-b||$


Now this is a pretty tricky part, since it is not so obvious to see how to continue



## Step 7

Let's continue by focusing on the 3 points we have now: $x,a,b$

They form a triangle in the space and $|| a- b||$ is the length of one of its legs, the other legs have length $|| x - a ||$ and $|| x - b ||$ and by the triangular inequality we have $|| a - b|| \le  || x - a || + || x - b ||$

This can be plugged into the previous relationship so we have

$d(x, G \cap L) \le || x - a || + C (||x-a|| + ||x-b||)$


Now continuation is simple algebra

$d(x, G \cap L) \le (1 + C)|| x - a || + C ||x-b||$



## Step 8

Now the continuation is dictated by the only link we have for $||x-a||$
and $||x-b||$ which regards the point to subspace distance

$d(x, G \cap L) \le (1 + C)(d(x, G) + \epsilon) + C(d(x, L) + \epsilon)$ 


Continuation is simple algebra

$d(x, G \cap L) \le (1 + C)d(x, G) + (1 + C) \epsilon + Cd(x, L) + C \epsilon$ 


and

$d(x, G \cap L) \le (1 + C)d(x, G) + Cd(x, L) + (1 + 2C)\epsilon$



## Step 9

Let's continue by making $C$ slightly larger so that we can group the 2 distance

$d(x, G \cap L) \le C(d(x, G) + d(x, L)) + (1 + 2C)\epsilon$ 


Notice this is a legit move because it preserves the inequality (we do not need equality)



## Step 10

Let's close the game by $\epsilon \rightarrow 0$ and we have the proof

$d(x, G \cap L) \le C(d(x, G) + d(x, L))$









