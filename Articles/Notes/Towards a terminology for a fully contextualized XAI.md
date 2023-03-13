Source: [[Towards a terminology for a fully contextualized XAI.pdf]]

## Introduction

The problem of XIS (eXplainable Intelligent Systems) is the need to explain how intelligent systems (including AI) works. The reason lies in the rise of their usage in many importnant areas of life (e.g., banking, medicine, etc.).

> It is this right [to understand the decision behind models] to explanation that the GDPR [1], among others, defends

The explainability and interpretability of IS is a part of long-term goal of creating _responsible IS_.

![[Pasted image 20230302103500.png]]

XIS consists of explaination model (that makes prediction) and explanation interface (that interacts with user to provide explanations).

## Terminology

![[Pasted image 20230302105441.png]]

### General Terminology

**User** - an agent that interacts with an XIS. 

**Explanations** and **Explainability** (come from Explanation Ontology Design Pattern): **an explanation** - result of an interaction between a user and an explainer in order to answer the user's questions. **explainability** - ability of an XIS to be explained to a user or to provide an explanation.

**Interpretability** - ability of an object or an XIS to be *seen, understood and studied* by a user with a reasonable cognitive effort. It's linked to *transparency* (by need to have enough information).

**Trust** - to believe that something is safe and reliable. It's very important for a final user to trust AI's conclusions. It's achieved by explanations, transparency, reliablitiy and providing the failure modes or edge cases. 

### Explanation terminology

XIS should answer the following questions:
- "What do we explain?" - **focus**
- "By what means do we explain?" - **means**
- "How do we explain?" - **modality**

#### Focus
Can be either local or global.
**Local explanation** aims at explaining a single prediction.
> It answers “what”, “why”, “what if” questions. Counterfactual reasoning is especially relevant for this kind of explanations, as it consists in exploring “what if” questions.


**Global explanation** describes the behaviour of the entire system.  
> The explanation may also include what training data was used, the performance of the system (evaluated by adequate metrics) and what its limitations or failure modes are


#### Means
Can be either *direct* or *post-hoc* explanations. 

**Post hoc explanation uses an auxiliarty method to explain an XIS or its decisions.** It's appropriate for explaning *black-boxes*, it's usually a model agnostic approach. 
**Direct explanation is an explanation issued directly from the AI algorithm at the core of the XIS.** For this explanation to be satisfactory, the system and its components should be interpretable.

#### Modality
**Statis explanation** - does not change depending on the user.
**Interactive explanation** - interacts with the user to explain the needed parts of the decision.

Interactive explanations are harder to achieve but provide much more information that static ones.

#### Reasoning
**Reasoning** - the process of thinking about something in order to make a decision.

**Abduction** - rendering what might be thought of as a unique experience into an instance of a more general phenomenon. Inductive reasoning. 
**Counterfactual reasoning** consists in imagining how an event could change if a previous event that led to the observed event was modified or removed. Answers to "What would happen if ...?" question. 

### System terminology

> The model is the object that calculates the prediction from the input, which means it is part of this system. We defined interpretability as being a property of an object or system, therefore, any component of a system can be interpretable on its own, without guaranteeing that the entire system is interpretable

> Trust and reponsibility are goals of explainability. Explainability is a part of _responsible AI_.

> Responsible AI is an AI that is accountable, i.e., has the ability to demonstrate and accept responsibility.

**Black-box-ness** - the opposite of interpretability. It's bound to interpretability and depend on user. There are some systems (e.g. deep neural networks) that are considered black boxes regardless of the user.


**Complexity** - the measure of the interpretability of an object (how easy it is for a user to simulate and/or understand an object). It's model dependent.

**Simulatability** - the ability of a model to be simulated or replicated by a user.

**Decomposability**: a system is decomposable if each of its components (inputs, parameters, and calculations) are interpretable. 

Simulatability and decomposability leads a system towards interpretability but the latter is not gurranteed.

**Reliability** - ability to withstand perturbations and erros to its input or parameters. It provides confidence that it will perform in the same manner in any condition.

**Fairness** - the ability of a system to avoid any form of unjustified discrimination at each level of the system. *Designing fair systems is incredibly difficult, intuitive solutions to prevent discriminations are not always valid.*

**Transparency**: a system is transparent if it provides all the information about its design and functioning for scrutiny. It doesn't guarrantee that a user will be able to understand the system but that it will have access to all the information concerning the training data.

Projects to research about:
- DARPA's XAI - D. Gunning, Explainable artificial intelligence (xai), Defense Advanced Research Projects Agency (DARPA), nd Web 2 (2) (2017).
- I. Tiddi, M. d’Aquin, E. Motta, An ontology design pattern to define explanations, in: Proceedings of the 8th International Conference on Knowledge Capture, 2015, pp. 1–8.