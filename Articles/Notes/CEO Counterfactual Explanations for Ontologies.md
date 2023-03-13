## Introduction

Source: [[Articles/Notes/CEO Counterfactual Explanations for Ontologies.pdf]]

There are some API that provide explanations for reasoner's decisions (`owlready`?). 

> Methods to generate explanations are divided into two types: black-box and glass-box methods [4]. According to [9], *glass-box* methods introduce significant modifications to description logic reasoners with the goal to use available internal information for a fast computation of diagnoses. *Black-box* methods use a reasoner as an oracle to check if some set of axioms is consistent.

> The simplest type of explanations that can be extracted from the reasoner is logical proofs. They display each step of the reasoning process that resulted in a specific entailment.

> Justifications are another popular form of explanation. ... They consist in finding the smallest sets of axioms necessary for a given entailment to hold.



## Preliminary work


**Close possible worlds** - counterfactuals should alter the values as little as possible.
**Diverse** - ideally, different counterfactuals should be provided so user may choose which set of changes are easier to achieve in order to receive the desired changes.
**Sparsity** - number of changed parameters should be limited in order for user to be able to understand the outcome. 

## CEO

The method consists of replacing the class assertation by the user-defined set and seeking for set of properties that would make the ontology consistent.
The method is black-box (uses reasoner as an oracle). 
**The major problem is open world assumption.**

CEO method is decomposed into four parts:
1. Generate a set of candidate counterfactuals
2. Remove non valid and non feasible candidates
3. Compute proximity and sparsity on the set of valid candidates
4. Display the valid candidates to the user

### Search space

$\Omega = (V, E)$
$V$ - set of IKGs that are nodes of the graph
$E$ - set of directed edges that link one IKG to another.

There are present three available operations:
- Object modification
- Assertion removal
- Assertion insertion

### Exploring the search space

The ideal initial point is individual $\hat I$ that contains all original assertations but class assertation.
The open world assumption allows identifying important features by following statement: _if the property assertation is not present, it may not cause inconsistencies with the ontology_. Therefore, the first step is to identify important properties by removing them and checking consistency of the given individual. 
The next step is to generate ancestors and descendants. They work by inserting and modifying assertions. 

> In the worst case, this CF is an IKG with no assertion.
> However, the number of candidate counterfactuals explored by Algorithm 1 in the worst case is exponential with the number of assertions in the original IKG.
> When the number of entities in the ontology increases, the reasoning time and the number of candidate counterfactuals to explore also increase.


### Computing metrics in the graph

Proximity is presented as *graph edit distance*:
$GED (I_1, I_2) = min_{(e_1, ..., e_k) \in P(I_1, I_2)} {\sum_{i=1}^{k}{c(e_i)}}$
where,
$P(I_1, I_2)$ - set of edit paths transforming $I_1$ into $I_2$.
$c(e)$ - is the cost of each elementary operation.

**The cost of removal is considered higher than modification, the cost of assertion is higher that removal.**
The rationale behind that is idea that removing some attribute makes it unknown and adding information is harder (especially if not specified before). TLDR: assertation removal or insertion have more chances of unfeasable results than modification. 

$c_m = sim(a_1, a_2)$
$c_r = max_{\alpha \in A} sim(a_1, \alpha) + 1$
$c_i = c_r(a_1) + 2$

Sparcity here is the shortest path between two IKGs containing one edge per modified assertion. For sparcity, $\forall e, c(e) = 1$

### Assertion similarity

> the distance between triples can be simplified into the distance between the objects.

The triples can be compared **only if they have the same predicate**.

> Edge-counting similarity between two classes is the length of the shortest path from one class to the other in this tree.

> If the individual is not subject of any ClassAssertion, then the class used is owl:Thing which is the root of the tree.
> If the individual is subject of a single ClassAssertion, this class is used to measure the similarity with another individual.
> If the individual is subject of multiple ClassAssertions, then the similarity between each class is calculated and the smallest one is kept.

The properties that can not be modified are marked as `NonActionable`. The modification of such property would make CF unfeasible. 

****

Questions:
- Why it's important to clarify that the class has changed? IMHO, the goal should be getting aimed class not discarding the initial one. This is not important for taxonomies but will be important for other ontologies. **It's important, so it fits the definition of counter-factual: what should be changed in order to achieve target class and change the initial one.**
- The addition cost doesn't check whether the individual had this assertion earlier. This makes it harder to add already existing assertions that were removed during the initial step (assertion removal). Is it correct?


## Conclusion

The proposed method consists of independable steps which allows modularity and partial application.

Three problems are identified:
- the proximity measure (similary) - it's not suited for this application and should be modified to improve the ranking of the explanations.
- exploration of the graph of all possible counterfactuals - it doesn't explore assertion insertions and does not guarantee to explore the best counterfactuals.
- some types of assertions are not handled (e.g., `DataPropertyAssertyions` or `NegativeObjectPropertyAssertions`).

In the current work, only hierarchical relations are exploited, the rest of the T-Box is not used to generate the graph.

> Exploiting the T-Box may reduce computation time without hindering the quality of explanations. Doing so may also facilitate the exploration of assertion insertions which is lacking in the current version. Other similarity metrics will also be investigated. Particularly, a variation of the edge-counting similarity that favors classes with the same depth will be researched, as well as other classes of similarity metrics that were seen in the literature. Finally, NegativeObjectPropertyAssertions and DataPropertyAssertions support will be implemented in the next versions of this method.

## To check later

- [28] W3C, OWL 2 Web Ontology Language Mapping to RDF Graphs, 2012, Online; accessed on 11-November-2022.