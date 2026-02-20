#  "Clean Code" a Timeless Truth OR a Myth We Keep Telling Ourselves?

[source](https://www.youtube.com/watch?v=OjW_0ZRdN5E)
Kevlin Henney and Daniel Terhorst-North take on one of the most enduring, and controversial, ideas in software engineering: clean code.

Since the publication of Robert C. Martin’s (Uncle Bob) Clean Code, generations of software developers and software engineers have been taught that “cleanliness” in code is the gold standard. But what does clean code really mean in modern software development? And does it still hold up in today’s complex, fast-moving systems?

Kevlin and Daniel explore how the idea of clean code evolved — from Bob Martin, Kent Beck, and even earlier thinkers in computer science — and challenge whether rigid rules and dogma actually help developers write better code, or whether they sometimes make systems harder to understand and change.

This conversation goes beyond style guides and naming conventions to focus on what truly matters:

How code supports human understanding
- Why habitability may be more useful than “cleanliness” 
- How context, scale, and team dynamics change what good code looks like
- When refactoring and design practices actually improve outcomes — and when they don’t

Synthesis by Claude.

## Main Question: Is Clean Code a Myth?

The answer they arrive at: **Clean code is not a myth, but it's relational rather than absolute** - it depends on context, people, and goals rather than being a fixed set of practices.

## Key Insights:

### Three Origins of "Clean Code"

1. **Robert C. Martin's "Clean Code" (2008)** - The most recognized source, though sometimes seen as dogmatic
2. **Kent Beck's "Tidy First"** - A more recent, gentler framing of similar concepts
3. **Richard Gabriel's "Habitability" (earlier)** - Focuses on code being comfortable to navigate and confident to change

### Historical Context

- The term "clean code" predates Martin's book significantly
- Found in Kent Beck's "Test Driven Development by Example" (2003): "clean code that works"
- Used in Martin Fowler's original "Refactoring" in the 1990s
- Even appears in "The Elements of Programming Style" (1974!)

### The Critical Shift in Understanding

**Dan North's key observation**: Much of the advice in Clean Code made sense for its time (late 90s/early 2000s) when:
- Work was distributed across specialized teams
- Different people handled UI, database, services, etc.
- Separating code prevented teams from conflicting

**But today**:
- Full-stack developers handle entire features
- Breaking code into 30 different places creates **fragmentation** rather than clarity
- The administrative overhead now outweighs the benefits

### The Goldilocks Principle

Kevlin introduces the idea that code size isn't linear (more = bad, less = good), but rather:
- **Too big**: Mental overload - you're constantly decomposing in your head
- **Too small**: Fragmentation - you're constantly recomposing scattered pieces
- **Just right**: The sweet spot where code fits your mental model

**Key metric**: "Small is about how much thinking you have to do, not about how much code there is"

### Locality of Behavior

Dan highlights the HTMX framework's principle: **Keep related functionality together** rather than separating by technical layer. This inverts traditional "separation of concerns" to focus on **single goals** rather than single responsibilities.

### Theory of Constraints Application

Dan connects this to Eliyahu Goldratt's work:
- Clean code isn't valuable in itself
- It's valuable **in order to** deliver software sustainably and effectively
- Code cleanliness should address your current constraint
- If code clarity isn't your bottleneck, focusing on it is opportunity cost

### What Endures from Clean Code

Some advice has "aged like wine":
- **Good naming** (Tim Ottinger's chapter)
- **Identifying boundaries** (James Grening's chapter)
- The general principle of code hygiene as continuous practice

Some advice has aged poorly:
- Rigid rules about function size
- Extreme fragmentation of code
- Dogmatic application without context

## The Central Metaphor

Clean code is like **kitchen hygiene** - not valuable for its own sake, but because it enables you to serve food (deliver value) sustainably, quickly, and effectively.

## Practical Takeaway

**"Best simple system for now"** - Code cleanliness should be exactly what you need to work effectively with your current goals and constraints. Not more (over-engineering), not less (technical debt that slows you down).

The conversation concludes that clean code is about **habitability** - creating an environment where developers can work comfortably and confidently, with code that brings joy rather than constant frustration. It's a human-centered, relational quality rather than a checklist of practices.

# Notes
### Goldilocks Principle,
est aussi appelé [le principe de boucle d'or](https://fr.wikipedia.org/wiki/Principe_de_Boucle_d%27or). 
> Dans les sciences cognitives et la psychologie du développement, l'effet ou principe Boucle d'or se réfère à la préférence d'un nourrisson pour assister à des événements qui ne sont ni trop simples, ni trop complexes en fonction de leur représentation du monde

### Notion d'habitabilité par Richard Gabriel
Il parle de code habitable, sur son site, il cite Christopher Alexander, on peut y lire :
> For years I’ve tried to blend art and science in my work
>
Un des ses textes [Better Science Through Art](https://www.dreamsongs.com/Files/BetterScienceThroughArt.pdf)
La notion d'habitabilité est tiré de [« Patterns of Software »](https://www.dreamsongs.com/Files/PatternsOfSoftware.pdf)
- https://www.codeworks.fr/articles/habitabilite