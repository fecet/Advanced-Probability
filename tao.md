
 Starting this week, I will be teaching an [introductory graduate course (Math 275A)](https://ccle.ucla.edu/mod/page/view.php?id=834267) on probability theory here at UCLA. While I find myself *using* probabilistic methods routinely nowadays in my research (for instance, the probabilistic concept of [Shannon entropy](https://en.wikipedia.org/wiki/Entropy_(information_theory)) played a crucial role in my [recent paper on the Chowla and Elliott conjectures](https://terrytao.wordpress.com/2015/09/18/the-logarithmically-averaged-chowla-and-elliott-conjectures-for-two-point-correlations-the-erdos-discrepancy-problem/), and random multiplicative functions similarly played a central role in the [paper on the Erdos discrepancy problem](https://terrytao.wordpress.com/2015/09/11/the-erdos-discrepancy-problem-via-the-elliott-conjecture/)), this will actually be the first time I will be *teaching* a course on probability itself (although I did give a [course on random matrix theory](https://terrytao.wordpress.com/category/teaching/254a-random-matrices/) some years ago that presumed familiarity with graduate-level probability theory). As such, I will be relying primarily on an existing textbook, in this case Durrett’s [Probability: Theory and Examples](http://www.math.duke.edu/~rtd/PTE/PTE4_1.pdf). I still need to prepare lecture notes, though, and so I thought I would continue my practice of putting my notes online, although in this particular case they will be less detailed or complete than with other courses, as they will mostly be focusing on those topics that are not already comprehensively covered in the text of Durrett. Below the fold are my first such set of notes, concerning the classical measure-theoretic foundations of probability. (I wrote on these foundations also in [this previous blog post](https://terrytao.wordpress.com/2010/01/01/254a-notes-0-a-review-of-probability-theory/), but in that post I already assumed that the reader was familiar with measure theory and basic probability, whereas in this course not every student will have a strong background in these areas.)

Note: as this set of notes is primarily concerned with foundational issues, it will contain a large number of pedantic (and nearly trivial) formalities and philosophical points. We dwell on these technicalities in this set of notes primarily so that they are out of the way in later notes, when we work with the actual mathematics of probability, rather than on the supporting foundations of that mathematics. In particular, the excessively formal and philosophical language in this set of notes will not be replicated in later notes.


##  —  1. Some philosophical generalities  — 

By default, mathematical reasoning is understood to take place in a *deterministic* mathematical universe. In such a universe, any given mathematical statement ${S}$ (that is to say, a sentence with no free variables) is either true or false, with no intermediate truth value available. Similarly, any deterministic variable ${x}$ can take on only one specific value at a time.

However, for a variety of reasons, both within pure mathematics and in the applications of mathematics to other disciplines, it is often desirable to have a rigorous mathematical framework in which one can discuss *non-deterministic* statements and variables – that is to say, statements which are not always true or always false, but in some intermediate state, or variables that do not take one particular value or another with definite certainty, but are again in some intermediate state. In probability theory, which is by far the most widely adopted mathematical framework to formally capture the concept of non-determinism, non-deterministic statements are referred to as *events*, and non-deterministic variables are referred to as *random variables*. In the standard foundations of probability theory, as laid out by Kolmogorov, we can then *model* these events and random variables by introducing a [sample space](https://en.wikipedia.org/wiki/Sample_space) (which will be given the structure of a [probability space](https://en.wikipedia.org/wiki/Probability_space)) to capture all the ambient sources of randomness; events are then modeled as measurable subsets of this sample space, and random variables are modeled as measurable functions on this sample space. (We will briefly discuss a more abstract way to set up probability theory, as well as other frameworks to capture non-determinism than classical probability theory, at the end of this set of notes; however, the rest of the course will be concerned exclusively with classical probability theory using the orthodox Kolmogorov models.)

Note carefully that sample spaces (and their attendant structures) will be used to *model* probabilistic concepts, rather than to actually *be* the concepts themselves. This distinction (a mathematical analogue of the [map-territory](https://en.wikipedia.org/wiki/Map%E2%80%93territory_relation) distinction in philosophy) actually is implicit in much of modern mathematics, when we make a distinction between an abstract version of a mathematical object, and a concrete representation (or *model*) of that object. For instance: 

-  In linear algebra, we distinguish between an [abstract vector space](https://en.wikipedia.org/wiki/Vector_space) ${V}$, and a concrete system of coordinates ${\phi: V \rightarrow {\bf R}^n}$ given by some [basis](https://en.wikipedia.org/wiki/Basis_(linear_algebra)) of ${V}$. 
-  In group theory, we distinguish between an [abstract group](https://en.wikipedia.org/wiki/Group_(mathematics)) ${G}$, and a concrete [representation of that group](https://en.wikipedia.org/wiki/Group_representation) ${\phi: G \rightarrow {Aut}(X)}$ as isomorphisms on some space ${X}$. 
-  In differential geometry, we distinguish between an [abstract manifold](https://en.wikipedia.org/wiki/Manifold) ${M}$, and a concrete [atlas of coordinate systems](https://en.wikipedia.org/wiki/Atlas_(topology)) that coordinatises that manifold. 
-  Though it is rarely mentioned explicitly, the abstract [number systems](https://en.wikipedia.org/wiki/Number#Classification) such as ${{\bf N}, {\bf Z}, {\bf Q}, {\bf R}, {\bf C}}$ are distinguished from the concrete [numeral systems](https://en.wikipedia.org/wiki/Numeral_system) (e.g. the decimal or binary systems) that are used to represent them (this distinction is particularly useful to keep in mind when faced with the [infamous identity](https://en.wikipedia.org/wiki/0.999...) ${0.999\dots = 1}$, or when switching from one numeral representation system to another).
 The distinction between abstract objects and concrete models can be fairly safely discarded if one is only going to use a single model for each abstract object, particularly if that model is “canonical” in some sense. However, one needs to keep the distinction in mind if one plans to switch between different models of a single object (e.g. to perform change of basis in linear algebra, change of coordinates in differential geometry, or [base change](https://en.wikipedia.org/wiki/Base_change) in algebraic geometry). As it turns out, in probability theory it is often desirable to change the sample space model (for instance, one could *extend* the sample space by adding in new sources of randomness, or one could couple together two systems of random variables by *joining* their sample space models together). Because of this, we will take some care in this foundational set of notes to distinguish probabilistic concepts (such as events and random variables) from their sample space models. (But we may be more willing to conflate the two in later notes, once the foundational issues are out of the way.)

From a foundational point of view, it is often logical to begin with some axiomatic description of the abstract version of a mathematical object, and discuss the concrete representations of that object later; for instance, one could start with the axioms of an abstract group, and then later consider concrete representations of such a group by permutations, invertible linear transformations, and so forth. This approach is often employed in the more algebraic areas of mathematics. However, there are at least two other ways to present these concepts which can be preferable from a pedagogical point of view. One way is to start with the concrete representations as motivating examples, and only later give the abstract object that these representations are modeling; this is how linear algebra, for instance, is often taught at the undergraduate level, by starting first with ${{\bf R}^2}$, ${{\bf R}^3}$, and ${{\bf R}^n}$, and only later introducing the abstract vector spaces. Another way is to avoid the abstract objects altogether, and focus exclusively on concrete representations, but taking care to emphasise how these representations transform when one switches from one representation to another. For instance, in general relativity courses in undergraduate physics, it is not uncommon to see tensors presented purely through the concrete representation of coordinates indexed by multiple indices, with the transformation of such tensors under changes of variable carefully described; the abstract constructions of tensors and tensor spaces using operations such as tensor product and duality of vector spaces or vector bundles are often left to an advanced differential geometry class to set up properly.

The foundations of probability theory are usually presented (almost by default) using the last of the above three approaches; namely, one talks almost exclusively about sample space models for probabilistic concepts such as events and random variables, and only occasionally dwells on the need to extend or otherwise modify the sample space when one needs to introduce new sources of randomness (or to forget about some existing sources of randomness). However, much as in differential geometry one tends to work with manifolds without specifying any given atlas of coordinate charts, in probability one usually manipulates events and random variables without explicitly specifying any given sample space. For a student raised exclusively on concrete sample space foundations of probability, this can be a bit confusing, for instance it can give the misconception that any given random variable is somehow associated to its own unique sample space, with different random variables possibly living on different sample spaces, which often leads to nonsense when one then tries to combine those random variables together. Because of such confusions, we will try to take particular care in these notes to separate probabilistic concepts from their sample space models.
##  —  2. A simple class of models: discrete probability spaces  — 

The simplest models of probability theory are those generated by *discrete probability spaces*, which are adequate models for many applications (particularly in combinatorics and other areas of discrete mathematics), and which already capture much of the essence of probability theory while avoiding some of the finer measure-theoretic subtleties. We thus begin by considering discrete sample space models.
> ### Definition 1 (Discrete probability theory)
>   A *discrete probability space* ${\Omega = (\Omega, (p_\omega)_{\omega \in \Omega})}$ is an at most countable set ${\Omega}$ (whose elements ${\omega \in \Omega}$ will be referred to as *outcomes*), together with a non-negative real number ${p_\omega}$ assigned to each outcome ${\omega}$ such that ${\sum_{\omega \in \Omega} p_\omega = 1}$; we refer to ${p_\omega}$ as the *probability* of the outcome ${\omega}$. The set ${\Omega}$ itself, without the structure ${(p_\omega)_{\omega \in \Omega}}$, is often referred to as the *sample space*, though we will often abuse notation by using the sample space ${\Omega}$ to refer to the entire discrete probability space ${(\Omega, (p_\omega)_{\omega \in \Omega})}$.
In discrete probability theory, we choose an ambient discrete probability space ${\Omega}$ as the randomness model. We then model *events* ${E}$ by subsets ${E_\Omega}$ of the sample space ${\Omega}$. The *probability* ${{\bf P}(E)}$ of an event ${E}$ is defined to be the quantity $$\displaystyle  {\bf P}(E) := \sum_{\omega \in E_\Omega} p_\omega;$$ note that this is a real number in the interval ${[0,1]}$. An event ${E}$ is *surely true* or is the *sure event* if ${E_\Omega = \Omega}$, and is *surely false* or is the *empty event* if ${E_\Omega =\emptyset}$.
We model random variables ${X}$ taking values in the range ${R}$ by functions ${X_\Omega: \Omega \rightarrow R}$ from the sample space ${\Omega}$ to the range ${R}$. Random variables taking values in ${{\bf R}}$ will be called *real random variables* or *random real numbers*. Similarly for random variables taking values in ${{\bf C}}$. We refer to real and complex random variables collectively as *scalar random variables*.

We consider two events ${E,F}$ to be equal if they are modeled by the same set: ${E=F \iff E_\Omega = F_\Omega}$. Similarly, two random variables ${X,Y}$ taking values in a common range ${R}$ are considered to be equal if they are modeled by the same function: ${X=Y \iff X_\Omega = Y_\Omega}$. In particular, if the discrete sample space ${\Omega}$ is understood from context, we will usually abuse notation by identifying an event ${E}$ with its model ${E_\Omega}$, and similarly identify a random variable ${X}$ with its model ${X_\Omega}$. 

> ### Remark 2
>   One can view classical (deterministic) mathematics as the special case of discrete probability theory in which ${\Omega}$ is a singleton set (there is only one outcome ${\omega}$), and the probability assigned to the single outcome ${\omega}$ in ${\Omega}$ is ${1}$: ${p_\omega = 1}$. Then there are only two events (the surely true and surely false events), and a random variable in ${R}$ can be identified with a deterministic element of ${R}$. Thus we can view probability theory as a generalisation of deterministic mathematics. 


As discussed in the preceding section, the distinction between a collection of events and random variable and its models becomes important if one ever wishes to modify the sample space, and in particular to *extend* the sample space to a larger space that can accommodate new sources of randomness (an operation which we will define formally later, but which for now can be thought of as an analogue to change of basis in linear algebra, coordinate change in differential geometry, or [base change](https://en.wikipedia.org/wiki/Base_change) in algebraic geometry). This is best illustrated with a simple example.
> ### Example 3 (Extending the sample space)
>   Suppose one wishes to model the outcome ${X}$ of rolling a single, unbiased six-sided die using discrete probability theory. One can do this by choosing the discrete proability space ${\Omega}$ to be the six-element set ${\{1,2,3,4,5,6\}}$, with each outcome ${i \in \{1,2,3,4,5,6\}}$ given an equal probability of ${p_i := 1/6}$ of occurring; this outcome ${i}$ may be interpreted as the state in which the die roll ${X}$ ended up being equal to ${i}$. The outcome ${X}$ of rolling a die may then be identified with the identity function ${X_\Omega: \Omega \rightarrow \{1,\dots,6\}}$, defined by ${X_\Omega(i) := i}$ for ${i \in \Omega}$. If we let ${E}$ be the event that the outcome ${X}$ of rolling the die is an even number, then with this model ${\Omega}$ we have ${E_\Omega = \{2,4,6\}}$, and $$\displaystyle  {\bf P}(E) = \sum_{\omega \in E_\Omega} p_\omega = 3 \times \frac{1}{6} = \frac{1}{2}.$$ Now suppose that we wish to roll the die again to obtain a second random variable ${Y}$. The sample space ${\Omega = \{1,2,3,4,5,6\}}$ is inadequate for modeling both the original die roll ${X}$ and the second die roll ${Y}$. To accommodate this new source of randomness, we can then move to the larger discrete probability space ${\Omega' := \{1,\dots,6\} \times \{1,\dots,6\}}$, where each outcome ${(i,j) \in \Omega'}$ now having probability ${p'_{(i,j)} := \frac{1}{36}}$; this outcome ${(i,j)}$ can be interpreted as the state in which the die roll ${X}$ ended up being ${i}$, and the die roll ${Y}$ ended up being ${j}$. The random variable ${X}$ is now modeled by a new function ${X_{\Omega'}: \Omega' \rightarrow \{1,\dots,6\}}$ defined by ${X_{\Omega'}(i,j) := i}$ for ${(i,j) \in \Omega'}$; the random variable ${Y}$ is similarly modeled by the function ${Y_{\Omega'}: \Omega' \rightarrow \{1,\dots,6\}}$ defined by ${Y_{\Omega'}(i,j) := j}$ for ${(i,j) \in \Omega'}$. The event ${E}$ that ${X}$ is even is now modeled by the set $$\displaystyle  E_{\Omega'} = \{2,4,6\} \times \{1,2,3,4,5,6\}.$$ This set is distinct from the previous model ${E_\Omega}$ of ${E}$ (for instance, ${E_{\Omega'}}$ has eighteen elements, whereas ${E_\Omega}$ has just three), but the probability of ${E}$ is unchanged: $$\displaystyle  {\bf P}(E) = \sum_{\omega' \in E_{\Omega'}} p'_{\omega'} = 18 \times\frac{1}{36} = \frac{1}{2}.$$ One can of course also combine together the random variables ${X,Y}$ in various ways. For instance, the sum ${X+Y}$ of the two die rolls is a random variable taking values in ${\{2,\dots,12\}}$; it cannot be modeled by the sample space ${\Omega}$, but in ${\Omega'}$ it is modeled by the function $$\displaystyle  (X+Y)_{\Omega'}: (i,j) \mapsto i+j.$$ Similarly, the event ${X=Y}$ that the two die rolls are equal cannot be modeled by ${\Omega}$, but is modeled in ${\Omega'}$ by the set $$\displaystyle  (X=Y)_{\Omega'} = \{ (i,i): i=1,\dots,6\}$$ and the probability ${{\bf P}(X=Y)}$ of this event is $$\displaystyle  {\bf P}(X=Y) = \sum_{\omega' \in (X=Y)_{\Omega'}} p'_{\omega'} = 6 \times \frac{1}{36} = \frac{1}{6}.$$ We thus see that extending the probability space has also enlarged the space of events one can consider, as well as the random variables one can define, but that existing events and random variables continue to be interpretable in the extended model, and that probabilistic concepts such as the probability of an event remain unchanged by the extension of the model. 


The set-theoretic operations on the sample space ${\Omega}$ induce similar boolean operations on events:
-  The *conjunction* ${E \wedge F}$ of two events ${E,F}$ is defined through the intersection of their models: ${(E \wedge F)_\Omega := E_\Omega \cap F_\Omega}$. 
-  The *disjunction* ${E \vee F}$ of two events ${E,F}$ is defined through the the union of their models: ${(E \vee F)_\Omega := E_\Omega \cup F_\Omega}$. 
-  The *symmetric difference* ${E \Delta F}$ of two events ${E,F}$ is defined through the symmetric difference of their models: ${(E \Delta F)_\Omega := E_\Omega \Delta F_\Omega}$. 
-  The *complement* ${\overline{E}}$ of an event ${E}$ is defined through the complement of their models: ${\overline{E}_\Omega := \Omega \backslash E_\Omega}$. 
-  We say that one event ${E}$ is *contained in* or *implies* another event ${F}$, and write ${E \subset F}$, if we have containment of their models: ${E \subset F \iff E_\Omega \subset F_\Omega}$. We also write “${F}$ is true on ${E}$” synonymously with ${E \subset F}$. 
-  Two events ${E,F}$ are *disjoint* if their conjunction is the empty event, or equivalently if their models ${E_\Omega, F_\Omega}$ are disjoint.

Thus, for instance, the conjunction of the event that a die roll ${X}$ is even, and that it is less than ${3}$, is the event that the die roll is exactly ${2}$. As before, we will usually be in a situation in which the sample space ${\Omega}$ is clear from context, and in that case one can safely identify events with their models, and view the symbols ${\vee}$ and ${\wedge}$ as being synonymous with their set-theoretic counterparts ${\cup}$ and ${\cap}$ (this is for instance what is done in Durrett).

With these operations, the space of all events (known as the *event space*) thus has the structure of a [boolean algebra](https://en.wikipedia.org/wiki/Boolean_algebra) (defined below in Definition [4](#mesalg)). We observe that the probability ${{\bf P}}$ is *finitely additive* in the sense that 

$$\displaystyle  {\bf P}( E \vee F ) = {\bf P}(E) + {\bf P}(F)$$

 whenever ${E,F}$ are disjoint events; by induction this implies that 

$$\displaystyle  {\bf P}(E_1 \vee \dots \vee E_n) = {\bf P}(E_1) + \dots + {\bf P}(E_n)$$

 whenever ${E_1,\dots,E_n}$ are pairwise disjoint events. We have ${{\bf P}(\emptyset)=0}$ and ${{\bf P}(\overline{\emptyset})=1}$, and more generally 

$$\displaystyle  {\bf P}(\overline{E}) = 1 - {\bf P}(E)$$

 for any event ${E}$. We also have monotonicity: if ${E \subset F}$, then ${{\bf P}(E) \leq {\bf P}(F)}$.


Now we define operations on random variables. Whenever one has a function ${f: R \rightarrow S}$ from one range ${R}$ to another ${S}$, and a random variable ${X}$ taking values in ${R}$, one can define a random variable ${f(X)}$ taking values in ${S}$ by composing the relevant models: 

$$\displaystyle  f(X)_\Omega := f \circ X_\Omega,$$

 thus ${f(X)_\Omega}$ maps ${\omega}$ to ${f(X_\Omega(\omega))}$ for any outcome ${\omega \in \Omega}$. Given a finite number ${X_1,\dots,X_n}$ of random variables taking values in ranges ${R_1,\dots,R_n}$, we can form the joint random variable ${(X_1,\dots,X_n)}$ taking values in the Cartesian product ${R_1 \times \dots \times R_n}$ by concatenation of the models, thus 

$$\displaystyle  (X_1,\dots,X_n)_\Omega: \omega \mapsto ((X_1)_\Omega(\omega),\dots, (X_n)_{\Omega}(\omega)).$$

 Combining these two operations, given any function ${f: R_1 \times \dots \times R_n \rightarrow S}$ of ${n}$ variables in ranges ${R_1,\dots,R_n}$, and random variables ${X_1,\dots,X_n}$ taking values in ${R_1,\dots,R_n}$ respectively, we can form a random variable ${f(X_1,\dots,X_n)}$ taking values in ${S}$ by the formula 

$$\displaystyle  f(X_1,\dots,X_n)_\Omega: \omega \mapsto f((X_1)_\Omega(\omega),\dots, (X_n)_{\Omega}(\omega)).$$

 Thus for instance we can add, subtract, or multiply two scalar random variables to obtain another scalar random variable. 


A deterministic element ${x}$ of a range ${R}$ will (by abuse of notation) be identified with a random variable ${x}$ taking values in ${R}$, whose model in ${\Omega}$ is constant: ${x_\Omega(\omega) = x}$ for all ${\omega \in \Omega}$. Thus for instance ${37}$ is a scalar random variable.

Given a relation ${F: R_1 \times \dots \times R_n \rightarrow \{ { true}, { false}\}}$ on ${n}$ ranges ${R_1,\dots,R_n}$, and random variables ${X_1,\dots,X_n}$, we can define the event ${F(X_1,\dots,X_n)}$ by setting 

$$\displaystyle  F(X_1,\dots,X_n) :=\{ \omega \in \Omega: F((X_1)_\Omega(\omega),\dots,(X_n)_\Omega(\omega)) { true}\}. $$

 Thus for instance, for two real random variables ${X,Y}$, the event ${X > Y}$ is modeled as 

$$\displaystyle  (X>Y)_\Omega := \{ \omega \in \Omega: X_\Omega(\omega) > Y_\Omega(\omega) \}$$

 and the event ${X=Y}$ is modeled as 

$$\displaystyle  (X=Y)_\Omega := \{ \omega \in \Omega: X_\Omega(\omega) = Y_\Omega(\omega) \}.$$

 At this point we encounter a slight notational conflict between the dual role of the equality symbol ${=}$ as a logical symbol and as a binary relation: we are interpreting ${X=Y}$ both as an external equality relation between the two random variables (which is true iff the functions ${X_\Omega}$, ${Y_\Omega}$ are identical), and as an internal event (modeled by ${(X=Y)_\Omega}$). However, it is clear that ${X=Y}$ is true in the external sense if and only if the internal event ${X=Y}$ is surely true. As such, we shall abuse notation and continue to use the equality symbol for both the internal and external concepts of equality (and use the modifier “surely” for emphasis when referring to the external usage).


It is clear that any equational identity concerning functions or operations on deterministic variables implies the same identity (in the external, or surely true, sense) for random variables. For instance, the commutativity of addition ${x+y=y+x}$ for deterministic real numbers ${x,y}$ immediately implies the commutativity of addition: ${X+Y=Y+X}$ is surely true for real random variables ${X,Y}$; similarly ${X+0=X}$ is surely true for all scalar random variables ${X}$, etc.. We will freely apply the usual laws of algebra for scalar random variables without further comment.

Given an event ${E}$, we can associate the [indicator random variable](https://en.wikipedia.org/wiki/Indicator_function) ${1_E}$ (also written as ${{\bf I}(E)}$ in some texts) to be the unique real random variable such that ${1_E=1}$ when ${E}$ is true and ${1_E=0}$ when ${E}$ is false, thus ${(1_E)_\Omega(\omega)}$ is equal to ${1}$ when ${\omega \in E_\Omega}$ and ${0}$ otherwise. (The indicator random variable is sometimes called the *characteristic function* in analysis, and sometimes denoted ${\chi_E}$ instead of ${1_E}$, but we avoid using the term “characteristic function” here, as it will have an [unrelated but important meaning](https://en.wikipedia.org/wiki/Characteristic_function_(probability_theory)) in probability theory.) We record the trivial but useful fact that Boolean operations on events correspond to arithmetic manipulations on their indicators. For instance, if ${E,F}$ are events, we have 

$$\displaystyle  1_{E \wedge F} = 1_E 1_F$$

$$\displaystyle  1_{\overline{E}} = 1 - 1_E$$

 and the inclusion-exclusion principle 

 In particular, if the events ${E,F}$ are disjoint, then 

$$\displaystyle  1_{E \vee F} = 1_E + 1_F.$$

 Also note that ${E \subset F}$ if and only if the assertion ${1_E \leq 1_F}$ is surely true. We will use these identities and equivalences throughout the course without further comment.


Given a scalar random variable ${X}$, we can attempt to define the [expectation](https://en.wikipedia.org/wiki/Expected_value) ${{\bf E}(X)}$ through the model ${X_\Omega}$ by the formula 

$$\displaystyle  {\bf E}(X) := \sum_{\omega \in \Omega} X_\Omega(\omega) p_\omega.$$

 If the discrete sample space ${\Omega}$ is finite, then this sum is always well-defined and so every scalar random variable has an expectation. If however the discrete sample space ${\Omega}$ is infinite, the expectation may not be well defined. There are however two key cases in which one has a meaningful expectation. The first is if the random variable ${X}$ is *unsigned*, that is to say it takes values in the non-negative reals ${[0,+\infty)}$, or more generally in the extended non-negative real line ${[0,+\infty]}$. In that case, one can interpret the expectation ${{\bf E}(X)}$ as an element of ${[0,+\infty]}$. The other case is when the random variable ${X}$ is *absolutely integrable*, which means that the absolute value ${|X|}$ (which is an unsigned random variable) has finite expectation: ${{\bf E} |X| < \infty}$. In that case, the series defining ${{\bf E}(X)}$ is absolutely convergent to a real or complex number (depending on whether ${X}$ was a real or complex random variable.)


We have the basic link 

$$\displaystyle  {\bf P}(E) = {\bf E}(1_E)$$

 between probability and expectation, valid for any event ${E}$. We also have the obvious, but fundamentally important, property of *linearity of expectation*: we have 

$$\displaystyle  {\bf E}(cX) = c {\bf E}(X)$$

 and 

$$\displaystyle  {\bf E}(X+Y) = {\bf E}(X) + {\bf E}(Y)$$

 whenever ${c}$ is a scalar and ${X,Y}$ are scalar random variables, either under the assumption that ${c,X,Y}$ are all unsigned, or that ${X,Y}$ are absolutely integrable. Thus for instance by applying expectations to [(1)](#iep) we obtain the identity 

$$\displaystyle  {\bf P}(E \vee F) = {\bf P}(E) + {\bf P}(F) - {\bf P}(E \wedge F).$$


We close this section by noting that discrete probabilistic models stumble when trying to model *continuous* random variables, which take on an uncountable number of values. Suppose for instance one wants to model a random real number ${X}$ drawn uniformly at random from the unit interval ${[0,1]}$, which is an uncountable set. One would then expect, for any subinterval ${[a,b]}$ of ${[0,1]}$, that ${X}$ will fall into this interval with probability ${b-a}$. Setting ${a=b}$ (or, if one wishes instead, taking a limit such as ${b \rightarrow a^+}$), we conclude in particular that for any real number ${a}$ in ${[0,1]}$, that ${X}$ will equal ${a}$ with probability ${0}$. If one attempted to model this situation by a discrete probability model, we would find that each outcome ${\omega}$ of the discrete sample space ${\Omega}$ has to occur with probability ${p_\omega = 0}$ (since for each ${\omega}$, the random variable ${X}$ has only a single value ${X_\Omega(\omega)}$). But we are also requiring that the sum ${\sum_{\omega \in \Omega} p_\omega}$ is equal to ${1}$, a contradiction. In order to address this defect we must generalise from discrete models to more general probabilistic models, to which we now turn.
##  —  3. The Kolmogorov foundations of probability theory  — 

We now present the more general measure-theoretic foundation of Kolmogorov which subsumes the discrete theory, while also allowing one to model continuous random variables. It turns out that in order to perform sums, limits and integrals properly, the finite additivity property of probability needs to be amplified to *countable* additivity (but, as we shall see, *uncountable* additivity is too strong of a property to ask for).

We begin with the notion of a measurable space. (See also this [previous blog post](https://terrytao.wordpress.com/2010/09/25/245a-notes-3-integration-on-abstract-measure-spaces-and-the-convergence-theorems/), which covers similar material from the perspective of a real analysis graduate class rather than a probability class.)
> ### Definition 4 (Measurable space)
>   Let ${\Omega}$ be a set. A [Boolean algebra](https://en.wikipedia.org/wiki/Boolean_algebra) in ${\Omega}$ is a collection ${{\mathcal F}}$ of subsets of ${\Omega}$ which 
>-  contains ${\emptyset}$ and ${\Omega}$; 
>-  is closed under pairwise unions and intersections (thus if ${E,F \in {\mathcal F}}$, then ${E \cup F}$ and ${E \cap F}$ also lie in ${{\mathcal F}}$); and 
>-  is closed under complements (thus if ${E \in {\mathcal F}}$, then ${\Omega \backslash E}$ also lies in ${{\mathcal F}}$.
 (Note that some of these assumptions are redundant and can be dropped, thanks to [de Morgan’s laws](https://en.wikipedia.org/wiki/De_Morgan%27s_laws).) A [-algebra](https://en.wikipedia.org/wiki/Sigma-algebra) in ${\Omega}$ (also known as a ${\sigma}$-field) is a Boolean algebra ${{\mathcal F}}$ in ${\Omega}$ which is also 
>-  closed under countable unions and countable intersections (thus if ${E_1,E_2,E_3,\dots \in {\mathcal F}}$, then ${\bigcup_{n=1}^\infty E_n \in {\mathcal F}}$ and ${\bigcap_{n=1}^\infty E_n \in {\mathcal F}}$).
 Again, thanks to de Morgan’s laws, one only needs to verify closure under just countable union (or just countable intersection) in order to verify that a Boolean algebra is a ${\sigma}$-algebra. A *measurable space* is a pair ${(\Omega, {\mathcal F})}$, where ${\Omega}$ is a set and ${{\mathcal F}}$ is a ${\sigma}$-algebra in ${\Omega}$. Elements of ${{\mathcal F}}$ are referred to as *measurable sets* in this measurable space.
If ${{\mathcal F}, {\mathcal F}'}$ are two ${\sigma}$-algebras in ${\Omega}$, we say that ${{\mathcal F}}$ is *coarser than* ${{\mathcal F}'}$ (or ${{\mathcal F}'}$ is *finer than* ${{\mathcal F}}$) if ${{\mathcal F} \subset {\mathcal F}'}$, thus every set that is measurable in ${(\Omega,{\mathcal F})}$ is also measurable in ${(\Omega,{\mathcal F}')}$. 

> ### Example 5 (Trivial measurable space)
>   Given any set ${\Omega}$, the collection ${\{\emptyset, \Omega\}}$ is a ${\sigma}$-algebra; in fact it is the coarsest ${\sigma}$-algebra one can place on ${\Omega}$. We refer to ${(\Omega, \{\emptyset,\Omega\})}$ as the *trivial* measurable space on ${\Omega}$. 

> ### Example 6 (Discrete measurable space)
>   At the other extreme, given any set ${\Omega}$, the power set ${2^\Omega := \{ E: E \subset \Omega\}}$ is a ${\sigma}$-algebra (and is the finest ${\sigma}$-algebra one can place on ${\Omega}$). We refer to ${(\Omega, 2^\Omega)}$ as the *discrete* measurable space on ${\Omega}$. 

> ### Example 7 (Atomic measurable spaces)
>   Suppose we have a partition ${\Omega = \biguplus_{\alpha \in A} E_\alpha}$ of a set ${\Omega}$ into disjoint subsets ${E_\alpha}$ (which we will call *atoms*), indexed by some label set ${A}$ (which may be finite, countable, or uncountable). Such a partition defines a ${\sigma}$-algebra on ${\Omega}$, consisting of all sets of the form ${\bigcup_{\alpha \in B} E_\alpha}$ for subsets ${B}$ of ${A}$ (we allow ${B}$ to be empty); thus a set is measurable here if and only if it can be described as a union of atoms. One can easily verify that this is indeed a ${\sigma}$-algebra. The trivial and discrete measurable spaces in the preceding two examples are special cases of this atomic construction, corresponding to the trivial partition ${\Omega = \Omega}$ (in which there is just one atom ${\Omega}$) and the discrete partition ${\Omega = \biguplus_{x \in \Omega} \{x\}}$ (in which the atoms are individual points in ${\Omega}$). 

> ### Example 8
>   Let ${\Omega}$ be an uncountable set, and let ${{\mathcal F}}$ be the collection of sets in ${\Omega}$ which are either at most countable, or are cocountable (their complement is at most countable). Show that this is a ${\sigma}$-algebra on ${\Omega}$ which is non-atomic (i.e. it is not of the form of the preceding example). 

> ### Example 9 (Generated measurable spaces)
>   It is easy to see that if one has a non-empty family ${({\mathcal F}_\alpha)_{\alpha \in A}}$ of ${\sigma}$-algebras on a set ${\Omega}$, then their intersection ${\bigcap_{\alpha \in A} {\mathcal F}_\alpha}$ is also a ${\sigma}$-algebra, even if ${A}$ is uncountably infinite. Because of this, whenever one has an arbitrary collection ${{\mathcal A}}$ of subsets in ${\Omega}$, one can define the ${\sigma}$-algebra ${\langle {\mathcal A} \rangle}$ *generated* by ${{\mathcal A}}$ to be the intersection of all the ${\sigma}$-algebras that contain ${{\mathcal A}}$ (note that there is always at least one ${\sigma}$-algebra participating in this intersection, namely the discrete ${\sigma}$-algebra). Equivalently, ${\langle {\mathcal A} \rangle}$ is the coarsest ${\sigma}$-algebra that views every set in ${{\mathcal A}}$ as being measurable. (This is a rather indirect way to describe ${\langle {\mathcal A} \rangle}$, as it does not make it easy to figure out exactly what sets lie in ${\langle {\mathcal A} \rangle}$. There is a more direct description of this ${\sigma}$-algebra, but it requires the use of the [first uncountable ordinal](https://en.wikipedia.org/wiki/First_uncountable_ordinal); see Exercise 15 of [these notes](https://terrytao.wordpress.com/2010/09/25/245a-notes-3-integration-on-abstract-measure-spaces-and-the-convergence-theorems/).) In Durrett, the notation ${\sigma({\mathcal A})}$ is used in place of ${\langle {\mathcal A}\rangle}$. 

> ### Example 10 (Borel -algebra)
>   Let ${\Omega}$ be a topological space; to avoid pathologies let us assume that ${\Omega}$ is locally compact Hausdorff and ${\sigma}$-compact, though the definition below also can be made for more general spaces. For instance, one could take ${\Omega = {\bf R}^n}$ or ${\Omega = {\bf C}^n}$ for some finite ${n}$. We define the [Borel -algebra](https://en.wikipedia.org/wiki/Borel_set) on ${\Omega}$ to be the ${\sigma}$-algebra generated by the open sets of ${\Omega}$. (Due to our topological hypotheses on ${\Omega}$, the Borel ${\sigma}$-algebra is also generated by the compact sets of ${\Omega}$.) Measurable subsets in the Borel ${\sigma}$-algebra are known as *Borel sets*. Thus for instance open and closed sets are Borel, and countable unions and countable intersections of Borel sets are Borel. In fact, as a rule of thumb, any subset of ${{\bf R}^n}$ or ${{\bf C}^n}$ that arises from a “non-pathological” construction (not using the axiom of choice, or from a deliberate attempt to build a non-Borel set) can be expected to be a Borel set. Nevertheless, non-Borel sets exist in abundance if one looks hard enough for them, even without the axiom of choice; see for instance Exercise 16 of [this previous blog post](https://terrytao.wordpress.com/2010/09/25/245a-notes-3-integration-on-abstract-measure-spaces-and-the-convergence-theorems/). 


The following exercise gives a useful tool (somewhat analogous to mathematical induction) to verify properties regarding measurable sets in generated ${\sigma}$-algebras, such as Borel ${\sigma}$-algebras.
> ### Exercise 11
>   Let ${{\mathcal A}}$ be a collection of subsets of a set ${\Omega}$, and let ${P(E)}$ be a property of subsets ${E}$ of ${\Omega}$ (thus ${P(E)}$ is true or false for each ${E}$ in ${\Omega}$). Assume the following axioms: 
>-  ${P(\emptyset)}$ is true. 
>-  ${P(E)}$ is true for all ${E \in {\mathcal A}}$. 
>-  If ${E \subset \Omega}$ is such that ${P(E)}$ is true, then ${P(\Omega \backslash E)}$ is also true. 
>-  If ${E_1, E_2, \dots \subset \Omega}$ are such that ${P(E_n)}$ is true for all ${n}$, then ${P(\bigcup_n E_n)}$ is true.
 Show that ${P(E)}$ is true for all ${E \in \langle {\mathcal A} \rangle}$. (*Hint:* what can one say about ${\{ E \subset \Omega: P(E) { true}\}}$?) 


Thus, for instance, if a property of subsets of ${{\bf R}^n}$ is true for all open sets, and is closed under countable unions and complements, then it is automatically true for all Borel sets.
> ### Example 12 (Pullback)
>   Let ${(R, {\mathcal B})}$ be a measurable space, and let ${\phi: \Omega \rightarrow R}$ be any function from another set ${\Omega}$ to ${R}$. Then we can define the *pullback* ${\phi^*({\mathcal B})}$ of the ${\sigma}$-algebra ${{\mathcal B}}$ to be the collection of all subsets in ${\Omega}$ that are of the form ${\phi^{-1}(S)}$ for some ${S \in {\mathcal B}}$. This is easily verified to be a ${\sigma}$-algebra. We refer to the measurable space ${(\Omega, \phi^*({\mathcal B}))}$ as the pullback of the measurable space ${(R, {\mathcal B})}$ by ${\phi}$. Thus for instance an atomic measurable space on ${\Omega}$ generated by a partition ${\Omega = \biguplus_{\alpha \in A} E_\alpha}$ is the pullback of ${A}$ (viewed as a discrete measurable space) by the “colouring” map from ${\Omega}$ to ${A}$ that sends each element of ${E_\alpha}$ to ${\alpha}$ for all ${\alpha \in A}$. 

> ### Remark 13
>   In probabilistic terms, one can interpret the space ${\Omega}$ in the above construction as a sample space, and the function ${\phi}$ as some collection of “random variables” or “measurements” on that space, with ${R}$ being all the possible outcomes of these measurements. The pullback then represents all the “information” one can extract from that given set of measurements. 

> ### Example 14 (Product space)
>   Let ${(R_\alpha, {\mathcal B}_\alpha)_{\alpha \in A}}$ be a family of measurable spaces indexed by a (possibly infinite or uncountable) set ${A}$. We define the product ${(\prod_{\alpha \in A} R_\alpha, \prod_{\alpha \in A} {\mathcal B}_\alpha)}$ on the Cartesian product space ${\prod_{\alpha \in A} R_\alpha}$ by defining ${\prod_{\alpha \in A} {\mathcal B}_\alpha}$ to be the ${\sigma}$-algebra generated by the [basic cylinder sets](https://en.wikipedia.org/wiki/Cylinder_set) of the form $$\displaystyle  \{ (x_\alpha)_{\alpha \in A} \in \prod_{\alpha \in A} R_\alpha: x_\beta \in E_\beta \}$$ for ${\beta \in A}$ and ${E_\beta \in {\mathcal B}_\beta}$. For instance, given two measurable spaces ${(R_1, {\mathcal B}_1)}$ and ${(R_2, {\mathcal B}_2)}$, the product ${\sigma}$-algebra ${{\mathcal B}_1 \times {\mathcal B}_2}$ is generated by the sets ${E_1 \times R_2}$ and ${R_1 \times E_2}$ for ${E_1 \in {\mathcal B}_1, E_2 \in {\mathcal B}_2}$. (One can also show that ${{\mathcal B}_1 \times {\mathcal B}_2}$ is the ${\sigma}$-algebra generated by the products ${E_1 \times E_2}$ for ${E_1 \in {\mathcal B}_1, E_2 \in {\mathcal B}_2}$, but this observation does not extend to uncountable products of measurable spaces.) 

> ### Exercise 15
>   Show that ${{\bf R}^n}$ with the Borel ${\sigma}$-algebra is the product of ${n}$ copies of ${{\bf R}}$ with the Borel ${\sigma}$-algebra. 


As with almost any other notion of space in mathematics, there is a natural notion of a map (or *morphism*) between measurable spaces.
> ### Definition 16
>   A function ${\phi: \Omega \rightarrow R}$ between two measurable spaces ${(\Omega, {\mathcal F})}$, ${(R,{\mathcal B})}$ is said to be *measurable* if one has ${\phi^{-1}(S) \in {\mathcal F}}$ for all ${S \in {\mathcal B}}$. 


Thus for instance the pullback of a measurable space ${R}$ by a map ${\phi: \Omega \rightarrow R}$ could alternatively be defined as the coarsest measurable space structure on ${\Omega}$ for which ${\phi}$ is still measurable. It is clear that the composition of measurable functions is also measurable.
> ### Exercise 17
>   Show that any continuous map from one topological space ${X}$ to another ${Y}$ is necessarily measurable (when one gives ${X}$ and ${Y}$ the Borel ${\sigma}$-algebras). 

> ### Exercise 18
>   If ${X_1: \Omega \rightarrow R_1, \dots, X_n: \Omega \rightarrow R_n}$ are measurable functions into measurable spaces ${R_1,\dots,R_m}$, show that the joint function ${(X_1,\dots,X_n): \Omega \rightarrow R_1 \times \dots \times R_n}$ into the product space ${R_1 \times \dots \times R_n}$ defined by ${(X_1,\dots,X_n): \omega \mapsto (X_1(\omega),\dots,X_n(\omega))}$ is also measurable. 


As a corollary of the above exercise, we see that if ${X_1: \Omega \rightarrow R_1, \dots, X_n: \Omega \rightarrow R_n}$ are measurable, and ${F: R_1 \times \dots \times R_n \rightarrow S}$ is measurable, then ${F(X_1,\dots,X_n): \Omega \rightarrow S}$ is also measurable. In particular, if ${X_1, X_2: \Omega \rightarrow {\bf R}}$ or ${X_1,X_2: \Omega \rightarrow {\bf C}}$ are scalar measurable functions, then so are ${X_1 +X_2}$, ${X_1 - X_2}$, ${X_1 \cdot X_2}$, etc..

Next, we turn measurable spaces into measure spaces by adding a measure.
> ### Definition 19 (Measure spaces)
>   Let ${(\Omega, {\mathcal F})}$ be a measurable space. A *finitely additive measure* on this space is a map ${\mu: {\mathcal F} \rightarrow [0,+\infty]}$ obeying the following axioms: 
>-  (Empty set) ${\mu(\emptyset)=0}$. 
>-  (Finite additivity) If ${E, F \in {\mathcal F}}$ are disjoint, then ${\mu(E \cup F) = \mu(E) + \mu(F)}$.
 A [countably additive measure](https://en.wikipedia.org/wiki/Measure_(mathematics)) is a finitely additive measure ${\mu: {\mathcal F} \rightarrow [0,+\infty]}$ obeying the following additional axiom: 
>-  (Countable additivity) If ${E_1, E_2, E_3, \dots \in {\mathcal F}}$ are disjoint, then ${\mu(\bigcup_{n=1}^\infty E_n) = \sum_{n=1}^\infty \mu(E_n)}$.
 A [probability measure](https://en.wikipedia.org/wiki/Probability_measure) on ${\Omega}$ is a countably additive measure ${\mu: {\mathcal F} \rightarrow [0,+\infty]}$ obeying the following additional axiom: 
>-  (Unit total probability) ${\mu(\Omega)=1}$.
 A [measure space](https://en.wikipedia.org/wiki/Measure_(mathematics)#measure_space) is a triplet ${\Omega = (\Omega, {\mathcal F}, \mu)}$ where ${(\Omega,{\mathcal F})}$ is a measurable space and ${\mu}$ is a measure on that space. If ${\mu}$ is furthermore a probability measure, we call ${(\Omega, {\mathcal F}, \mu)}$ a [probability space](https://en.wikipedia.org/wiki/Probability_space).
A set of measure zero is known as a *null set*. A property ${P(x)}$ that holds for all ${x \in \Omega}$ outside of a null set is said to hold *almost everywhere* or *for almost every *. 

> ### Example 20 (Discrete probability measures)
>   Let ${\Omega}$ be a discrete measurable space, and for each ${\omega \in \Omega}$, let ${p_\omega}$ be a non-negative real number such that ${\sum_{\omega \in \Omega} p_\omega = 1}$. (Note that this implies that there are at most countably many ${\omega}$ for which ${p_\omega > 0}$ – why?.) Then one can form a probability measure ${\mu}$ on ${\Omega}$ by defining $$\displaystyle  \mu(E) := \sum_{\omega \in E} p_\omega$$ for all ${E \subset \Omega}$. 

> ### Example 21 (Lebesgue measure)
>   Let ${{\bf R}}$ be given the Borel ${\sigma}$-algebra. Then it turns out there is a unique measure ${m}$ on ${{\bf R}}$, known as [Lebesgue measure](https://en.wikipedia.org/wiki/Lebesgue_measure) (or more precisely, the restriction of Lebesgue measure to the Borel ${\sigma}$-algebra) such that ${m([a,b]) = b-a}$ for every closed interval ${[a,b]}$ with ${-\infty \leq a \leq b \leq \infty}$ (this is also true if one uses open intervals or half-open intervals in place of closed intervals). More generally, there is a unique measure ${m^n}$ on ${{\bf R}^n}$ for any natural number ${n}$, also known as Lebesgue measure, such that $$\displaystyle m^n( [a_1,b_1] \times \dots \times[a_n,b_n]) = (b_1-a_1) \times \dots \times (b_n-a_n)$$ for all closed boxes ${[a_1,b_1] \times \dots \times[a_n,b_n]}$, that is to say products of ${n}$ closed intervals. The construction of Lebesgue measure is a little tricky; see [this previous blog post](https://terrytao.wordpress.com/2010/09/09/245a-notes-1-lebesgue-measure/) for details. 


We can then set up general probability theory similarly to how we set up discrete probability theory:
> ### Definition 22 (Probability theory)
>   In probability theory, we choose an ambient probability space ${\Omega = (\Omega,{\mathcal F}_\Omega,\mu)}$ as the randomness model, and refer to the set ${\Omega}$ (without the additional structures ${{\mathcal F}_\Omega}$, ${\mu}$) as the *sample space* for that model. We then model an *event* ${E}$ by an element ${E_\Omega}$ of ${\sigma}$-algebra ${{\mathcal F}_\Omega}$, with each such element describing an event. The *probability* ${{\bf P}(E)}$ of an event ${E}$ is defined to be the quantity $$\displaystyle  {\bf P}(E) := \mu( E_\Omega ).$$ An event ${E}$ is *surely true* or is the *sure event* if ${E_\Omega = \Omega}$, and is *surely false* or is the *empty event* if ${E_\Omega =\emptyset}$. It is *almost surely true* or an *almost sure event* if ${{\bf P}(E) = 1}$, and *almost surely false* or a *null event* if ${{\bf P}(E)=0}$.
We model random variables ${X}$ taking values in the range ${R}$ by measurable functions ${X_\Omega: \Omega \rightarrow R}$ from the sample space ${\Omega}$ to the range ${R}$. We define real, complex, and scalar random variables as in the discrete case.

As in the discrete case, we consider two events ${E,F}$ to be equal if they are modeled by the same set: ${E=F \iff E_\Omega = F_\Omega}$. Similarly, two random variables ${X,Y}$ taking values in a common range ${R}$ are considered to be equal if they are modeled by the same function: ${X=Y \iff X_\Omega = Y_\Omega}$. Again, if the sample space ${\Omega}$ is understood from context, we will usually abuse notation by identifying an event ${E}$ with its model ${E_\Omega}$, and similarly identify a random variable ${X}$ with its model ${X_\Omega}$. 


As in the discrete case, set-theoretic operations on the sample space induce similar boolean operations on events. Furthermore, since the ${\sigma}$-algebra ${{\mathcal F}_\Omega}$ is closed under countable unions and countable intersections, we may similarly define the countable conjunction ${\bigwedge_{n=1}^\infty E_n}$ or countable disjunction ${\bigvee_{n=1}^\infty E_n}$ of a sequence ${E_1,E_2,\dots}$ of events; however, we do *not* define uncountable conjunctions or disjunctions as these may not be well-defined as events.

The axioms of a probability space then yield the [Kolmogorov axioms for probability](https://en.wikipedia.org/wiki/Probability_axioms):
-  ${{\bf P}(\emptyset)=0}$. 
-  ${{\bf P}(\overline{\emptyset})=1}$. 
-  If ${E_1,E_2,\dots}$ are disjoint events, then ${{\bf P}(\bigvee_{n=1}^\infty E_n) = \sum_{n=1}^\infty {\bf P}(E_n)}$.

We can manipulate random variables just as in the discrete case, with the only caveat being that we have to restrict attention to *measurable* operations. For instance, if ${X}$ is a random variable taking values in a measurable space ${R}$, and ${f: R \rightarrow S}$ is a measurable map, then ${f(X)}$ is well defined as a random variable taking values in ${S}$. Similarly, if ${f: R_1 \times \dots \times R_n \rightarrow S}$ is a measurable map and ${X_1,\dots,X_n}$ are random variables taking values in ${R_1,\dots,R_n}$ respectively, then ${f(X_1,\dots,X_n)}$ is a random variable taking values in ${S}$. Similarly we can create events ${F(X_1,\dots,X_n)}$ out of *measurable* relations ${F: R_1 \times \dots \times R_n \rightarrow \{ {true}, {false}\}}$ (giving the boolean range ${\{ {true}, {false}\}}$ the discrete ${\sigma}$-algebra, of course). Finally, we continue to view deterministic elements of a space ${X}$ as a special case of a random element of ${X}$, and associate the indicator random variable ${1_E}$ to any event ${E}$ as before.

We say that two random variables ${X,Y}$ *agree almost surely* if the event ${X=Y}$ is almost surely true; this is an equivalence relation. In many cases we are willing to consider random variables up to almost sure equivalence. In particular, we can generalise the notion of a random variable slightly by considering random variables ${X}$ whose models ${X_\Omega: \Omega \rightarrow R}$ are only defined almost surely, i.e. their domain is not all of ${\Omega}$, but instead ${\Omega}$ with a set of measure zero removed. This is, technically, not a random variable as we have defined it, but it can be associated canonically with an equivalence class of random variables up to almost sure equivalence, and so we view such objects as random variables “up to almost sure equivalence”. Similarly, we declare two events ${E}$ and ${F}$ *almost surely equivalent* if their symmetric difference ${E \Delta F}$ is a null event, and will often consider events up to almost sure equivalence only.

We record some simple consequences of the measure-theoretic axioms:
> ### Exercise 23
>   Let ${(\Omega, {\mathcal F}_\Omega, \mu)}$ be a measure space. 
>1.  (Monotonicity) If ${E \subset F}$ are measurable, then ${\mu(E) \leq \mu(F)}$. 
>1.  (Subadditivity) If ${E_1,E_2,\dots}$ are measurable (not necessarily disjoint), then ${\mu(\bigcup_{n=1}^\infty E_n) \leq \sum_{n=1}^\infty \mu(E_n)}$. 
>1.  (Continuity from below) If ${E_1 \subset E_2 \subset \dots }$ are measurable, then ${\mu(\bigcup_{n=1}^\infty E_n) = \lim_{n \rightarrow \infty} \mu(E_n)}$. 
>1.  (Continuity from above) If ${E_1 \supset E_2 \supset \dots}$ are measurable and ${\mu(E_1)}$ is finite, then ${\mu(\bigcap_{n=1}^\infty E_n) = \lim_{n \rightarrow \infty} \mu(E_n)}$. Give a counterexample to show that the claim can fail when ${\mu(E_1)}$ is infinite.

Of course, these measure-theoretic facts immediately imply their probabilistic counterparts (and the pesky hypothesis that ${\mu(E_1)}$ is finite is automatic and can thus be dropped): 

1.  (Monotonicity) If ${E \subset F}$ are events, then ${{\mathbf P}(E) \leq {\mathbf P}(F)}$. (In particular, ${0 \leq {\mathbf P}(E) \leq 1}$ for any event ${E}$.) 
1.  (Subadditivity) If ${E_1,E_2,\dots}$ are events (not necessarily disjoint), then ${{\mathbf P}(\bigvee_{n=1}^\infty E_n) \leq \sum_{n=1}^\infty {\mathbf P}(E_n)}$. 
1.  (Continuity from below) If ${E_1 \subset E_2 \subset \dots }$ are events, then ${{\mathbf P}(\bigvee_{n=1}^\infty E_n) = \lim_{n \rightarrow \infty} {\mathbf P}(E_n)}$. 
1.  (Continuity from above) If ${E_1 \supset E_2 \supset \dots}$ is events, then ${{\mathbf P}(\bigwedge_{n=1}^\infty E_n) = \lim_{n \rightarrow \infty} {\mathbf P}(E_n)}$.

Note that if a countable sequence ${E_1, E_2, \dots}$ of events each hold almost surely, then their conjunction does as well (by applying subadditivity to the complementary events ${\overline{E_1},\overline{E_2},\dots}$. As a general rule of thumb, the notion of “almost surely” behaves like “surely” as long as one only performs an at most countable number of operations (which already suffices for a large portion of analysis, such as taking limits or performing infinite sums).
> ### Exercise 24
>   Let ${(\Omega, {\mathcal B})}$ be a measurable space. 
>-  If ${f: \Omega \rightarrow [-\infty,\infty]}$ is a function taking values in the extended reals ${[-\infty,\infty]}$, show that ${f}$ is measurable (giving ${[-\infty,\infty]}$ the Borel ${\sigma}$-algebra) if and only if the sets ${\{ \omega \in \Omega: f(\omega) \leq t \}}$ are measurable for all real ${t}$. 
>-  If ${f,g: \Omega \rightarrow [-\infty,\infty]}$ are functions, show that ${f=g}$ if and only if ${\{ \omega \in \Omega: f(\omega) \leq t \} = \{ \omega \in \Omega: g(\omega) \leq t \}}$ for all reals ${t}$. 
>-  If ${f_1,f_2,\dots: \Omega \rightarrow [-\infty,\infty]}$ are measurable, show that ${\sup_n f_n}$, ${\inf_n f_n}$, ${\limsup_{n \rightarrow \infty} f_n}$, and ${\liminf_{n \rightarrow \infty} f_n}$ are all measurable.
> ### Remark 25
>   Occasionally, there is need to consider uncountable suprema or infima, e.g. ${\sup_{t \in {\bf R}} f_t}$. It is then no longer automatically the case that such an uncountable supremum or infimum of measurable functions is again measurable. However, in practice one can avoid this issue by carefully rewriting such uncountable suprema or infima in terms of countable ones. For instance, if it is known that ${f_t(\omega)}$ depends continuously on ${t}$ for each ${\omega}$, then ${\sup_{t \in {\bf R}} f_t = \sup_{t \in {\bf Q}} f_t}$, and so measurability is not an issue. 


Using the above exercise, when given a sequence ${X_1,X_2,\dots}$ of random variables taking values in the extended real line ${[-\infty,\infty]}$, we can define the random variables ${\sup_n X_n}$, ${\inf_n X_n}$, ${\limsup_{n \rightarrow \infty} X_n}$, ${\liminf_{n \rightarrow \infty} X_n}$ which also take values in the extended real line, and which obey relations such as 

$$\displaystyle  (\sup_n X_n > t) = \bigvee_{n=1}^\infty (X_n > t) $$

 for any real number ${t}$.


We now say that a sequence ${X_1,X_2,\dots}$ of random variables in the extended real line [converges almost surely](https://en.wikipedia.org/wiki/Convergence_of_random_variables#Almost_sure_convergence) if one has 

$$\displaystyle  \liminf_{n \rightarrow \infty} X_n = \limsup_{n \rightarrow \infty} X_n $$

 almost surely, in which case we can define the limit ${\lim_{n \rightarrow \infty} X_n}$ (up to almost sure equivalence) as 

$$\displaystyle  \lim_{n \rightarrow \infty} X_n = \liminf_{n \rightarrow \infty} X_n = \limsup_{n \rightarrow \infty} X_n.$$

 This corresponds closely to the concept of [almost everywhere convergence](https://en.wikipedia.org/wiki/Pointwise_convergence#Almost_everywhere_convergence) in measure theory, which is a slightly weaker notion than pointwise convergence which allows for bad behaviour on a set of measure zero. (See [this previous blog post](https://terrytao.wordpress.com/2010/10/02/245a-notes-4-modes-of-convergence/) for more discussion on different notions of convergence of measurable functions.)


We will defer the general construction of expectation of a random variable to the next set of notes, where we review the notion of integration on a measure space. For now, we quickly review the basic construction of continuous scalar random variables.
> ### Exercise 26
>   Let ${\mu}$ be a probability measure on the real line ${{\bf R}}$ (with the Borel ${\sigma}$-algebra). Define the *Stieltjes measure function* ${F: {\bf R} \rightarrow [0,1]}$ associated to ${\mu}$ by the formula $$\displaystyle  F( t ) := \mu( (-\infty,t] ) = \mu( \{ x \in {\bf R}: x \leq t \} ).$$ Establish the following properties of ${F}$: 
>- (i) ${F}$ is non-decreasing. 
>- (ii) ${\lim_{t \rightarrow -\infty} F(t) = 0}$ and ${\lim_{t \rightarrow +\infty} F(t) = 1}$. 
>- (iii) ${F}$ is right-continuous, thus ${F(t) = \lim_{s \rightarrow t^+} F(s)}$ for all ${t \in {\bf R}}$.

There is a somewhat difficult converse to this exercise: if ${F}$ is a function obeying the above three properties, then there is a unique probability measure ${\mu}$ on ${{\bf R}}$ (the [Lebesgue-Stieltjes measure](https://en.wikipedia.org/wiki/Lebesgue%E2%80%93Stieltjes_integration) associated to ${F}$) for which ${F}$ is the Stieltjes measure function. See Section 3 of [this previous post](https://terrytao.wordpress.com/2010/10/30/245a-notes-6-outer-measures-pre-measures-and-product-measures/) for details. As a consequence of this, we have
> ### Corollary 27 (Construction of a single continuous random variable)
>   Let ${F: {\bf R} \rightarrow [0,1]}$ be a function obeying the properties (i)-(iii) of the above exercise. Then, by using a suitable probability space model, we can construct a real random variable ${X}$ with the property that $$\displaystyle  F(t) = {\bf P}( X \leq t)$$ for all ${t \in {\bf R}}$. 


Indeed, we can take the probability space to be ${{\bf R}}$ with the Borel ${\sigma}$-algebra and the Lebesgue-Stieltjes measure associated to ${F}$. This corollary is not fully satisfactory, because often we may already have chosen a probability space to model some other random variables, and the probability space provided by this corollary may be completely unrelated to the one used. We can resolve these issues with product measures and other joinings, but this will be deferred to a later set of notes.

Define the [cumulative distribution function](https://en.wikipedia.org/wiki/Cumulative_distribution_function) ${F: {\bf R} \rightarrow [0,1]}$ of a real random variable ${X}$ to be the function 

$$\displaystyle  F(t) := {\bf P}(X \leq t).$$

 Thus we see that cumulative distribution functions obey the properties (i)-(iii) above, and conversely any function with those properties is the cumulative distribution function of some real random variable. We say that two real random variables (possibly on different sample spaces) *agree in distribution* if they have the same cumulative distribution function. One can therefore define a real random variable, up to agreement in distribution, by specifying the cumulative distribution function. See Durrett for some standard real distributions (uniform, normal, geometric, etc.) that one can define in this fashion.

> ### Exercise 28
>   Let ${X}$ be a real random variable with cumulative distribution function ${F}$. For any real number ${t}$, show that $$\displaystyle  {\bf P}(X < t) = \lim_{s \rightarrow t^-} F(s)$$ and $$\displaystyle  {\bf P}(X = t) = F(t) - \lim_{s \rightarrow t^-} F(s).$$ In particular, one has ${{\bf P}(X=t)=0}$ for all ${t}$ if and only if ${F}$ is continuous. 


Note in particular that this illustrates the distinction between almost sure and sure events: if ${X}$ has a continuous cumulative distribution function, and ${t}$ is a real number, then ${X=t}$ is almost surely false, but it does not have to be surely false. (Indeed, if one takes the sample space to be ${{\bf R}}$ and ${X_\Omega}$ to be the identity function, then ${X=t}$ will not be surely false.) On the other hand, the fact that ${X}$ is equal to *some* real number is of course surely true. The reason these statements are consistent with each other is that there are uncountably many real numbers ${t}$. (Countable additivity tells us that a countable disjunction of null events is still null, but says nothing about uncountable disjunctions.)
> ### Exercise 29 (Skorokhod representation of scalar variables)
>   Let ${U}$ be a uniform random variable taking values in ${[0,1]}$ (thus ${U}$ has cumulative distribution function ${F_U(t) := \min(\max(t,0),1)}$), and let ${F: {\bf R} \rightarrow [0,1]}$ be another cumulative distribution function. Show that the random variables $$\displaystyle  X^- := \sup \{ y \in {\bf R}: F(y) < U \}$$ and $$\displaystyle  X^+ := \inf \{ y \in {\bf R}: F(y) \geq U \}$$ are indeed random variables (that is to say, they are measurable in any given model ${\Omega}$), and have cumulative distribution function ${F}$. (This construction is attributed to Skorokhod, but it should not be confused with the [Skorokhod representation theorem](https://en.wikipedia.org/wiki/Skorokhod%27s_representation_theorem). It provides a quick way to generate a single scalar variable, but unfortunately it is difficult to modify this construction to generate multiple scalar variables, especially if they are somehow coupled to each other.)	 


There is a multidimensional analogue of the above theory, which is almost identical, except that the monotonicity property has to be strengthened:
> ### Exercise 30
>   Let ${\mu}$ be a probability measure on ${{\bf R}^n}$ (with the Borel ${\sigma}$-algebra). Define the *Stieltjes measure function* ${F: {\bf R}^n \rightarrow [0,1]}$ associated to ${\mu}$ by the formula $$\displaystyle  F( t_1,\dots,t_n ) := \mu( (-\infty,t_1] \times \dots \times (-\infty,t_n] )$$$$\displaystyle  = \mu( \{ (x_1,\dots,x_n) \in {\bf R}^n: x_i \leq t_i \forall i=1,\dots,n \} ).$$ Establish the following properties of ${F}$: 
>- (i) ${F}$ is non-decreasing: ${F(t_1,\dots,t_n) \leq F(t'_1,\dots,t'_n)}$ whenever ${t_i \leq t'_i}$ for all ${i}$. 
>- (ii) ${\lim_{t_1,\dots,t_n \rightarrow -\infty} F(t_1,\dots,t_n) = 0}$ and ${\lim_{t_1,\dots,t_n \rightarrow +\infty} F(t_1,\dots,t_n) = 1}$. 
>- (iii) ${F}$ is right-continuous, thus ${F(t_1,\dots,t_n) = \lim_{(s_1,\dots,s_n) \rightarrow (t_1,\dots,t_n)^+} F(s_1,\dots,s_n)}$ for all ${(t_1,\dots,t_n) \in {\bf R}^n}$, where the ${+}$ superscript denotes that we restrict each ${s_i}$ to be greater than or equal to ${t_i}$. 
>- (iv) One has


Again, there is a difficult converse to this exercise: if ${F}$ is a function obeying the above four properties, then there is a unique probability measure ${\mu}$ on ${{\bf R}^n}$ for which ${F}$ is the Stieltjes measure function. See Durrett for details; one can also modify the arguments in [this previous post](https://terrytao.wordpress.com/2010/10/30/245a-notes-6-outer-measures-pre-measures-and-product-measures/). In particular, we have
> ### Corollary 31 (Construction of several continuous random variables)
>   Let ${F: {\bf R}^n \rightarrow [0,1]}$ be a function obeying the properties (i)-(iv) of the above exercise. Then, by using a suitable probability space model, we can construct real random variables ${X_1,\dots,X_n}$ with the property that $$\displaystyle  F(t_1,\dots,t_n) = {\bf P}( X_1 \leq t_1 \wedge \dots \wedge X_n \leq t_n)$$ for all ${t_1,\dots,t_n \in {\bf R}}$. 


Again, this corollary is not completely satisfactory because the probability space produced by it (which one can take to be ${{\bf R}^n}$ with the Borel ${\sigma}$-algebra and the Lebesgue-Stieltjes measure on ${F}$) may not be the probability space one wants to use; we will return to this point later.
##  —  4. Variants of the standard foundations (optional)  — 

We have focused on the orthodox foundations of probability theory in which we model events and random variables through probability spaces. In this section, we briefly discuss some alternate ways to set up the foundations, as well as alternatives to probability theory itself. (Actually, many of the basic objects and concepts in mathematics have multiple such foundations; see for instance [this blog post](https://terrytao.wordpress.com/2009/10/19/grothendiecks-definition-of-a-group/) exploring the many different ways to define the notion of a group.) We mention them here in order exclude them from discussion in subsequent notes, which will be focused almost exclusively on orthodox probability.

One approach to the foundations of probability is to view the event space as an *abstract* ${\sigma}$-algebra ${{\mathcal E}}$ – a collection of abstract objects with operations such as ${\wedge}$ and ${\vee}$ (and ${\bigwedge_{n=1}^\infty}$ and ${\bigvee_{n=1}^\infty}$) that obey a number of axioms; see [this previous post](https://terrytao.wordpress.com/2009/01/12/245b-notes-1-the-stone-and-loomis-sikorski-representation-theorems-optional/) for a formal definition. The probability map ${E \mapsto {\bf P}(E)}$ can then be viewed as an abstract probability measure on ${{\mathcal E}}$, that is to say a map from ${{\mathcal E}}$ to ${[0,1]}$ that obeys the Kolmogorov axioms. Random variables ${X}$ taking values in a measurable space ${(R, {\mathcal B})}$ can be identified with their pullback map ${X^*: {\mathcal B} \rightarrow {\mathcal E}}$, which is the morphism of (abstract) ${\sigma}$-algebras that sends a measurable set ${S \in {\mathcal B}}$ to the event ${X \in S}$ in ${{\mathcal E}}$; with some care one can then redefine all the operations in previous sections (e.g. applying a measurable map ${f: R \rightarrow S}$ to a random variable ${X}$ taking values in ${R}$ to obtain a random variable ${f(X)}$ taking values in ${S}$) in terms of this pullback map, allowing one to define random variables satisfactorily in this abstract setting. The probability space models discussed above can then be viewed as *representations* of abstract probability spaces by concrete ones. It turns out that (up to null events) any abstract probability space can be represented by a concrete one, a result known as the *Loomis-Sikorski theorem*; see [this previous post](https://terrytao.wordpress.com/2009/01/12/245b-notes-1-the-stone-and-loomis-sikorski-representation-theorems-optional/) for details.

Another, related, approach is to start not with the event space, but with the space of scalar random variables, and more specifically with the space ${L^\infty}$ of *almost surely bounded* scalar random variables ${X}$ (thus, there is a deterministic scalar ${C}$ such that ${|X| \leq C}$ almost surely). It turns out that this space has the structure of a commutative tracial (abstract) [von Neumann algebra](https://en.wikipedia.org/wiki/Von_Neumann_algebra). Conversely, starting from a commutative tracial von Neumann algebra one can form an abstract probability space (using the idempotent elements of the algebra as the events), and thus represent this algebra (up to null events) by a concrete probability space. This particular choice of probabilistic foundations is particularly convenient when one wishes to generalise classical probability to *noncommutative* probability, as this is simply a matter of dropping the axiom that the von Neumann algebra is commutative. This leads in particular to the subjects of [quantum probability](https://en.wikipedia.org/wiki/Quantum_probability) and [free probability](https://en.wikipedia.org/wiki/Free_probability), which are generalisations of classical probability that are beyond the scope of this course (but see [this blog post](https://terrytao.wordpress.com/2010/02/10/245a-notes-5-free-probability/) for an introduction to the latter, and [this previous post](https://terrytao.wordpress.com/2014/06/28/algebraic-probability-spaces/) for an abstract algebraic description of a probability space).

It is also possible to model continuous probability via a nonstandard version of discrete probability (or even finite probability), which removes some of the technicalities of measure theory at the cost of replacing them with the formalism of [nonstandard analysis](https://en.wikipedia.org/wiki/Non-standard_analysis) instead. This approach was [pioneered by Ed Nelson](http://www.ams.org/mathscinet-getitem?mr=906454), but will not be discussed further here. (See also [these](https://terrytao.wordpress.com/2013/12/07/ultraproducts-as-a-bridge-between-discrete-and-continuous-analysis/) [previous](https://terrytao.wordpress.com/2010/11/27/nonstandard-analysis-as-a-completion-of-standard-analysis/) [posts](https://terrytao.wordpress.com/2014/06/25/lebesgue-measure-as-the-invariant-factor-of-loeb-measure/) on the Loeb measure construction, which is a closely related way to combine the power of measure theory with the conveniences of nonstandard analysis.)

One can generalise the traditional, countably additive, form of probability by replacing countable additivity with finite additivity, but then one loses much of the ability to take limits or infinite sums, which reduces the amount of analysis one can perform in this setting. Still, finite additivity is good enough for many applications, particularly in discrete mathematics. An even broader generalisation is that of *qualitative* probability, in which events that are neither almost surely true or almost surely false are not assigned any specific numerical probability between ${0}$ or ${1}$, but are simply assigned a symbol such as ${I}$ to indicate their indeterminate status; see [this previous blog post](https://terrytao.wordpress.com/2013/11/16/qualitative-probability-theory-types-and-the-group-chunk-and-group-configuration-theorems/) for this generalisation, which can for instance be used to view the concept of a “generic point” in algebraic geometry or metric space topology in probabilistic terms.

There have been multiple attempts to move more radically beyond the paradigm of probability theory and its relatives as discussed above, in order to more accurately capture mathematically the concept of non-determinism. One family of approaches is based on replacing deterministic *logic* by some sort of [probabilistic logic](https://en.wikipedia.org/wiki/Probabilistic_logic); another is based on allowing several parameters in one’s model to be unknown (as opposed to being probabilistic random variables), leading to the area of [uncertainty quantification](https://en.wikipedia.org/wiki/Uncertainty_quantification). These topics are well beyond the scope of this course.
