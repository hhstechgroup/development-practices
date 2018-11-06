This document identifies CWDS Testing standards in an effort to help improve software quality and have common standards across development teams. The project comprises of several vendors with different testing philosophies and standards, which can cause confusion among teams that interact. A common testing strategy helps set testing expectations among all team members.

# Standards
Developers are responsible for testing there code. All code must be tested and typically will include multiple types of tests. There are no absolute requirements about which tests are required, each story may require a different set of tests. However, most code will require unit tests and functional test. All tests should be created along side the code being developed.

* **Unit Tests**: All Code should have Unit Test. Code should have nearly 100% code coverage. Integration Tests are a form of unit tests and should be used similarly. Integration tests take longer and require more resources and should be used sparingly. Prefer unit tests over integration style tests.
* **Functional/Acceptance Tests** All Major functionality should include Functional/Acceptance tests. Tests should include normal execution paths and some error handling. Not all code paths can or will be tested. Focus is testing the app from an external black box perspective focusing on external behavior.
* **Cross Browser Tests** When creating Functional and Acceptance tests, all major supported browsers should be targeted. This includes current versions of IE, Chrome, and Firefox.
* **ADA Tests** ADA tests include manual and automated tests. Developers should check for ADA issues manually prior to completing story. Any tests that can be automated should be,
* **Smoke Tests** Smoke Tests verify key areas of an application is working correctly. Smoke Tests are often performed after a deployment. Tests should be limited tests which may include functional or acceptance test or other tests to check functionality. Care must be taken to ensure tests can run in any environment, including production. Make database changes typically is not advisable.
* **Load and Performance Tests** Load and Performance tests are created during performance testing rather than at code development time. Performance Tests may focus on specific scenarios depending on what is being tested. Load Tests should mirror Functional and Acceptance tests as well as any other cases identified.

#Unit/Integration Testing
Unit and Integration testing tests are the primary method of testing code components. Unit Tests focuses on the smallest testable components of code and allows for extensive testing of all code paths. CWDS standards are to write unit tests for all code. Please see the Unit Testing Standards document for more detailed information.

# Functional/Acceptance Testing
Functional and Acceptance Tests ensure code meets requirements and works as requested. Functional and Acceptance Tests are black box style tests that test the systems specifications or use cases and focusing on external behavior. Functional and Acceptance Test determine if requirements are met.

Front end  web applications will use a web driven tool such as Selenium or Capybara to test the web application. These tests typically log in and perform various use case scenarios. The web app will implicitly test the back end systems via the API.

Back end applications will use an automated REST API testing tool to verify the API functions as expected. These tests typically involve logging into the system and executing a request against a single API endpoint.

Functional and Acceptance Tests are ran via a public interface which becomes impractical to tests every permutation. Developers should be focused on writing tests for application features success paths and key error scenarios. Not all errors can be tested, but a reasonable amount of error testing should be tested. New features require new tests while adding new behavior to existing features typically require modifying existing tests.

# Load and Performance Testing
Load and Performance testing are specialized tests that focus on application performance. These tests are typically created during performance activities rather than during feature development. Typical Load Tests are use case based scenarios that will relate to Functional and Acceptance tests. Specialized Performance Tests can be created to test specific characteristics. Load testing typically involves testing the Web Application layer to gain insight about how the application as a unit performs. Targeted testing can be performed against the API services, Authentication servers, Databases, etc.

# ADA Testing
Americans with Disabilities Act (ADA) is a specialty test to ensure the web application is accessibility compliant. Many tests are manually checked. The goal is to automate as much as possible based on availability of tools.

# Cross Browser Testing
Tests that run in the browser must be tested across the CWDS supported browsers the best they can.
 Some features may not be equally testable in all browsers.
Test should target current versions of Microsoft's Edge and IE browsers, Chrome, and Firefox.

# Smoke Testing

