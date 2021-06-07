% Hereditarily Transitive Sets
% Sébastien Boisgérault, MINES ParisTech

## Notations 

  - The symbol $\varnothing$ denotes the empty set $\{\;\}$: $\forall x, \, x \not \in\varnothing$.

  - We use the ellipsis "$\dots$" to signify that a set may have more elements 
    than those explicitly listed : a "set with ellipsis" should 
    be interpreted as any superset of "the same set without ellipsis". 
    So we have for example
    $$
    \{x\} \subset \{x, \dots\}, \; \{x, y\} \subset \{x, y, \dots\}, \;
    \{x \;| \; x \in y\} \subset \{x, \dots \; | \; x \in y\},
    $$
    and the corresponding interpretation of equality
    $$
    z = \{x, \dots \} \; \longleftrightarrow \; \{x\} \subset z \; \longleftrightarrow \; x \in z,
    $$
    $$
    z = \{x, y, \dots \} \; \longleftrightarrow \; \{x, y\} \subset z \; \longleftrightarrow \; x \in z \wedge y \in z,
    $$
    $$
    z = \{x, \dots \; | \; x \in y\} \; \longleftrightarrow \; \{x \; | \; x \in y\} \subset z \; \longleftrightarrow \; y \subset z.
    $$



## Transitive sets

A set $z$ is *transitive* if 
$$
\forall x \, \forall y \, (x\in y \wedge y\in z) \rightarrow x \in z.
$$
We can use the abbreviation $x \in y \in z$ to denote 
$x\in y \wedge y\in z$ and make implicit the universal quantifiers $\forall x$
and $\forall y$ ; we then end up with the simple
$$
x \in y \in z \rightarrow x \in z.
$$
This property appears very similar to the concept of transitivity used in order theory: 
remember that if $x$, $y$ and $z$ are elements of a set endowed with a strict order $<$, 
transitivity of this relation means:
$$
x < y < z \rightarrow x < z.
$$
With ellipses, transitivity of $z$ reads:
$$
z = \{\{x,\dots\},\dots \} \rightarrow z = \{x, \dots\}.
$$
Note that the element of an element of an element of a transitive
set is also an element of the transitive set since
$$
x \in y \in w \in z \rightarrow x \in y \in z \rightarrow x \in z.
$$
or alternatively
$$
z = \{\{\{x,\dots\},\,\dots\},\dots \} 
\rightarrow z = \{\{x,\dots\},\dots \}
\rightarrow  z = \{x, \dots\}.
$$
This property can be generalized by induction to any chain of membership that
ends up in a transitive set $z$:

#### Transitivity runs deep
If $z$ is a transitive set then
$$
x_n \in x_{n-1} \in \dots \in x_0 = z \rightarrow x_n \in z.
$$

**TODO.** Transitivity and subsets

## Hereditarily transitive sets

A set $z$ is hereditarily transitive if it is transitive, all its elements are
transitive, all the elements of its elements are transitive, and so on, 
"all the way down". In other words, if for any integer $n$, 
$$
x_{n} \in x_{n-1} \in x_{n-2} \in \dots \in x_0 = z
\; \rightarrow \;
x_{n} \in x_{n-2}.
$$
Note that if $x_n \in x_{n-1} \in x_{n-2} \in \dots \in x_0$, 
we also have $x_n \in x_{n-2} \in x_{n-3} \in \dots \in x_0$ and thus
$x_{n} \in x_{n-3}$. More generally, by induction
$$
x_{n} \in x_{n-1} \in x_{n-2} \in \dots \in x_0
\; \rightarrow \;
x_{n} \in x_{n-1} \wedge x_{n} \in x_{n-2} \wedge \dots \wedge x_n \in x_0.
$$

Note that it is not necessary to explicitly check transitivity all the way down:

**TODO.** emphasize "deepness" of the terminology but only apparent, compare
with the situation for (simply) transitive, strees that we thus have an
alternate (shallow) definition:

#### Hereditarily transitive sets
A set is hereditarily transitive if and only if it is transitive and 
its elements are transitive.

