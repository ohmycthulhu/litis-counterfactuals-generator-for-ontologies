
One of the biggest challenges is performance - counter-factual generation relies on usage of reasoner which is very slow. 

*CEO already utilizes flag of non-actionable flag*. We may benefit from flagging relations by low and high priority. 

Caching as way to accelerate the progress. 
Yes, and it works but not significantly.

*Consider the graph of classes to calculate distance* (needs proof).
Already implemented in CEO

Using meta-heuristics for solving counterfactuals problems. 
The problem with the performance.

_Can we use evolutionary programming here?_
Nope, it's unrelevant.

Is it possible to perform batch check using reasoner?
Nope, it doesn't work like this with reasoner.

Calculating distance for number attributes, should they be normalized?
There is no way to consider number properties. 

Is it possible to run reasoner without generating new facts? (just to check consistency)

We need to find some ontologies for testing. 

_As an idea, we can recompile reasoner to not generate new facts and only to ensure the existing ones._

_Check implementation of "Interactive Ontology Debugging Plug-in for Protégé" - OntoDebug_

Is it considered the counter-factual if the only class assertion is the one that we gave and not what the reasoner generated?

Need to search for:
- [ ] counterfactuals and ontologies
- [ ] meta-heuristics in generatic ontologies
- [ ] genetic programming for generating CF
- [ ] explainability in ontologies
- [ ] using ontology's T-box
- [ ] post-hoc explanation in ontology
- [ ] 