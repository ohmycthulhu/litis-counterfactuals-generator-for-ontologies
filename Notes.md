
One of the biggest challenges is performance - counter-factual generation relies on usage of reasoner which is very slow. 

****

*CEO already utilizes flag of non-actionable flag*. We may benefit from flagging relations by low and high priority. 

****

Caching as way to accelerate the progress. 
Yes, and it works but not significantly.

****

*Consider the graph of classes to calculate distance* (needs proof).
Already implemented in CEO

****

Using meta-heuristics for solving counterfactuals problems. 
The problem with the performance.

****

_Can we use evolutionary programming here?_
Nope, it's unrelevant.

****

Is it possible to perform batch check using reasoner?
Nope, it doesn't work like this with reasoner.

****

Calculating distance for number attributes, should they be normalized?
There is no way to consider number properties. 

****

Is it possible to run reasoner without generating new facts? (just to check consistency)

****

We need to find some ontologies for testing. 

****

_Idea: we can recompile reasoner to not generate new facts and only to ensure the existing ones._

****

_Check implementation of "Interactive Ontology Debugging Plug-in for Protégé" - OntoDebug_

****

Is it considered the counter-factual if the only class assertion is the one that we gave and not what the reasoner generated?
Yes

****

*Does the current implementation calculates the distance between the very first individual or altered one?*
Yes

****

*Idea: Use experts for defining the costs of different operations*

****

*Does the current implementation work only with functional relations?*
No

*****

Need to search for:
- [x] counterfactuals and ontologies
- [x] meta-heuristics in generatic ontologies
- [x] genetic programming for generating CF
- [x] explainability in ontologies
- [x] using ontology's T-box
- [x] post-hoc explanation in ontology