**Proof.** The "only if" part of the result is obvious. For the "if" part, 
notice that if $z$ is transitive as well as its elements, then
$x_2 \in x_1 \in x_0 = z$
yields
$x_2 \in x_0 = z,$
thus $x_2$ is also transitive; by induction every $x_n$ such that 
$$
x_n \in x_{n-1} \in x_{n-2} \in \dots \in x_0 = z
$$
is actually transitive. $\blacksquare$


## Axiom of foundation {#axiom-foundation}

The axiom of foundation is usually formulated as
\begin{equation}
\forall x, \, (x\neq \varnothing \rightarrow \exists y'\in x, \, (y'\cap x=\varnothing))
\end{equation}
(see e.g. Rieger, quoted by Wikipedia). If we discard the use of the intersection
operator $\cap$ to rely only on $\in$, we obtain a reductionist version of the 
statement:
\begin{equation} \label{eq:AF2}
\forall x, \, (x\neq \varnothing \rightarrow \exists y'\in x, \, \forall y \in x, \, y \not \in y').
\end{equation}
or even
$$
\forall x, \, (x\neq \varnothing \rightarrow \exists y'\in x, \forall y \in x, \,   \forall z \in y',  \, y \neq z).
$$
Despite the verbosity, I used to find the latter version more illuminating, 
since it lends itself to an "explicitly expanded view" of the sets involved:
one can visualize a non-empty set $x$ as a collection of generic $y$'s; 
the axiom simply asserts that one of these $y$'s
can be expanded into $z$'s such that 
$$
x = \{y,\{z,\dots\},\dots\}
\, \rightarrow \,
y \neq z.
$$
This is used to be my go-to "mental model" for the axiom of foundation.
I found later that there is another formulation of the axiom that I can 
also work with and that it's especially useful in the context of hereditarily
transitive set. Its statement needs a bit of preparation however, so let's
get into it.

Consider $\in$ as a binary relation in a set $x$. The axiom of foundation
implies that $\in$ is *irreflexive*, which means that
$$
\forall y \in x, \, y \not \in y.
$$
Indeed, for any $y \in x$, since $x = \{y\}$ is not empty,
there is an element $y'$ of $\{y\}$ such that  $y' \cap x = y' \cap \{y\} = \varnothing$ ; 
but $y$ is the unique element of $\{y\}$, thus $y \cap \{y\} = \varnothing$ 
or equivalently, $y\not \in y$. Alternatively, the same conclusion can be drawn 
-- arguably more easily -- from the statement:
$$
x = \{y\} = \{\{z, \dots\}\} \rightarrow y \neq z.
$$

Additionally, if $x$ is a hereditarily transitive set, the relation $\in$ on $x$
is also *transitive* -- and since the term "transitive" refers to several concepts 
here, let us be clear that we mean *transitive as a binary relation on $x$*: 
$$
\forall y \in x, \, \forall z\in x, \, \forall t \in x,
\, (y \in z \wedge z \in t) \rightarrow y \in t. 
$$
Why? Because every element $t$ of $x$ is transitive (as in
*transitive set*) and thus
$$
\forall y, \, \forall z, \, \forall t \in x,
\, (y \in z \wedge z \in t) \rightarrow y \in t.
$$
The irreflexivity and transitivity of $\in$ makes it a (strict, partial) order on $x$.
And thus, we have a known concept of *minimality* associated with this
order: an element $y'$ of $x$ is ($\in$)-minimal if no element of $x$ is
($\in$)-smaller than $y'$. Which reads here $\forall y \in x, \, y \not \in y'.$
And thus the existence in $x$ of such a minimal element would be stated as
$$
\exists y'\in x, \, \forall y \in x, \, y \not \in y'.
$$
From the formulation \eqref{eq:AF2} of the axiom of foundation, 
we see that *every non-empty hierarchical set has a $\in$-minimal element*.
If you are familiar with the concept of minimality,
this is such a strikingly simple statement that you'd probably 
like to capitalize on this discovery.

