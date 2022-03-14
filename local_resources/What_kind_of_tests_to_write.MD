You should always pick tests carefully when it comes to test automation. :)

One of the reasons, as you said, is overlap (and with that, execution time and robustness).
An **example** to clarify:

 - Your API has 10 endpoints which might return several different error messages each.
 - **Don't** test each error as a UI test: this will take up lots of runtime and will also cause the highest maintenance. And yes, you'll have functional overlap with API and unit tests.
 - **Don't** test each error as an API test **if** their logic is fully covered in unit tests.
- **Do** write a UI test for one or two errors to make sure they are properly displayed by the front-end. But this is probably a generic system, so if the system works it'll work for any error message. UI tests should be considered as probing the application's flows and see a user can get the job done, not in-depth testing of logic.
- **Do** write API tests for one or two errors to make sure the back-end integration is playing nicely from request to response (beyond the scope of unit tests). Or write more tests for specific cases (e.g. where database access comes into play, which will be mocked in a unit test).

Another reason to think about which cases to automate is simply that not every automated tests is as useful or cost efficient in the long run.
I advise you to look on YouTube for Angie Jones' presentation on "Which tests should we automate" - also see https://slides.com/angiejones/which-tests-should-we-automate#/20