This document identifies CWDS Testing standards in an effort to help improve software quality and have common standards across development teams. The CWDS project comprises of several vendors with different testing philosophies and standards, which can cause confusion among teams that interact. This document will outline testing expectations among all team members to ensure common coding standards are followed.

# Standard
It is a CWDS requirement that all code must be fully tested. Developers are responsible for creating tests while developing code. This includes tests for new code as well as modifying existing tests and creating test for code that was never properly tested. There are no absolute requirements about which tests are required, each story may require a different set of tests. However, most code will require unit tests and functional test. All tests should be created while the code being developed, where possible, a TDD approach is desirable.

Several types of tests exists and should be written for various purposes. Typical development should include unit/integration tests along with Acceptance/Functional tests. Any UI work would include ADA testing. Load and Performance testing and smoke testing are special cases. Special efforts will add tests to these testing suites.

* **Unit Tests** All Code should have Unit Test and have nearly 100% code coverage. Adhering to TDD practice ensures this requirement is met. Integration Tests are a special form of unit tests and should be used similarly. Integration tests take longer and require more resources and should be used sparingly. Prefer unit tests over integration style tests where possible.
* **Functional/Acceptance Tests** All Major functionality should include Functional/Acceptance tests. Tests should include normal execution paths and some error handling. Not all code paths can or will be tested. The focus for Functional and Acceptance Tests are to test the app from an external black box perspective focusing on external behavior.
* **Cross Browser Tests** When creating Functional and Acceptance tests, all major supported browsers should be targeted. This includes current versions of IE, Chrome, and Firefox. Check with current standards for details.
* **ADA Tests** ADA tests include manual and automated tests. Developers should check for ADA issues manually prior to completing story. Any tests that can be automated should be implemented.
* **Smoke Tests** Developers are required to have a suite of smoke tests to verify the application is functional.the tests will perform various tests and report the outcome in a way that can be automated and monitored. Test must be able to run in production, which would prevent any writing to the DB.
* **Load and Performance Tests** Load and Performance tests are created during performance testing efforts rather than at normal code development time. Performance Tests may focus on specific scenarios depending on what is being tested. Load Tests should mirror Functional and Acceptance tests as well as any other cases identified.

# Unit/Integration Testing
Unit and Integration testing tests are the primary method of testing code components. Unit Tests focuses on the smallest testable components of code and allows for extensive testing of all code paths. CWDS standards are to write unit tests for all code. Please see the Unit Testing Standards document for more detailed information.

# Functional/Acceptance Testing
Functional and Acceptance Tests ensure code meets requirements and works as requested. Functional and Acceptance Tests are black box style tests that test the systems specifications or use cases and focusing on external behavior. Functional and Acceptance Test determine if requirements are met.

Front end  web applications will use a web driven tool such as Selenium or Capybara to test the web application. These tests typically log in and perform various use case scenarios. The web app will implicitly test the back end systems via the API.

Back end applications will use an automated REST API testing tool to verify the API functions as expected. These tests typically involve logging into the system and executing a request against a single API endpoint.

Testing every code base permutation with Functional and Acceptance test is impractical. Instead, developers should focus on writing tests for application features success paths and key error scenarios. Not all errors can be tested, but a reasonable amount of error testing should be tested. New features will require new tests while updating existing code requires modifying existing tests. It is the developers responsibility to keep all tests up to date and ensure all tests exists.

# Cross Browser Testing
Tests that run in the browser must be tested across the CWDS supported browsers the best they can.
 Some features may not be equally testable in all browsers.
Test should target current versions of Microsoft's Edge and IE browsers, Chrome, and Firefox.

# ADA Testing
Americans with Disabilities Act (ADA) is a specialty test to ensure the web application is accessibility compliant. Many tests are manually checked. The goal is to automate as much as possible based on availability of tools.

As for the tools that we should use for testing against accessiblity and more on accessibility standards for CWDS-CARES can be accessed [here](https://github.com/ca-cwds/research-design/wiki/Accessible-Design).

Tests based on the following checklists would help dev's to be more ADA compliant:
* [WCAG checklist from WebAIM](https://webaim.org/standards/wcag/checklist)
* [JSX checklist from The A11Y Project](https://a11yproject.com/checklist.html)


# Smoke Testing
Smoke Tests verify an application is working correctly by checking a limited set of key functional areas. Smoke Tests are often performed after a deployment to ensure application was deployed and restarted or periodically as part of a health check. Tests should be limited in scope rather than a full suite of tests. Tests may include existing functional or acceptance test or other tests. Smoke Tests should provide a pass fail response so test can be automated and appropriate actions can be taken when a test fails. Smoke Tests may be required to run in Production Environment, which limits the ability to write to a database.

# Load and Performance Testing
Load and Performance testing are specialized tests that focus on application performance. These tests are typically created during performance activities rather than during feature development. Typical Load Tests are use case based scenarios that will relate to Functional and Acceptance tests. Specialized Performance Tests can be created to test and monitor specific characteristics such as how the system handles load and what the response times are. Load testing typically involves testing the Web Application layer to gain insight about how the application as a unit performs. Besides testing the application holistically, subsystems can be targeted for measuring performance. Testing can be performed against the API services, Authentication servers, Databases, etc.
