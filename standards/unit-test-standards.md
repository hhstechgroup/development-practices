#Intent & Goal
In an effort to help improve software quality...

Different teams with different expectations...

This document scope is to identify the Unit Testing Standards adopted for the CWDS CARES project. The project comprises of several vendors with different testing philosophies and standards. CWDS CARES project was initiated with a commitment to Agile and it's practices which include Unit Testing and Test Driven Development (TDD). This document will outline the CWDS Standards that will adhere to industry best practices and to standardize testing practices.

#Background
Unit Testing has been an important part of the Agile community since the beginning. Unit testing benefits has expanded beyond just testing that code works. Unit tests can be used to:
* design code
* documentation
* working examples
* explore solutions
* regression testing
* debugging

Unit tests are simple tests that test the smallest components of software, often a public method in an class. A true unit test does not try to test dependencies or try to run separate processes in order to test. By following standard unit testing practices, code will have a tendency to be cleaner, clearer, and have less bugs. All code should strive for tests.

Test Driven Development (TDD) is a subset of Unit Testing. TDD goes beyond just testing that code is functional. It's main focus is to improve the quality of code by driving the development of it. TDD is a testing philosophy that starts with the test first followed by the implementation. By following the pattern, only the required code to solve that problem is coded and a test created for all code written.

TDD is not without criticism and some interesting debates have occurred various public discussions. One main issue is TDD involves a different workflow than most developers are used to. It takes time to get comfortable with it, and many choose not to devote the time. Testing is an art and it is easy to create bad tests and code despite using TDD. TDD doesn't enforce you write good code, but it does make it harder to test when the code violates best practices.


#Standards
#Maturity Model
A maturity model is concept used to define and assess a continuum for continuous improvement. A Unit Test Maturity Model breaks down unit tests by test coverage. We could break down unit test by other factors, but currently we will limit them by quantity.

##Level 0: No Unit Test
Level 0 is when no unit tests exist. This was often the state of code created a decade ago and is typified by legacy code. This level of testing does not meet CWDS CARES standards and should be avoided.

##Level 1: Limited Unit Test
level 1 is having "some" tests. This may include one person adding lots of tests and others not contributing, focus on delivery over "perfection", not concerned with thorough testing, or thinking other tests will fill in the gaps.

Level 1 is an improvement over level 0 but does not meet CWDS CARES standards. There is no ability to ensure modules are doing what they are expected to do. Although some code is tested, it doesn't provide enough testing coverage to properly say the application is tested. This level of testing provides little benefit to the application and development cycle. Usually limited to ensuring a specific algorithm or method works.

##Level 2: 80% Unit Test Coverage
Level 2 has 80% code coverage and is the low bar for CWDS CARES. Having 80% code coverage provides a good amount of testing for the code base. The majority of functionality and is typically considered the minimum in the Testing world. This allows code to be reasonably tested as well as provides some sort of documentation and regression testing that are useful for refactoring or modifying code for maintenance or additional features. Developers can understand how the code works by reviewing existing tests.

##Level 3: ~100% Unit Test Coverage
Level 3 has near 100% code coverage. In actuality, this is a bit difficult to achieve and is an ideal. There is some code that often is too trivial to test, such as getters and setters and which maybe left out of the metrics for simplicity. Having near 100% test coverage ensures that the code has been tested and protects against introduction of errors when modifying behavior or refactoring code. It also provides documentation on how code is expected to work by providing working examples. However, level 3 does not ensure tests are of quality and code is thoroughly tested.

##Level 4: TDD
Level 4 is near 100% code coverage and is the gold standard. TDD by nature provides full test coverage. The major difference in level 3 and 4 is the method of testing. TDD is a technique that impacts the design of code, which should result in code that follows best practices and has fewer errors. TDD requires a failing test to be created first, followed by enough code to pass the test. Some refactoring occurs and the process is repeated. The idea is use tests to drive the functionality of the class. The Test is the client of the class being created and the behavior of the class is determined based on the test interactions.

Level 4 not only fully tests the code, provides regression tests, and documents code, it also helps design code. Code tends to be cleaner, clearer, more concise, and cohesive.

#Unit Test
Unit Test promote the following benefits:
* Better Design
* Documentation/Examples
* Regression Testing
* Faster Development
* Faster Debugging


#Integration Tests

#Best Practices
Unit tests are subject to bad code themselves. Several best practices exist to prevent tests from becoming a drag on development

* Do not mock or modify the Class under test for testing purposes.
* Keep tests as simple as possible
* Test only one thing per test. Each test should fail for one and only one reason.
* Listen to the tests. Tests that are painful to run or write are suggesting there is something wrong.
* Limit setup. Too much setup is suggesting the class under test is doing too much
* Test name should be clear. Should explain what is being tested and any important information. Example: executeShouldReturnFalseWhenNotSuccessful()
* Common code should be moved to the setup
* Setup should create a base successful scenario. Each test then can modify from a happy path scenario.
* Keep Tests Dry. Think of ways to reuse fixtures. Don't create one fixture per test.
* Follow naming standards.
* Keep Tests small and focused.
* Do not rely on test order.
* Prefer unit tests over integration tests
* Use Integration tests for any code you do not own. (Any imported code that can be changed by someone outside your realm of influence)
* Limit use of mocking for code you do not own. Mocks may not warn you when object interface changes.
* Keep tests small and fast. Unit tests are fast. Integration tests are slow.

Test Smells:
* Test are difficult to write
* Tests are difficult to manage
* Tests are difficult to run
#TDD
