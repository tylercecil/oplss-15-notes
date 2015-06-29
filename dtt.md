# Dependent Type Theory

## Day 1 --- _Computational Trinitarianism_
  - Abstraction; Strictures, not affordances; proof relevance; identity.
  - Boolean, Heyting Algebras
  - **Exercises**
    1. Show that every Heyting Algebra is Distributive.
    2. Show that in a Heyting Algebra the following hold:
       - Weakening:
         - $$X \le X \vee Y$$
         - $$X \vee Y \le X$$
       - Contraction
         - $$X <= X \wedge Y$$
       - Exchange
         - $$X \wedge Y \le Y \wedge X$$

## Day 2 --- _IPL and STT_
  - Intuitionistic Propositional Logic / Simple Type Theory
  - Analytic vs Synthetic Judgement
  - Families of Types
  - **Exercises** NOTE(dbp 2015-06-28): I couldn't find any.

## Day 3 -- _DTT_
  - Families of Types
  - Functionality / Functorality
  - Dependenty Type Theory (DTT)
  - **Exercises**
    1. What does this proof of $$\ex a,b irrational s.t. a^b \in Q$$
       actually say?

       Consider a = b = $$\sqrt{2}$$. Either $$\sqrt{2}^\sqrt{2}$$ is
       in Q or not. If it is, then we're done. Otherwise, let $$a =
       \sqrt{2}^\sqrt{2}$$ and $$b = \sqrt{2}$$. Then $$a^b = 2 \in
       Q$$. QED.
    2. NOTE(dbp 2015-06-28): I have an exercise relating to choosing
       z : Nat |- Seq z, with the prompt to write a program such
       that... And that's where it ends.
    3. Write $$EQ(n,m)$$ with `rec_nat` where the it should obey the
       following spec:

       ```
       EQ(0,0) = 1
       EQ(0,Succ _) = 0
       EQ(Succ _, 0) = 0
       EQ(Succ x, Succ y) = EQ(x,y)
       ```
    4. Write a proof term showing that for all `x:Nat`, `EQ(x,x)`.


## Day 4 --- _Proof Relevant Equality_
  - Proof Relevant Equality
  - Identification Type
  - **Exercises**
    1. Define the following `EQ` relations (the first is given as an example):
       - $$EQ_{AxB} = EQ_A x EQ_B = \lambda x. \lambda y. EQ_A(fst x, fst y) x EQ_B(snd x, snd y)$$
       - $$EQ_{A+B} = EQ_{A} + EQ_{B} = ?$$
       - $$EQ_{\Sigma x:A. B} = ?$$
       - $$EQ_{\Pi x:A. B} = ?$
    2. Prove the following:
       $$\Pi x:A. \Sigma y:B. R(x,y) \rightarrow \Sigma f : A -> B. \Pi x:A R(x, y x)$$


## Day 5 --- _Identification Types_
  - Identification is an Equivalence Relation
  - Identification is an $$\infty$$-groupoi
  - Interval
  - **Exercises**
    1. NOTE(dbp 2015-06-28): I'm not totally sure what this exercise
       is. It has to do with $$ap_f$$ - I just have something boxed
       and the word "exercise" written below.
    2. Show groupoid laws by identification induction:
       - $$unit_L : refl(M) \dot \alpha =_{M=_AN} \alpha$$
       - $$unit_R : \alpha =_{M=_AN} \alpha \dot refl(N)$$
       - $$inv_L : \alpha^{-1}\alpha =_{N=_AN} refl(N)$$
       - $$inv_R : \alpha\alpha^{-1} =_{M=_AM} refl(M)$$
       - $$assoc : \alpa \dot (\beta \gamma) =_{M=P} (\alpha \beta) \gamma$$
    3. Show $$Id_{AxB}(M,N) \cong Id_A(fst M, fst N) \times Id_B(snd M, snd N)$$
    4. Prove the following implication (using `happly`):
       $$Id_{A \rightarrow B}(f,g) \rightarrow \Pi_{x:A} f(x) =_{B} g(x)$$
    5. Prove the following implication:
       $$ \Pi_{x:A} f(x) =_{B} g(x) \rightarrow \Pi_{x,y:A} x =_A y \rightarrow f(x) =_B g(y)$$
