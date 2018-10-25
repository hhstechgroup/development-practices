In an effort to help improve software quality...

Different teams with different expectations...

This document scope is to identify the Unit Testing Standards adopted for the CWDS CARES project. The project comprises of several vendors with different testing philosophies and standards. CWDS CARES project was initiated with a commitment to Agile and it's practices which include Unit Testing and Test Driven Development (TDD). This document will outline the CWDS Standards that will adhere to industry best practices and to standardize testing practices.

# Standards
The CWDS standard for testing is to have tests for all code. This includes unit and functional tests. Unit tests include integration tests and functional tests includes acceptance test. The desire is for developers to be doing TDD, but since that requires some learning and discipline, that is a labeled a goal that should be strive for.

Nearly all code should be tested. This should be close to 100% coverage which includes all paths through the code. Changes to the code should cause some test to break. Typically the only code not tested is code that returns or sets a property

# Background
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

# Maturity Model
A maturity model is concept used to define and assess a continuum for continuous improvement. A Unit Test Maturity Model breaks down unit tests by test coverage. We could break down unit test by other factors, but currently we will limit them by quantity.

## Level 0: No Unit Test
Level 0 is when no unit tests exist. This was often the state of code created a decade ago and is typified by legacy code. This level of testing does not meet CWDS CARES standards and should be avoided.

## Level 1: Limited Unit Test
level 1 is having "some" tests. This may include one person adding lots of tests and others not contributing, focus on delivery over "perfection", not concerned with thorough testing, or thinking other tests will fill in the gaps.

Level 1 is an improvement over level 0 but does not meet CWDS CARES standards. There is no ability to ensure modules are doing what they are expected to do. Although some code is tested, it doesn't provide enough testing coverage to properly say the application is tested. This level of testing provides little benefit to the application and development cycle. Usually limited to ensuring a specific algorithm or method works.

## Level 2: 80% Unit Test Coverage
Level 2 has 80% code coverage and is the low bar for CWDS CARES. Having 80% code coverage provides a good amount of testing for the code base. The majority of functionality and is typically considered the minimum in the Testing world. This allows code to be reasonably tested as well as provides some sort of documentation and regression testing that are useful for refactoring or modifying code for maintenance or additional features. Developers can understand how the code works by reviewing existing tests.

## Level 3: ~100% Unit Test Coverage
Level 3 has near 100% code coverage. In actuality, this is a bit difficult to achieve and is an ideal. There is some code that often is too trivial to test, such as getters and setters and which maybe left out of the metrics for simplicity. Having near 100% test coverage ensures that the code has been tested and protects against introduction of errors when modifying behavior or refactoring code. It also provides documentation on how code is expected to work by providing working examples. However, level 3 does not ensure tests are of quality and code is thoroughly tested.

## Level 4: TDD
Level 4 is near 100% code coverage and is the gold standard. TDD by nature provides full test coverage. The major difference in level 3 and 4 is the method of testing. TDD is a technique that impacts the design of code, which should result in code that follows best practices and has fewer errors. TDD requires a failing test to be created first, followed by enough code to pass the test. Some refactoring occurs and the process is repeated. The idea is use tests to drive the functionality of the class. The Test is the client of the class being created and the behavior of the class is determined based on the test interactions.

Level 4 not only fully tests the code, provides regression tests, and documents code, it also helps design code. Code tends to be cleaner, clearer, more concise, and cohesive.

# Unit Test
Unit tests are the standard testing practices. Nearly all code should have tests. And the majority of those tests should be unit tests. Unit tests ideally should be short small tests that test one thing. Each behavior of a class/method is tested separately. Ideally everything that a class/method does is tested.

Unit Test promote the following benefits:
* Better Design
* Documentation/Examples
* Regression Testing
* Faster Development
* Faster Debugging

# Integration Tests
Integration tests are used to test multiple code units/modules. This may include two or more different classes in the same codebase, a library component, or an external service or process. The main use case is libraries and external code. Integration tests should be used to test code that is not easily tested with unit tests.

Integration tests are typically less desirable than unit tests due to the speed in which they run. An integration tests typically has to start up some sort of service which takes time. A service SHOULD be restarted between each test but often that is changed to start once per test in order to save time. This approach can lead to unstable tests and is not recommened. Running integration tests may feel quick, but they are relatively much slower and that time adds up and is compounded over time. It's not uncommon for test suites heavy on integration tests to take and hour, while comparble unit test suites can be done in seconds to a few minutes.

Unit tests will either mock a dependent object or use the real one if possible. Integration tests are never mocked. Depending on the language, mocking a library or class you do not have control of is dangerous. If the interface changes, the mock will continue to work and will not advise you of the error. Mocking out library classes should be done with care.

# Test Driven Development (TDD)
Test Driven Development (TDD) is a technique used to develop code popularized by Kent Beck and is considered a core agile principle. TDD helps the developer create code that is smaller, cleaner, and adhears to best practices. It does this by focusing on code from the user of the code's perspective. Only code that is needed is implemented. Becuase setting up lots of dependencies is painful, classes tend to be smaller.

TDD is a standard CWDS has commited to and developers should strive to reach this standard. However, TDD takes practice and a certain amount of skill. The best way to learn TDD is simply to do it, and if possible, pair with someone experienced with it.

TDD is a very simple concept. Write a test before the code is written. The test MUST fail. Only after the test has failed is the minimal amount of code neccesary to pass the test implemented. The test should pass. Refactor any code and/or test. Repeat. This is very simple but very powerful process. The two key areas are failing test and minimal amount of code. A failed test ensures that the test actually is working appropriatly. Often a test will pass when it should fail and the developer thinks the test is good. Minimal amout of code is also very important as only code that is tested is implemented. The tests force the code to take shape. If it canot be tested, then there is no benifit to that feature.

Code coverage for TDD is near 100% since code can only be implemented if there is a test. However, there are some cases where testing may not be necessary. A typical exception is code that is too simple to test. This typically applies to accessor methods that just return a property value. This does not apply to any code with any logic, even if it is trivial. Occaionally there may be some code that is too difficult to test with unit testing. In these cases either integration or functional tests should be used.

# Unit Test vs TDD
Unit tests are not the same as TDD. Unit tests are just tests while TDD is a methodology on how to test and write code. TDD typically involves unit tests but can be applied to other types of tests. Unit tests can be written before, during, or after code has been written. Typically if unit tests are a requirement but not TDD, then only partial coverage is acheived. Real TDD ensures near 100% coverage.

# Best Practices
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

# Test Smells:
**Test are difficult to write**
Keep code small and focused. Keep dependencies to a minimum. Inject dependencies, Don't new up dependencies in methods. Avoid statics.

**Tests are difficult to maintain**
Too many overlapping tests. Class under test is doing too much, refactor into smaller classes. To many dependencies, refactor into smaller classes. Lots of setup required, create common fixtures and refactor class under test into smaller classes.

**Tests are difficult to run**
Tests are fragile. Tests should not rely on other tests or expect data to be availible. Create every thing the test needs prior to test execution.

