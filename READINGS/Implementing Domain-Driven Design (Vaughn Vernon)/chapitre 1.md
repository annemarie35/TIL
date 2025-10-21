
## Big Picture
> Early on I take you through one of the pillars of DDD, the Ubiquitous Lan- guage (1). A Ubiquitous Language is applicable within a single Bounded Con- text (2). Straightaway, you need to familiarize yourself with that critical domain modeling mindset. Just remember that whichever way your software models are designed tactically, strategically you’ll want them to reflect the following: a clean Ubiquitous Language modeled in an explicitly Bounded Context.


DDD isn’t first and foremost about technology.
In its most central principles, DDD is about discussion, listening, understanding, discovery, and business value, all in an effort to centralize knowledge.

ubiquitous language > vient du bouquin de Evans
software domain modeling concepts

## What’s a Domain Model?
> It’s a software model of the very specific business domain you are working in. Often it’s implemented as an object model, where those objects have both data and behav- ior with literal and accurate business meaning.
> Creating a unique, carefully crafted domain model at the heart of a core, strate- gic application or subsystem is essential to practicing DDD. With DDD your domain models will tend to be smallish, very focused. Using DDD, you never try to model the whole business enterprise with a single, large domain model.

les personnes impliquées et leurs différents points de vue
manager
domain expert
senior dev, architect
midlevel dev
junior dev

faire équipe, une seule team > make sense for the business and everybody will learn
zero translation cause we use a common language

The Ubiquitous Language is developed with full team agreement, is spoken, and is directly captured in the model of the software.
 the cost of developing software is a justifiable busi- ness investment, not just a cost center. (p.9)
 how an overall service-oriented architecture or business-driven architecture is achieved (p.10)
 DDD meets the real technical demands of the software by using tacti- cal design modeling tools to analyze and develop the executable software deliverables. These tactical design tools allow developers to produce soft- ware that is a correct codification of the domain experts’ mental model, is highly testable, is less error prone (a provable statement), performs to service-level agreements (SLAs), is scalable, and allows for distrib- uted computing. (p.10)

## Core domains / Supporting Subdomains
utiliser DDD sur les parties de ton businnes les plus spécifiques et importantes  "ou invest in the nontrivial, the more complex stuff, the most valuable and important stuff that promises to return the greatest dividends. "
Use DDD to Simplify, Not to Complicate

## DDD scorecards (p11-12)
Use Table 1.1 to determine whether your project qualifies for an investment in DDD. If a row on the scorecard describes your project, place the corresponding number of points in the right-hand column.
Tally all the points for your project. If it’s 7 or higher, seriously consider using DDD.
Matrice pour savoir si fait faire du DDD, si c'est juste du crud, pas besoin

> practicing DDD, the design is the code and the code is the design. In other words, whiteboard diagrams aren’t the design, just a way to discuss the challenges of the model.( p.20)

## Anemic Domain Model [Fowler, Anemic]
Comment reconnaître un modele anémique (p.13)
You probably call this particular client layer of the “domain model” a **Service Layer or Application Layer** (4, 14)
>  a lot of getters and setter
> As [Fowler, Anemic] says, an Anemic Domain Model is a bad thing because you pay most of the high cost of developing a domain model, but you get little or none of the benefit.
>  you have is not a domain model at all, but just a data model projected from a relational model (or other database) into objects
> It’s an impostor that may actually be closer to the definition of **Active Record**  [Fowler, P of EAA].
> You can probably simplify your architecture by not being pretentious and just admit that you are really using a form of **Transaction Script** [Fowler, P of EAA].

causes :
- penser en langage fonctionnel
- c'est à cause de Visual Basic >  JavaBean standard

pas bon
we simply provide data accessors to our model
creating attributes on a class and exposing getters and setters publicly to clients of the model
data-centric model and not behavior centric

## What does anemia everywhere have to do with memory loss? car c'est le problème ! Perte de savoir

- Almost certainly it will take you some time to mentally map between Java attributes and column names.  > il peut y avoir des règles de constraints qui emêche d'enregistrer des datas fausses mais encore faut-il aller voir la db et que le nom des tables soient cohérent avec le "modèle"
- on ne voit pas les cas métiers, on upadte et on sauvegarder le "modèle" user
- faut aller voir l'historique pour comprendre pourquoi des bouts de code ont été ajoutés/modifiés

Let’s call this unenviable situation anemia-induced memory loss. :

1. There is little intention revealed by the saveCustomer() interface.
2. The implementation of saveCustomer() itself adds hidden complexity.
3. The Customer “domain object” isn’t really an object at all. It’s really just a dumb data holder. (p.19)

## Comment résoudre ces problèmes
one of the most empowering features of DDD, the **Ubiquitous Language**. (It’s one of the two primary pillars of DDD’s strengths, the second being the **Bounded Context** (2), and one cannot properly stand without the other)

