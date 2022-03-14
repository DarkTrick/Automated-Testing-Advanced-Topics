
**TL;DR**: you will have overlap between E2E and API integration test cases, in terms of the same endpoints being exercised in both and *that's OK* - it helps you figure out where the problem is if (...when) something goes wrong.

When working with a codebase that doesn't currently have comprehensive automated testing, _start with the E2E(/functional/UI) tests_. Why?

 1. Automating the app through the UI workflows helps build empathy for the users - what are they using this for, and how do they do it?

 2. These tests let you check the software actually delivers the value it's supposed to; your users don't care about API calls or functions! Note that this would be different if your API was a product in itself, not just consumed by the web client.

 3. From a more technical testing perspective, lower-level tests will likely require some changes to implement (e.g. to introduce appropriate boundaries to test at); code written without thinking about testing is often difficult to test. You need the higher-level tests to give you confidence those changes were made correctly.

This will likely lead to a place where you have too many E2E tests, characterised by overly long test run times, but you can now start pushing tests down the stack to integration and unit tests. Focus on maintaining a set of key workflows (this can be a good conversation with the product people in your team - does everyone know what the key workflows *are*?) at the E2E level, then push the less important paths and repetition to lower-level tests.

In terms of the API tests specifically, there will be a lot of overlap; your E2E test cases should exercise every endpoint at least once (if not, think about whether the unused endpoints can be removed). This overlap is fine, because now if an E2E test fails but the relevant API tests pass you've localised the issue to the UI. But there will be things that are hard to test through the UI. Commonly these are the *unhappy paths*, for example:

 - you probably have validation of inputs at the UI level that prevents the request getting made if they're invalid, but you should still be testing server-side validation; and

 - you probably don't have links to missing resources in the UI, but still want to test 404s.

Similarly there are things that are hard to test through the API, and require a lot of setup and teardown; in this case, push down further to unit test the service/business logic layer (I would *not* recommend unit testing the controller/transport or repository/persistence layers; these tend to be largely boilerplate, if they have a lot of logic it's probably in the wrong place).

## Meta
- Author: [jonrsharpe](https://sqa.stackexchange.com/users/11488/jonrsharpe)
- [Online Version](https://sqa.stackexchange.com/a/45610/52466)
