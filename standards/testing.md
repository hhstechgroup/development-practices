This document identifies CWDS Testing standards in an effort to help improve software quality and have common standards across development teams. The project comprises of several vendors with different testing philosophies and standards which can cause confusion among teams that interact. A common testing strategy helps set testing expectations among all team members.

# Standards
Developers are responsible for testing there code. All code must be tested and typically will include multiple tests. Planning must take into account testing and code is not complete until tests are complete.

* **Unit Tests**: All Code should have Unit Test. Code should have nearly 100% code coverage.
* **Functional/Acceptance Tests** All Major functionality should include Functional/Acceptance tests. Tests should include normal execution paths and some error handling.
* **Cross Browser Tests** When creating Functional and Acceptance tests, all major supported browsers should be targeted. This includes current versions of IE, Chrome, and Firefox.
* **ADA Tests** ADA tests include manual and automated tests. Developers should check for ADA issues manually prior to completing story. Any tests that can be automated should be,
* **Smoke Tests** Smoke tests should check key areas of an application to ensure app is working correctly. These should be some sort of limited tests which may include functional or acceptance test or other tests to check functionality.
* **Performance Tests** Performance tests are created during performance testing. Tests should mirror Functional and Acceptance tests as well as any other cases identified.
#Unit Testing
Unit testing tests are the primary testing artifacts for testing code components. It allows for testing all aspects of code. CWDS standards are to write unit tests for all code. Please see the Unit Testing Standards document for more detailed information.

# Functional/Acceptance Testing
Functional Tests are black box style tests that test the systems specifications or use cases. Acceptance Test determine if requirements are met. Both tests have lots of overlap and will be referred to together.

Front end  web applications will use some sort of a web driven tool such as selenium or capybara to test the web application. These tests typically log in and perform various use case scenario tests. The web app will implicitly test other back end systems via the API.

Back end application will a rest API testing tool to verify the API functions as expected. These tests typically involve logging into the system and executing a request against a single API endpoint.

Not every permutation can be tested. Developers should be focused on writing tests for the application key features. The successful test (Happy Path) and relevant error tests to ensure errors are handled correctly. Creating new features will require new tests. Adding to existing features typically require modifying existing tests.

# Performance Testing
Performance testing are specialized tests that focus on application performance. Tests These tests are typically not created during development, but during performance activities. Typical performance load tests are usecase based scenarios. Specialized performance tests can be created to test specific characteristics. Performance testing typically involves testing from the Web application layer to gain insight about how the application performs. Targeted testing can be performed against the API services, Authentication servers, Databases, etc. 

# Cross Browser Testing
# ADA Testing
# Smoke Testing

