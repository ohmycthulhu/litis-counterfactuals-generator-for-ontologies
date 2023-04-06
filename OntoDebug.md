
OntoDebug contains means to test singular expression (test cases window).

Possible Ontology repairs contains a number of axioms that may be removed or modified in order to make the ontology consistent. **It doesn't try to predict possible values that would make ontology consistent.**


Running the test case for instruments, I got the error related to `hasMechanism some keyboard`

*We imply that T-Box is correct and try coming up with*


Hypothesis:
> Running test case in OntoDebug is several times faster than checking consistency using a reasoner.


Idea:
> Reusing the methods of finding potential changes for ontologies using OntoDebug's method, proposing potential changes using CEO, and evaluating the result using test case infrastructure.

Assumptions:
- using test case is faster than using reasoner
- it is always possible to reformulate individual into test case syntax
- ontodebug is able to find the missing assertions

*Sometimes OntoDebug can't work with inconsistent ontologies but sometimes it's not a case.*
