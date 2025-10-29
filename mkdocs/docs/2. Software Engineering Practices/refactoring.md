# Refactoring

To explain why refactoring is important, let me first begin with a cautionary tale...

## A Cautionary Tale

A new project begins with a clean slate and developers start hammering away on new features. The codebase is small, so it is easy to see the various pieces and how they fit together. Updating the code is a breeze because there isn't much that can go wrong, and if something breaks it will be easy to notice. Stakeholders are happy with the team's velocity. The team is generally small at this stage and everyone has an intuitive sense of what's going on.

Time goes by, and the complexity gradually and steadily increases. After a while, there are dozens of components interacting with each other, and hundreds of individual features supporting several critical user workflows. Individual contributors only a partial understanding of the whole system. The cost of breaking something is much higher since the app is so much more useful. At the same time, it's harder for any single person to grasp how everything fits together. Developers begin to lose their self-confidence and become anxious about making changes to the code. Delivery slows down, and bugs find their way into the system.

Eventually, the complexity of the app becomes overwhelming. The speed of delivery tapers off, deadlines are missed, outages happen. If this continues, progress could grind to a halt. The codebase starts to resemble a Jenga tower at risk of collapse.

![Jenga](../img/Jenga_tower_1.JPG)

Unfortunately, this cautionary tale is based on several real-world experiences. Without taking proactive steps to manage the complexity, software projects often follow a trajectory similar to the one in this story. The question is, what can be done to prevent this situation for new projects, and how can we recover from this situation in existing projects?

## On Complexity

One important point about complexity is that it can be broken down into two categories: __necessary__ and __unnecessary__ complexity. What I mean is that certain complexity is baked in, or __necessary__. Put another way, this is "business logic". For example, an double-entry accounting app must record each entry in two accounts, a social media app must store relationships between users, and a game must keep track of the player's state.

Sometimes complexity is __unnecessary__. A simple example of unnecessary complexity is duplicated code. Another example is a confusing data model. I'd put over-engineered code and duct-tape fixes into this category as well.

I like visual aids, so here is a graph showing the typical progression of necessary and unnecessary complexity in a codebase without refactoring:
![1 - No Refactoring](../img/refactor1 Medium.jpeg)

## Why Refactor?

[Wikipedia](https://en.wikipedia.org/wiki/Code_refactoring) defines refactoring as "restructuring existing source code—changing the factoring—without changing its external behavior." 

By distinguishing necessary and unnecessary complexity, it's easy to see that the only way to bring down the __total__ complexity is to tackle __unnecessary__ complexity. If we want to deliver with high speed and confidence over a long time period, we must refactor. 

When refactoring becomes a regular part of development, it can make a __significant impact__ on the overall complexity:

![2 - With Regular Refactoring](../img/refactor2 Medium.jpeg)

## Refactoring Confidently

Although the problem and solution are easily stated, the work of refactoring can be extremely challenging! And it's challenging for the same reason that all code changes are challenging: developers become overwhelmed by complexity, and lose confidence that they can change things without breaking them (remember from the definition of 'refactoring' that the behavior of the application cannot change). 

To refactor successfully, we need to avoid becoming overwhelmed, and this is mainly a preventative effort. Refactoring should begin early on in the project, and be a regular part of development. It's routine maintenance.

_"A stitch in time saves nine."_

We also need to make sure the developers have confidence that their changes are correct. This is primarily done through automated testing. [Test-Driven Development](../01-%20tdd/) is __the best way__ to achieve good test coverage. Like refactoring, this is most effective when started early and made a regular part of development.

## It's Getting Late

In an ideal world, all codebases would get the necessary regular maintenance. But in the real world, this doesn't always happen. What can be done about applications that are already facing significant challenges, like the one I described in my cautionary tale?

Unfortunately, this is a very challenging situation and teams can spend a lot of time digging themselves out of this hole! 

The hole may be deeper, but the basic approach is the same. Validating the expected app behavior with automated tests is paramount, as this creates the confidence needed for major code changes. More often than not, collaboration with users & business stakeholders will be necessay to even define the expected program behavior.

Next, possible refactors should be identified and the team should consider the cost/benefit of each. A [2x2 prioritization](https://labspractices.com/practices/2x2/) exercise can be useful to identify the highest priority changes.

In extreme cases, a rewrite may be the best option. However, this carries major costs and should be considered only as a last resort (in my opinion).

## Learn More About Refactoring

Would you like to learn more about how regular refactoring can improve your team's software delivery? Are you struggling with slow progress and buggy software updates? [Let's chat](../../1.%20Lake%20Wingra%20Software/01%20-%20whoAreWe/#lets-connect)!