**There is no concept of overlapping testcases in different test levels,**

Both are completely isolated

Just because API works fine you cannot guarantee UI works fine.

Imagine all your API tests passing but user not able to use the UI , Imagine all your UI working due to cached information but actual backend is failing.

Ensure more low level coverage like unit test and API test , this ensures that you will have faster test execution and build feedback. This will also ensures faster debugging as your tests will be more focused on component or feature.

In UI test actual business flow and error handling tests

In each test level we have different test scopes.

**Unit test;**

We don't test the business flow but the component and functionality

**Integration Test**

Integration with other components , how stable is the integrated subsystem to be able to be used to extend with higher level components . Like API with UI

**System Test**

Here you test Usability , user interactions , visual regression , business logic and flow.

So there are no concept of overlapping tests in different testlevels


## Meta
- Author: [PDHide](https://sqa.stackexchange.com/users/40022/pdhide)
- [Online version](https://sqa.stackexchange.com/a/45608/52466)