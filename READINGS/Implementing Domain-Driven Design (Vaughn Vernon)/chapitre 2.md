# Chapitre 2


In the end you will have to integrate with and even work in brownfield domains, so be prepared to exercise the techniques taught in the first one-third of this chapter as you analyze the multiple implicit models found in a single, brown Bounded Context.
When referring to just one area of the business, I will generally qualify it with the use of **Core Domain**, **Subdomain**, and the like.
The whole Domain of the organization is composed of **Subdomains**. Using DDD, models are developed in **Bounded Contexts**.
 

> Any attempt to define the business of even a moderately complex organization in a single, all-encompassing model will be at best extremely difficult and will usually fail.


Des subdomains très simple (ex des algo) peuvent être mis dans des modules
We would be certain that each of those concepts is well understood, spoken of explicitly, and modeled as such

integration relationships, (entre domaines) > context maps sont utilisé pour les décrire

supporting subdomain vs generic sundomains

comment nommer les bounded context ?

Big Ball of Mud ??

Domains : They have both a problem space and a solution space:
- The **problem space** enables us to think of a strategic business challenge to be solved > need to be developed to deliver a new Core Domain (= strategic business problem)
- while the **solution space** focuses on how we will implement the software to solve the problem of the business challenge. > = one or more Bounded Contexts, a set of specific software models, The Bounded Context is used to realize a solution as software

Here are some questions that should be answered in order to steer your project in the right direction:
- What is the name of and vision for the strategic Core Domain?
- What concepts should be considered part of the strategic Core Domain? - WhatarethenecessarySupportingSubdomainsandtheGenericSubdomains? - Who should do the work in each area of the domain?
- Can the right teams be assembled?


> If we don’t understand the vision and goals of the Core Domain and the areas of the Domain that are needed to support it, we won’t be able to strategically take advantage of them and avoid associated pitfalls.

When you have a good understanding of the problem space, you then turn to the solution space. The first assessment will contribute knowledge to the second. The solution space will be strongly influenced by the existing systems and technologies, and those that are to be newly created.

- What software assets already exist, and can they be reused?
- What assets need to be acquired or created?
- How are all of these connected to each other, or integrated?
- What additional integration will be needed?
- Given the existing assets and those that need to be created, what is the required effort?
- Do the strategic initiative and all supporting projects have a high proba- bility of success, or will any one of them cause the overall program to be delayed or even fail?
- Where are the terms of the Ubiquitous Languages involved completely different?
- Where is there overlap and sharing of concepts and data between Bounded Contexts?
- How are shared terms and/or overlapping concepts mapped and translated between the Bounded Contexts?
- Which Bounded Context contains the concepts that address the **Core Domain** and which of the [Evans] tactical patterns will be used to model it?