### Bounded Context
> For now think of a Bounded Context as a conceptual boundary around a whole application or finite system. The reason for this boundary is to highlight that every use of a given domain term, phrase, or sentence—the Ubiquitous Language—inside the boundary has a specific contextual meaning. Any use of the term outside that boundary could, and probably does, mean something different.

### Ubiquitous Language
Ce n'est pas le language du business
>The Ubiquitous Language is a shared team language. It’s shared by domain experts and developers alike.
> In fact, it’s shared by everyone on the project team.
> No matter your role on the team, since you are on the team you use the Ubiquitous Language of the project.

** The Ubiquitous Language is a shared language developed by the team—a team composed of both domain experts and software developers. **

Comment capturer le language ubiquitous
- faire un glossaire
- même si quelques personnes écrivent le glossaire, le refaire relire par toute la team
- Draw pictures of the physical and conceptual domain and label them with names and actions. These drawings are mostly informal but may contain some aspects of formal software modeling. Even if your team does some formal modeling with Unified Modeling Language (UML), you want to avoid any kind of ceremony that will bog down discussions and stifle the creativity of the ultimate Language being sought.
- Create a glossary of terms with simple definitions. List alternative terms, including the ones that show promise and the ones that didn’t work, and why. As you include definitions, you cannot help but develop reusable phrases for the Language because you are forced to write in the Language of the domain.
-If you don’t like the idea of a glossary, still capture some kind of documentation that includes the informal drawings of important software concepts. Again, the goal here is to force additional Language terms and phrases to surface.
- Since only one or a few team members may capture the glossary or other written documents, circle back with the rest of the team to review the resulting phrases. You won’t always, if ever, agree on all the captured linguistics, so be agile and ready to edit heavily.

ce language va être difficile à maintenir dans sa version dessin/glossaire > le code va être sa source de vérité in fine

Cas pratique avec le customer (p.23)
Each Application Service method would be modified to deal with a single use case flow or user story: In the new example we have limited a single Application Service method to deal with changing the personal name of the Customer, and nothing more
Now, however, this specific Application Service method doesn’t require its client to pass ten nulls following the first- and last- name parameters.
```java
public interface Customer {
    public void changePersonalName(
        String firstName, String lastName);
}
```

Application Service =
```public void changeCustomerPersonalName(){ // do somethin}```

- You can read the code and easily comprehend it.
- You can also test it and confirm that it does exactly what it is meant to do, and that it doesn’t do anything that it shouldn’t.

> Thus, the Ubiquitous Language is a team pattern used to capture the con- cepts and terms of a specific core business domain in the software model itself. The software model incorporates the nouns, adjectives, verbs, and richer expressions formally formulated and spoken by the close-knit team. Both the software and the tests that verify the model’s adherence to the tenets of the domain capture and adhere to this Language, the same one spoken by the team.


### Ubiquitous, but Not Universal (p.24-25)

• Ubiquitous means “pervasive,” or “found everywhere,” as spoken among the team and expressed by the single domain model that the team develops.
• The use of the word ubiquitous is not an attempt to describe some kind of enterprise-wide, company-wide, or worldwide, universal domain language.
• **There is one Ubiquitous Language per Bounded Context**.
• Bounded Contexts are relatively small, smaller than we might at first imagine. A Bounded Context is large enough only to capture the complete Ubiquitous Language of the isolated business domain, and no larger.
• The Language is ubiquitous only within the team that is working on the project that develops in an isolated Bounded Context.
• On a single project that develops a single Bounded Context, there are always one or more additional isolated Bounded Contexts with which it integrates using Context Maps (3). Each of the multiple Bounded Con- texts that integrate has its own Ubiquitous Language, even though some terms of each may overlap.
• If you try to apply a single Ubiquitous Language to an entire enterprise, or worse, universally among many enterprises, you will fail.


# the business value = How You Can Sell DDD to Your Boss.
We must justify everything that we do >  I think the best justifica- tion for using any technology or technique is to provide value to the business.

1. The organization gains a useful model of its domain.
We focus on the Core Domain (what distinguishes our business from all others > competitive advantage ).

2. A refined, precise definition and understanding of the business is developed.
3. Domain experts contribute to software design.
4. A better user experience is gained.
5. Clean boundaries are placed around pure models.
6. Enterprise architecture is better organized.
7. Agile, iterative, continuous modeling is used.
8. New tools, both strategic and tactical, are employed.
Disparate teams, sometimes each respon- sible for a given Bounded Context, use Context Maps to strategically segregate Bounded Contexts and understand their integrations. Within a single modeling boundary the team may employ any number of useful tactical modeling tools: Aggregates (10), Entities (5), Value Objects (6), Services (7), Domain Events (8), and others.

