This document identifies CWDS Functional and Acceptance Testing standards in an effort to help improve software quality and have a common standard across development teams. The project comprises of several vendors with different testing philosophies and standards which can cause confusion among teams that interact. A common testing strategy helps set testing expectations among all team members.

CWDS CARES project was initiated with a commitment to agile and it's practices with the expectation that teams will be following such practices. Writing automated Tests is a core agile practice that is expected to be followed by all team members. Functional and Acceptance tests are specialized tests used to verify and validate the application externally from a user's perspective.

# Standards
The CWDS testing standard is to test all major application functionality with functional and acceptance tests. Functional tests focus on the user interface of the application and not the internal implementation detail. The tests should not rely on detailed knowledge of the application architecture, but only on application behavior. The user interface may be a web page for a web based application, an API endpoint for a RESTful back end service, or any other interface the user would access the system through. A user is any agent that accesses the system. This would include both human and machine users.

Functional tests exercise code from a high level and 100% complete test coverage is not practical nor should be expected or strived for. Since it is not feasible to test every permutation of the code, a representative collection of tests suffices. The focus should be on testing all acceptance criteria, use cases, requirements, and typical error handling. This leaves much of the data permutations and some scenarios untested from a functional level. These tests should already be tested with unit tests. If deficiencies are found or current tests are not sufficient, then additional tests should be added.

Testing is always be part of the development process. Tests should be written whenever new behavior is added to the code base. When existing code is changed, the tests should be updated. Changes may require changing lots of code. The developer is responsible for keeping tests up to date and in good condition. Changes may require code or tests to be refactored. Tests should never be ignored when making code changes. The developer must understand the impact of their changes and update both tests and code as appropriate. All bugs should have tests to ensure the bug never occurs again. The developer is expected to create new tests whenever a bugs is identified and is being fix.

Browser interface tests should run against all the major supported browsers and be compatible with the last several releases. It is not sufficient to test against just one browser. See official browser requirements for more details.

# Background
Functional And Unit testing are important to verify and validate the application has correct functionality. The functional tests focus on external business facing behavior of the application. Functional tests verify the "right thing was built" where unit tests validate "the thing was built right". The former ensures the application does what it is supposed to where the latter tests that it works correctly.

Acceptance tests are related and similar to functional tests. Where functional tests focuses on testing functionality, acceptance test focus on the acceptance criteria for a story. The acceptance criteria is typically defined in the story and is the criteria the approver will judge the story against. Acceptance tests are not limited to UI testing, but typically are found in these types of tests. Some maybe implemented in unit tests depending on the scope of the implementation.

Functional and Acceptance tests are high level tests that tests the application externally as a black box. No special knowledge is known of the application other than how to interact with its interface. The entire application ecosystem or environment will be required to be running since all dependent services will be exercised. This includes authentication servers, Databases, Search Engines, Geo Services, and other CWDS or third-party applications or services.

Smoke Tests are a specialized set of tests that test that the application is in a suitable running state. Often these are used after a deployment to ensure application has started and is working as expected. A good test exercises basic components and should only be a few minutes in length. Other types of tests ensure the application is correct while smoke tests validates the app is running correctly. Since an application requires many integrated systems, it is worthwhile to test dependent systems to ensure the networks are reachable, credentials are valid, and servers running.

# Best Practices
Tests should be repeatable. Tests should be able to run multiple times in a row or perform a rerun if the test should fail or be terminated in the middle of a run.

Long running and/or expensive tests should be consolidated to prevent excessive run times. Typically a web application may require some setup and signing in which may take excessive time. Individual tests should focus on a use case and test several features at once. But features in a tests should all be related to a specific use case.

A Test that maintains state, such as a web application, may fail in the middle of a test. Test suites should be able to recover from one or more failing tests. Each test should not rely on previous test data and should start with a known location in case last test did not end on a specific page.

User interface tests can sometimes be fragile. Graphical User Interfaces such as web pages often change during development and during it's lifetime as new features are added and the look and feel changes. Developers should separate the testing of behavior from the page components. Techniques such as a page object can help encapsulate page components so the tests operate on an object that represents a page, but which encapsulates the details, which make changes much easier.

Special consideration needs to be placed on storing credentials. Credentials expire or change over time. Tests should account for acquiring and updating credentials, especially if tests are automated. Each environment may have separate credentials as well.

It is best if tests do not rely on existing data. Data can change over time. A good test will always create the data it needs to work with. However, in some cases we cannot create data as needed. Care should be taken in these cases. A premium is placed on automatically running all tests continually. Data tests that fail frequently or otherwise disrupt test running is not desirable. A suitable strategy should be taken to ensure the code is tested and that the tests are stable.

Smoke tests should be written in a way that allows them to be ran in all environments. This would include production and production like environments. Credentials can be difficult to procure in these systems. Also, writes to the DB should be carefully considered. Creating a referral in production would not be acceptable and would not create a good smoke test.

Tests are expected to be automated during the build process. New code checked into the repository should trigger the build to execute all tests to ensure new code does not break existing code. This type of regression testing will prevent code from regressing over time.
