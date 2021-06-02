% Hereditarily Transitive Sets
% Sébastien Boisgérault, MINES ParisTech

A set $z$ is *transitive* if 

$\forall x \, \forall y \, (x\in y \wedge y\in z) \rightarrow x \in z$


Most syntactically convenient version:
$$
x \in y \in z \rightarrow x \in z.
$$


### Axiom of foundation

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
x = \{\dots, y\dots, \{\dots, z,\dots\},\dots\}
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
x = \{y\} = \{\{\dots, z, \dots\}\} \rightarrow y \neq z.
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
The axiom of foundation can then be re-stated as

**Axiom of foundation.** Every non-empty set $x$ has a $\in$-minimal element.

**TODO.** find reference where this version of the axiom of foundation is used (Jech ?)