aux intersections de bounded context on utilise des context map

The Challenges of Applying DDD (p.29-30)
• Allowing for the time and effort required to create a Ubiquitous Language
• Involving domain experts at the outset and continuously with the project
• Changing the way developers think about solutions in their domain

It’s about designing the behaviors of objects

exercice  whiteboard time (p;34)
• Using the specific domain you currently work in, think of the common terms and actions of the model.
• Write the terms on the board.
• Next, write phrases that should be used by your team when you talk about the project.
• Discuss them with a real domain expert to see how they could be refined (remember to bring the coffee).

#### Justification for Domain Modeling
Tactical modeling is generally more complex than strategic modeling.
the DDD tactical patterns (Aggre- gates, Services, Value Objects, Events, and so forth)

## tips (p35-36)  Core domain > Generic Subdomain > Supporting Domain
Suivant ce que c'est, utiliser les outils tactiques, ce qui importe c'est la valeur pour le business, qui peut évoluer
- If a Bounded Context is being developed as the Core Domain, it is strategically vital to the success of the business.
- A domain that may become a Generic Subdomain (2) or Supporting Sub- domain to its consumers may actually be a Core Domain to your busi- ness.

### tips (p.35) plus orienté devs  > Transaction Script ?
1. Are domain experts available and are you committed to forming a team around them?
2. Although the specific business domain is somewhat simple now, will it grow in complexity over time? There is risk in using **Transaction Script **1 for complex applications. If you use Transaction Script now, will the potential for refactoring to a behavioral domain model later on be practi- cal if/when the Context becomes complex?
3. Will the use of the DDD tactical patterns make it easier and more practical to integrate with other Bounded Contexts, whether third-party or custom developed?
4. Will development really be simpler and require less code if you use Transaction Script? (Experience with both approaches proves that many times Transaction Script requires as much or more code. This is probably because the complexity of the domain and the innovation of the model were not well understood during project planning. Underestimating domain complexity and the innovation involved happens often.)
5. Do the critical path and timeline allow for any overhead required for tactical investment?
6. Will the tactical investment in a Core Domain protect the system from changing architectural influences? Transaction Script may leave it exposed. (Domain models are often enduring while architectural influences tend to be more disruptive to other layers.)
7. Will clients/customers benefit from a cleaner, enduring design and devel- opment approach, or could their application be replaced by an off-the- shelf solution tomorrow? In other words, why would we ever develop this as a custom application/service in the first place?
8. Will developing an application/service using tactical DDD be more diffi- cult than using other approaches such as Transaction Script? (Skill level and availability of domain experts is vital to answering this question.)
9. If the team’s toolkit was complete with DDD enablers, would we consci- entiously choose to use another approach instead? (Some enablers make model persistence practical, such as using object-relational mapping, full Aggregate serialization and persistence, an Event Store, or a framework that supports tactical DDD. There may be other enablers, too.)

Méthodo pour les devs  attention This test stage is not attempting to prove with absolute cer- tainty that the model is bulletproof. !
1. Write a test that demonstrates how the new domain object should be used by a client of the domain model.
2. Create the new domain object with enough code to make the test compile.
3. Refactor both until the test properly represents the way a client would use the domain object, and the domain object has proper behavioral method signatures.
4. Implement each domain object behavior until the test passes, refactoring
the domain object until no inappropriate code duplications exist.
5. Demonstrate the code to team members, including domain experts, to ensure that the test is using the domain object according to the current meaning of the Ubiquitous Language.

Comment vérifier, un non expert peut comprendre ne lisant le code à côté d'un(e) dev : Domain experts who are nontechnical should be able, with the help of a developer, to read the code well enough to get a clear impression that the model has achieved the goal of the team

Fiction, with Bucketfuls of Reality
projet existant ou pas ? une vraie entreprise

• You’ve discovered what DDD can do for your projects and your teams to help you grapple with domain complexity.
• You found out how to score your project to see if it deserves the DDD investment.
• You considered the common alternatives to DDD and why using those approaches often leads to problems.
• You’ve grasped the foundations of DDD and are prepared to take the first steps on your project.
• You’ve found out how to sell DDD to your management, domain experts, and technical team members.
• You are now armed with knowledge of how to succeed while facing the challenges of DDD.

A clarifier : la différence entre tactique et stratégique

Transaction Script ?
Domain Event
developing a given Subdomain (2)  

application programming interface (API)
a “brownfield” environment common where many legacy systems exist vs greenfield

## Bouquins
If you have abilities somewhere between grasping Head First Design Patterns [Freeman et al.] and grokking the original Design Patterns [Gamma et al.] text, or even more advanced patterns, you stand a really good chance of succeeding with DDD. 
