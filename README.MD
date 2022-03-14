(Automated) Software Testing - Advanced topics
==============================================


## What is this? / Purpose
For software development there seems to be no book (/consolidated resource) on advanced topics on (auto) testing - Something like follow-up guide on auto testing after one is familiar with the basic concepts (Like if you read a programming book and now need to learn about software architecture) (See also [this question on Stackexchange](https://sqa.stackexchange.com/questions/49876/exhaustive-resources-on-concrete-advanced-test-automation-practices).

## Copyright infringement
I don't mean to infringe anyones copyright with the *offline versions*. They are there to prevent dead links for the future. If you feel infringed, please contact me or leave a bug report.



# Collection of topics

## Testing types

- Testing static values (most basic form: assert_equal (foo(5), output=25)
- Fuzz Testing: Basically brute force testing [offline](local_resources/Test_Type_Fuzz_Testing.html) | [online](https://www.tutorialspoint.com/fuzz-testing-fuzzing-tutorial-what-is-types-tools-example)

## Testing Areas / Testiong circumstances
- Load testing: *How does the app work under (heavy) work load?* [online](https://www.tutorialspoint.com/load-testing-tutorial-definition-how-to-example)<br>

- Backend testing: [online](https://www.tutorialspoint.com/backend-testing-tutorial-what-is-tools-examples)

## Misc
The following list links to various topics.

- Robert Nystrom - Game Programming Patterns: How a test suite should look (don't remember concrete chapters) [online](http://gameprogrammingpatterns.com/)
- Justin Searls - How to stop hating your test suite [youtube](https://www.youtube.com/watch?v=VD51AkG8EZw)

- About What kind of tests to write/ to not write: [offline](local_resources/What_kind_of_tests_to_write.MD) | [online](https://sqa.stackexchange.com/a/45609/52466)

- More scientific approach on *what tests to automate* [youtube](https://www.youtube.com/watch?v=VL-_pnICmGY)

- About overlapping tests: [offline](local_resources/overlapping_tests.md) | [online](https://sqa.stackexchange.com/a/45608/52466)

- About end-to-end testing: [offline](local_resources/End-to-End_Testing_Tutorial.html) | [online](https://www.tutorialspoint.com/end-to-end-testing-tutorial-what-is-e2e-testing-with-example)



# Open questions

For the following questions, I couldn't yet find a topic.

- How do you express the "functional dependency order" of tests? <br>
I.e. `test2` makes use of functionality `test1` tests exhaustively. How do I express that in a test? Background: I'd If test1 and test2 both fail, it should be clear, that test1 is the one I should look for an error first.

- How do I express priorities for tests? <Br>
E.g. there is `test_show_error_message` and `test_software_starts_up`. `test_software_starts_up` is the the test with more priority and if anything happens should be looked at first. How do I express that?

- How do I express that tests take only short time or a long time to test?

- How do I express that tests have external dependencies?

- Unit tests, Integration Tests, System Tests, ... Do I have a completely separated test system for each of these? If yes, How do I make sure to not forget to start up each of them after a change?

- How should I implement the same test with many different inputs? <br>
E.g. I want to test an `add(a,b)` function: do I have many different tests with rather silly names like `test_test_lower_bound` and make it difficult to overview or do I use some kind of CSV table to feed in data? Pros? Cons?

- How do I handle database test? <br>
 Do I build up and destroy a database server everytime a test starts that needs the database? Do I use one huge test database containing all test data for all tests and use transactions and rollbacks? What I test code that finishes transaction? What I I'm working with a MySQL database?

- How do I maintain all of the tests?
