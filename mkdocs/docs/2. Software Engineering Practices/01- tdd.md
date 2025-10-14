# Test Driven Development

I have found no technique that with a higher impact on software quality than __Test Driven Development__, or __TDD__. I'm a huge fan, possibly bordering on fanatic, so just know you will get a very biased view of TDD here. Most teams do not practice TDD, and since most software engineers are very bright people, I assume their reasoning is sound! But to me the results are so clear and so valuable, I just can't imagine going without.

## What is it?

TDD, or Test Driven Development, is a simple, 3-step software development practice. 

First, a developer creates a new automated test that describes some expected behavior of the code. Behaviors are just the various ways your software behaves given different inputs. Here's an example: _"If the user types an invalid character in the field, it should indicate an error by applying a red outline"_. 

At this point, the developer runs the test. However, the expected behavior doesn't exist, so the test will fail. 

![1 - Failing Test](../img/tdd-1.png)

After running the test and watching it fail, the developer writes some code that makes the test pass.

![2 - Passing Test](../img/tdd-2.png)

When every automated test passes, this provides an opportunity to refactor the code.

![3 - Refactor!](../img/tdd-3.png)

After the developer has (optionally) refactored the code, it is time to work on the next incremental feature by writing a new test.

![4 - Loop is completed](../img/tdd-4.png)

As you can see, each of the 3 steps follows one of the others, forming a __cycle__. When developing an application, applying TDD means to repeat the cycle over and over and over again. A concise way to remember this is "__Red-Green-Refactor__".

## Why Test?

The purpose of TDD is to ensure that test coverage remains as high as possible. But test coverage isn't just a metric for its own sake. Let’s step back and ask: why is test coverage important?

What really matters at the end of the day is good software. In other words, the app should work! To make sure it works, we test it out. If the code is complete and it has been manually tested, we can confently deliver the app and call it a day. 

![5 - Overly Simple diagram](../img/tdd-5.png)

If only it was so simple!

The reality for nearly all software is that it is never done; it is always being tweaked and improved. Top software companies like Amazon and Google push new updates to their major products daily or even multiple times a day. There is a term for this: [__Continuous Delivery__](https://martinfowler.com/books/continuousDelivery.html).

![6 - Another cycle](../img/tdd-6.png)

So a tension is born. We want frequent changes to the code, and we want to deliver quickly, but we also want the app to work. Some teams accept the risk of breaking things, and simply don't test. Other teams pay some error-prone humans to test each version of the app before it gets shipped. The third option is comprehensive __automated tests__. Having good test coverage is about delivering __quickly and confidently__.

## Invest in Tests

One argument against TDD is that writing automated tests takes too long, or it is too hard. I won't argue that it takes time and can be difficult, especially at first. But the other side of this equation deserves exploring. When we invest in tests, what do we get for our efforts?

First, as I mentioned earlier, your automated tests replace testing by hand. In many cases __manual testing can be eliminated__ by comprehensive tests. That's probably reason enough to write automated tests.

However, beyond that lies another big return on investment in the form of __developer confidence__. This is somewhat hard to convey if you haven't experienced it, but it's undeniable for many who have worked on well-tested codebases. In short, having tests gives you freedom to make bigger, bolder changes to the code, especially __refactoring__. A great deep dive on this is Matthew Parker's [Why TDD](https://blogs.vmware.com/tanzu/why-tdd/).

## Test First

One of the biggest arguments against TDD is that the whole idea of 'writing the test first' is unnecessary. But I think when you drill down on what makes a good test, the idea of writing them first naturally follows.

The main thing a good test should do is pass when things work as expected, and fail when they don't work as expected. It sounds obvious but it's worth saying. As the author of a good test, a developer needs to verify both of these scenarios. In other words, they must try the test on 2 different versions of the code and see that the test passes under the expected condition, and fails under incorrect conditions.

I really want to drive this point: __if a test has never failed, it's not a good test__. I have encountered many tests that look correct at first glance but never fail due to some bug in the test. 

So a test should fail. The only remaining question is, at what point in development should the test fail? 

* The test fails __first__. Congratulations, you're doing TDD! 
* The implementation comes first, then a test which passes. Then __at the end__, the implementation is temporarily removed to verify the test will fail. This is still effective, but it does add an extra step.

For me, the choice is clear. Only writing the test __first__ gives me the confidence I need while avoiding extra work. That's why I TDD!

## Learn more about TDD

Let's chat about TDD or discuss how adopting TDD could improve outcomes for your team! 

### Resources

* [Test Driven Development - Martin Fowler](https://martinfowler.com/bliki/TestDrivenDevelopment.html)
* [Test Driven Development By Example - Kent Beck (Amazon)](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530)