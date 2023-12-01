# Code design patterns

This pages contains a list of code patterns that we use in developing SS3D. We recommend you to take a look as those patterns improve the code quality, testability, reusability.

## Humble object pattern

This design came from the necessity to answer the following question : How do we make code testable in a class tightly coupled with its environment ?

In our case, that's what happen in our codebase with everything inheriting from monobehaviour, or worse, from networkbehaviour. All networkbehaviour objects are tightly coupled to both Unity framework, and Fishnet framework.

To remedy to this issue, we split the object in two, one  "Plain Old Class Object", containing the logic we want to test, and one object tightly coupled to our framework, handling only framework stuff.

A great introduction to this concept in the following video :&#x20;

{% embed url="https://www.youtube.com/watch?v=OecJvh8Zvc4" %}

If you want to learn more about it, [XunitPatterns.com](http://xunitpatterns.com/Humble%20Object.html) goes into great details.

In our codebase, you can see this pattern in action with the Container and AttachedContainer class. The container class is the testable object containing most of the logic, the AttachedContainer class contains the framework logic, networking and Unity stuff.



## (Soft) Humble object pattern



Sometimes, applying a strict humble object pattern causes more trouble than good. Duplicating code, loss of encapsulation, code difficult to read ... It's not always worth it.

We encounter many of those issues while working on the Item class. After many attempts, ending with overly complicated and hacky codes, we were not satisfied.

That's when we decided to not apply a strict humble object pattern (splitting a class in two different classes), but rather to draw some inspiration from it to come with the following set of rules :&#x20;

* Keep everything in the same class.
* Separate framework and logic code in different methods.
* Make logic in method involving framework code as simple as possible, consider this method untestable.
* Write code to make it work in both framework and unit test context.

Instead of splitting in two different classes, we split our code in different methods, and/or we rewrite it so it works as well  in both framework and unit test context.

### Practical case, the SetContainer method of the Item class.