And indeed, if we take a step back we realize that the definition of $\in$-minimality
does not require in any meaningful way that $\in$ should be a strict order.
Thus, we can extend our definition of the $\in$-minimality to any set $x$:
we will say that $y'\in x$ is $\in$-minimal in $x$ if 
$$
\forall y \in x, \, y \not \in y'.
$$ 
The axiom of foundation can then be re-stated as (see e.g. @Jec03)

#### Axiom of foundation 
Every non-empty set $x$ has a $\in$-minimal element.

## Hereditarily sets and ordinals

We say that the sets $x$ and $y$ are *comparable* if $x \in y$, $x=y$ or 
$y \in x$; otherwise, they are *incomparable*.

#### Lemma -- Comparability lift {#comparability-lift}

Two transitive sets $x$ and $y$ such that for 
every $w \in x$, $w$ and $y$ are comparable and for every $z \in y$, $z$ and $x$ 
are comparable, are comparable.

The following lemma and theorem are adapted from [@Sco14].

**Proof.** Let $w\in x$; since by assumption $w$ and $y$ are comparable, 
$w \in y$, $w=y$ or $y \in w$. If $w=y$ then $y \in x$ ; if $y \in w$, 
since $w \in x$ and $x$ is transitive, we also have $y\in x$. 
In each of these two cases, $x$ and $y$ are comparable as expected. 
Otherwise, for every $w \in x$, we have $w \in y$, that is $x \subseteq y$.

Similarly, we can infer that either $x$ and $y$ are comparable or for every 
$z \in y$, $z \in y$, and hence $y \subseteq z$.
In this latter case, since $x \subseteq y$ and $y \subseteq x$, we end up with 
$x=y$; in any case, $x$ and $y$ are comparable. $\blacksquare$

This lemma unlocks the following theorem:

### Theorem {#linear-order}
Membership orders linearly any hereditarily transitive set. 

**Proof.** We have already demonstrated in the ["axiom of foundation" section](#axiom-foundation) that membership if a (possibly partial) strict order in any hereditarily transitive
set $t$. 

We now prove that the order is total. Let's assume the opposite;
thus, the set of elements of that is incomparable with at least another
element of $z$ is not empty. Let $x$ be a $\in$-minimal element of this subset and 
let $y$ be a $\in$-minimal element of
the (also non-empty) subset of elements that cannot be compared to $x$.
By minimality of $x$, for every $w \in x$, $w$ is comparable to every element of 
$t$, thus $w$ is comparable to $y$ as a special case. 
By minimality of $y$, every $z \in y$ is also comparable with $x$. 
Thus, by the ["comparability lift" lemma](#comparability-lift), $x$ and $y$
are comparable and we have a contradiction.
$\blacksquare$

Remember the definition of a well-order:

#### Well-order {#well-order}
A *well-order* on a set is an order such that every non-empty subset has a
least element: the strict order $<$ well-orders the set $x$ if
$$
\forall y \subset x, \, (y \neq \varnothing \rightarrow \exists x \in y, \, \forall z \in y, \; 
x = z \vee x < z).
$$

Ordinals are often defined as a distinguished class of well-ordered sets.
This definition totally makes sense if you believe that ordinals shall 
first and foremost be used as canonical versions of well-ordered sets 
up to an isomorphism 
(the unique ordinal associated to a well-order being its *order type*). 
In this approach:

#### Ordinals {#ordinal}
A set is an *ordinal* if it is well-ordered by membership and transitive.

However, the theorem above leads to an alternate characterization:

#### Theorem
A set if an ordinal if and only if it is hereditarily transitive.

**Proof.** If the set $z$ is hereditarily transitive, then it is transitive.
Additionally, since every non-empty subset of $z$ has a $\in$-minimal element
by [the axiom of foundation](@axiom-foundation) and since [$\in$ is a linear
order on $z$](#linear-order), every non-empty subset has a least element for
$\in$. Hence $z$ is well-ordered and thus is an ordinal.

To establish the converse result, we prove that elements of ordinals are 
transitive sets. Let $z$ be an ordinal; if $w \in x \in y (\in z)$, 
then $y\in z$, $x\in z$ and $w \in z$ by transitivity of $z$. 
Since $\in$ (well-)orders $z$, it is transitive and $w \in y$. 
Thus $y$ is a transitive set.


## References