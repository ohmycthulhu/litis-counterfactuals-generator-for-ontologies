Source: [[CEO Counterfactual Explanations for Ontologies]]

White-box approach that parses the hierachies and relations, and act upon the differences between initial and desired class. 

Input: the entity, the desired class
Output: set of changes for the individual

The repairing should comply with the following conditions:
- It can not change nonactionable relations, including class assertion
- All changes should have the target individual as subject
- It should generate different individuals as resulting action

### Strategies
- Specify non-actionable relations, including the class assertion
- "Break" the ontology by inserting the desired class assertion
- Generate several fixed individuals that will comply with the ontology

### Questions?

- How do you create many counter-factuals?
- How to parse and get final asserions for the ontology?
- Which language may be useful here?
- Is there any other libraries to work with OWL ontologies?
- Is there any work that aimed at white-box approach to ontologies?

### Investigation

- Need exploring [OWL specification](https://www.w3.org/TR/owl2-syntax/)
- Maybe needs exploring [RDF specification](https://www.w3.org/TR/owl2-syntax/)
- It may be useful to check how protege calculates attributes and children ([source code](https://github.com/protegeproject/protege))
- Checking owlready code is advised ([source code](https://bitbucket.org/jibalamy/owlready2/))



### Useful literature
- [[Ontology/Completing and Debugging Ontologies State of the Art and Challenges.pdf]]
