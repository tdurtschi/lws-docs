# Test Driven Development (Draft)

In my experience as a software engineer, I have found no technique is more powerful than Test Driven Development, or "TDD". 

## What is TDD

TDD is a simple software development practice: First, a failing test is written. Then, an implementation is written that makes the test pass. When developing an application, applying TDD means to repeat these two steps over and over again.

## Why test first?

Although TDD can provide a lot of value, arguments against TDD are out there. I'd like to address just one here, which is the idea that writing the test *first* is unnecessary.

Consider the following XUnit test:

```csharp
public async Task New_ThrowsErrorIfDuplicateItem()
{
    var service = new ItemService(new InMemoryItemRepository());

    var createItemDto = () => new CreateItemDto()
    {
        Value = "false",
        ItemHref = "https://example.com/item",
    };

    Assert.ThrowsAsync<DuplicateItemException>(async () =>
        await service.New([createItemDto(), createItemDto()]));
}
```

In this case, I first wrote the function `ItemService.New` which throws the duplicate error, then wrote the test which creates duplicates. The test passed. Nice!

Then I removed the duplicate check from the service under test. I re-ran the test expecting it to fail, because now it can't throw the expected error. However, when I ran the test, I was surprised to see that it passed! 

But how? In this case, `ThrowsAsync()` is asynchronous, so it must be awaited. Currently, the test exits with no failures, because the test finishes before the asynchronous operation throws the exception.

Here is the point... if you don't observe the test failing for the expected reason when the implementation is missing, then you don't actually know if your test tests the code you think it does.

To put it another way, in order to have confidence in the test suite, you must test the test. When the functionality is not correct, we must observe the test failing for the expected reason.