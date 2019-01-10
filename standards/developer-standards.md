This documents outlines CWDS Developer Standards and expectations along with basic guidance. The intent is to define developer responsibilities and create a standard set of procedures among all the development groups in an effort to increase code quality and promote a common set of values among teams/vendors. Each developer can then explicitly understand was is expected and can contribute positively to the project.

Agile has long history of practices and core beliefs that impact the quality of code. The following responsibilities, standards, and practices in this document are fairly common and are typically the expectation in high functioning teams. Like all agile practices measurement and review are import to ensure practices are relevant and contribute to delivering quality code.

# Ethics
Developing well crafted software requires more than understanding a languages syntax and semantics. Agile practices and various best practices offer techniques and guidance on programming techniques, principles, patterns, etc. In addition, Robert Martin has created a Programmers Oath to help bind programmers together as a profession. The Programmer's Oath is a set of statements that affirm the Programmer's attention to the key qualities that make agile development powerful. This Oath describes an ethic that can when followed will help drive code quality. The following is a list he created in 2015.

**In order to defend and preserve the honor of the profession of computer programmers,**
## I Promise that, to the best of my ability and judgement:
1. I will not produce harmful code.
1. The code that I produce will always be my best work. I will not knowingly allow code that is defective either in behavior or structure to accumulate.
1. I will produce, with each release, a quick, sure, and repeatable proof that every element of the code works as it should.
1. I will make frequent, small, releases so that I do not impede the progress of others.
1. I will fearlessly and relentlessly improve my creations at every opportunity. I will never degrade them.
1. I will do all that I can to keep the productivity of myself, and others, as high as possible. I will do nothing that decreases that productivity.
1. I will continuously ensure that others can cover for me, and that I can cover for them.
1. I will produce estimates that are honest both in magnitude and precision. I will not make promises without certainty.
1. I will never stop learning and improving my craft.

# Code as a Craft
Code craftsmanship has been at the heart of Agile development since it's inception, and been part of Programming since the earliest days. Kent Beck's Extreme Programming outline several key practices that are common to all Agile development including Test Driven Development (TDD), Continuous Integration, and Refactoring. Andy Hunt and Dave Thomas have have written about career development, architectural techniques, and personal responsibility in their Pragmatic Programmer book. Martin Fowler has cataloged patterns related to refactoring and enterprise development as well as named key concepts. Robert Martin has championed development practices, patterns and principles as well as define Programmer's Oath and books dedicated to code of conduct and software craftsmanship. These individual's along with many more have authored the Agile Manifesto and spearheaded what can know be called Code Craftsmanship.

Code Craftsmanship can be described as a movement to increase code quality, development skills, and to promote code ownership. Development requires a broad set of skills and practices that change over time, but which always aim at producing quality software. Developers will continue to evolve and grow by following best practices and learning the motivation behind those practices.

# Developer Responsibilities
Developers have many responsibilities in addition to writing code. The developer must ensure the quality of the code by following standards, submitting to reviews, testing code, and ensuring the code and build is always in a runnable state. The following lists the major developer responsibilities.

## Standards
Developers have a responsibility to adhere to CWDS standards. These includes team agreed upon standards, testing, developer standards, and other standards that are in effect. Standards provide a mechanism to promote quality code. And as such, they should be reviewed from time to time and updated accordingly. Developers should play a role in reviewing the effectiveness of existing and new rules.

## Code Quality
Developers have a responsibility to ensure a high level of code quality by utilizing best practices and patterns, testing code, and addressing code analysis issues. Developers are not just responsible for their own code, but are responsible for continuously improving the quality of all code. Existing code may need to be refactored and new concepts created or existing ones modified to handle new or changing requirements.

## Communication
Developers have a responsibility to communicate with various individuals and groups during their development activities. Any major changes should be communicated to appropriate individuals or groups. Public API's, libraries, DB schemas, processes, etc are all important to share and discuss. Please do not keep information to yourself.

Appropriate communication channels are a must. Messaging may be appropriate in many cases, but physical communication or other methods may be better suited for specific cases. Documentation that lives with the code may also be necessary.

## Stories
Developers have a responsibility to ensure the stories they work on are in the proper state prior to accepting them for the sprint. Developers are agreeing to complete the story and to the acceptance criteria, so ensure it is clear and defined in a way that can be completed. Refinement Meetings are provided to review and add details to stories and Sprint Planning provides the final check on a story prior to pulling it into the sprint. Developers should ensure:
* The intention of the story is clear.
* The Acceptance Criteria is present, clear, and achievable.
* There is no Ambiguity.
* Any requirements missing or to be determined at a later date should be avoided.
Accepting stories without clear requirements causes code to be incorrectly implemented, wastes developer time, and/or creates incorrect behavior in the system.  Note in many cases a story will not spell out every possible detail such as exact visual design, and that this is OK, and can be easily resolved through converstations with POs, users, and designers.

## Testing
Developers have a responsibility for testing their code. Several layers of tests should be implemented to insure full testing. Unit testing provides the simplest, flexible, and most effective testing and is the default. Developers also must create Functional and Acceptance tests to ensure the entire system works as expected.

Other tests may be required to be implemented in special cases.

## Code
Developers have a responsibility to write code in a manner that is flexible, readable, and interoperable.

Developers have the responsibility to ensure the code meets acceptable quality standards. The developer has the responsibility to ensure the quality by running all tests and quality analyzers and resolving all issues.

## Code Review
Developers are responsible for reviewing and providing feedback as part of code review. Reviewers are responsible for ensuring code meets coding and project standards as well as trying to identify any code issues. The code review process is also a method of sharing ideas and learning alternatives for both the reviewer and reviewee.

Some reviews are subjective, but reasonable requests for changes should be applied. More subjective cases can be arbitrated by a third party. Both sides should explain the rational behind their point of view. In some cases, there may be several acceptable outcomes.

## Documentation
Developers have a responsibility to provide adequate documentation. Public interfacing code (APIs, Libraries, public methods, etc) should provide documentation when not obvious. Documentation pertaining to architecture, major code components, key algorithms, complex structures or processes should also be documented in the repository or other appropriate locations.  

## Code Commits
Developers have a responsibility for checking in reasonable size amounts of code. Large commits should be avoided. Several smaller commits are preferable. In cases where large commits are unavoidable, discussions should occur early so individuals reviewing the code can be aware.

## The Build Pipeline
Developers are response for their code and the stability of the builds. If a check in or merge breaks the build, the developer must resolve the issue. Developers should refrain from checking in code if they will not be available if it breaks

All developers are responsible for the build in general. A broken build is a high priority event and all devs must react to resolve the build as quickly as possible. The individual that checked in the code is primarily responsible, but if they are not available, then other developers are expected to help fix the build. That may mean rolling back code or making code changes.

# Development Standards
Developer Standards outline development expectations. The standards outlined below are generic and mostly abstract from specific languages. Explicit details should be defined in language specific standards that development teams agree with. The standards are expected to be followed by everyone. Any standard that is deemed un-useful should be removed or adjusted as appropriate.

## Coding standards
Coding standards are conventions that improve readability by making code consistent. Teams are required to follow a coding standards that is compatible with other teams. Each language should define a working standards that all teams agree to. Code is expected to adhere to these standards. Code reviews are expected to enforce standards.  Coding standards include conventions for:
* Formatting
* Naming
* Whitespace
* Statements
* Idioms & Practices

Developers are expected to follow the appropriate coding standards, conventions, and idioms, which may be application specific.. Code reviews are the mechanism to help enforce these requirements. Any exceptions should be limited and clearly understood by all developers on the project.

Linting tools and IDE's plugins should be used to enforce rules.

## Code
> Getting software to work is only half of the job. -- Robert Martin

> Make it work. Make it right. Make it fast. -- Kent Beck

In addition to style guides and team agreements relating to code, developers should follow best practices, principles, and processes where appropriate. Developers should continually refactor code to make it better.

Code isn't complete when coding is finished. The developer needs to ensure the code is structured appropriately. Development cycle should contain refactoring sessions to reorganize the code into appropriate modules and components. These modules should make logical sense and fit the model of the application.

Developers should focus on simple well decomposed methods/functions that solve the problem at hand. Solving for future requirements and over engineering should be avoided.

Code should follow standard error handling practices. Defensive programming is expected. Make reasonable checks against the data and not assume anything. Unit Tests allow for exhaustive test cases. Appropriate errors should be handled and reported back to the caller. Error message should be clear and concise and explain what the error was to the level appropriate to the calling party. It is not appropriate to display a SQL exception to the the User.

The following compiled list of phrases describe what good code should be. Developers should be developing with these ideas in there mind.
  * Elegant, efficient, and focused code.
  * Simple, direct, and straight forward.
  * Should be hard for bugs to hide.
  * Minimize dependencies.
  * Code should reveal developers intent not obscure it.
  * Practice YAGNI. Don't design for an unknown future state.
  * Readable by other developers regardless of skill level.
  * Consistent ways of doing things.
  * Follow existing patterns, else refactor.
  * Element of lease surprise.
  * Boy scout rule & broken windows.
  * Write it like you care. Craftsmanship.

## Testing
CWDS follows Agile testing practices. This includes Test Driven Development and Unit Testing. Code that runs against third party libraries or services is expected to contain integration tests. Acceptance and Functional tests tests applications externally and ensure application behaves as expected. All tests should be automated and ran from the build pipeline.

TDD is recognized as a core agile practice and CWDS has stated that it is part of our development practices.

Tests should be made as simple as possible. Tests that require large or complicated setup are signs that the code needs to be refactored into smaller components. Test should also be repeatable, stable, automated. Ideally they should not rely on external states of systems such as the DB, where ever possible.

Tests are part of the code base and need to be refactored as well. Tests should be continuously refactored to keep the tests clean and simple. Developers should not "just add" tests. They should review the existing tests and determine if refactoring is needed.

Tests should be simple to maintain. Changes in the code base should not require dozens of test changes. Care need to be applied when creating fixtures. Using multiple data components such as JSON files will require massive update when JSON changes. Instead, use some sort of builder that can create a default entity that has modifiable fields which can then be used in multiple tests.

Test should be written when bugs are found. These tests guard against the bug returning in the future.

Other tests maybe required for special cases such as smoke tests, performance tests, and any other special tests.

## Committing Code
All code is expected to be deployable at all times. Conditions may arise where a hot patch must be deployed. Developers are expected to ensure the build is stable and the code committed is either able to run as expected in production or is prevented from running.

Stories should be small and ideally code commits should also be small. Large commits are difficult to review and can hide lots of coding issues. This means favoring smaller commits and integrating code sooner.

Commit messages should be explicit about what the commit is. Commit messages should let the reviewer know exactly the purpose of the commits. Multiple commits should Rarely have the same descriptions and should refrain from vague titles like, 'initial check in' or 'fixed bug'. Commits should contain a story number and a brief description. A developer should be able to look through the logs and get a sense of what work was done. A good overview of current good practices for Git commit messages can be found (here)[https://code.likeagirl.io/useful-tips-for-writing-better-git-commit-messages-808770609503].

## Code Review
All code artifacts are expected to be reviewed by team members. Code reviews offer the ability to review the coding style, adherence to standards, review any architectural decisions, and to find bugs. Code Reviews often acts as a second set of eyes.

Reviewers are expected to enforce standards and provide feedback both positive and constructive. It is the responsibility of the reviewer to provide a substantial and honest review. The review should be reasonable and objective. There should be justification for comments provided. Examples and references should be provided. Code should only be accepted if the code meets CWDS and team standards.

Reviewees should seek honest reviews and are responsible for implementing requested changes. The developer should not take offense at the reviews but try and understand the reason the critique was given. Reviews are a place to learn new techniques. The reviewee is expected to conform to standards and style in the code base they are developing in, which may be different from the developers normal coding practices.

Pull Requests should be a size that is easily reviewable. Code that is too large cannot be reviewed in a timely manner. The developer should not make changes once a request has been made. Requests should include appropriate documentation to describe what the request is doing. The pull request should be filled out appropriately and provide an adequate description and link to the story for which it is derived from.

Remember that a code review is a converstation.  If a potential issue is hard to describe within a code review the item can often be discussed in person where understanding is greatly enhanced.

Any developer has the right to reject a pull request if it fails to meet standards, has flaws, or other reasons that make it not ready for deployment. If a pull request is rejected, other developers should honor those reasons. In cases of dispute or in high priority cases, developers should mediate the process. This should be a meeting to assess the issue and how to best remediate them rather than a way to push past a difficult situation.

Some questions to ask durring a pull request:
  * Are they violating best practices or idioms?
  * Was the code developed using TDD?
  * Are there any security issues?
  * Could the code be refactored?
  * Is the code readable?
  * Are there tests?
  * Do the tests actually verify the behavior?
  * Are things named appropriately?
  * Are the right abstractions made?
  * Is code cohesive and loosely coupled?
  * Is the code cohesive?

## API Endpoints
API endpoints are considered public and should receive special care during their creation. API end points should follow RESTful patterns and be named intuitively and clearly expose resource concepts. Similar or duplicate resources should be discouraged. Reuse should be a major consideration in the endpoints name.

Digital Service Applications are considered to be part of shareable resources. It is often difficult to predict which resources will be of use for future clients. By providing generic interfaces to the application we can ensure any client can integrate with out applications. APIs should be generic, clear, documented, and easy to interact with. Endpoints should default to providing all data necessary to create and interact with resources rather than convince shortcuts. This would allow external clients to use the interface with out having to have special knowledge.

## Documentation
Code should include documentation that outlines system architecture, major system components, important concepts, technologies, and algorithms. Documentation should be clear and concise. Github wiki provides a great place to keep documentation. Documentation living outside the repository should have a link pointing to it from the repo.

Code comments should be used to clarify intent or to explain complicated structures or algorithms. The code should be laid out in such a way as to minimize the need for comments. The need for comments should be minimal.

Code intended to be used as a public API should be documented. Documentation should include a description of what the method does and any parameters it takes.

## Security
All Applications are expected to be secured applications. Applications must be continually scanned with security tools to check for vulnerabilities and security issues. Code should follow security standards and best practices. Security standards extend far beyond the scope of this document.

## Code Quality Tools
Code is required to have static code analysis applied. Developers are responsible for overall code quality. Developers must ensure their code is not adding to the code quality issues. Developers must review the results of their analysis reports, even if the build did not break. Team members should be reviewing outstanding issues and should be trying to resolve all outstanding issues.

Developer toolsets should include as many code quality tools as possible rather than waiting until checkin. Tools that can be integrated into the IDE or ran locally should be. Running checks early mitigates delays that may occur after code has been written. Such tools include static code analyzers, linters, and even running automated tests suites.

## Logging
Application should include logging for key events. Key events are anything that would be of interest during auditing or troubleshooting scenarios. User login, request for sensitive information, major coding errors such as exceptions are typical examples. Logs should be set to the appropriate level.

Applications logs should include a traceable ID, date times, message, and other information that would be useful for troubleshooting or information gathering. Logs should contain context around the event rather than a message that stating some even occurred. As much data as possible should be logged to provide context around an event, however, PII information should not be logged.

## Feature Flags
Feature Flags guard blocks of code from being unintentionally executed and should be used to controls access to features not yet ready for use. Feature Flags also allow for some code to be rolled out to customers or to temporarily turn off access to the code. Code should always be modularized to allow features flags to be inserted. This may adjust how the code is designed.

## PII and other security concerns
Care should be taken whenever PII is encountered. Steps need to be taken to guard the data appropriately. PII should not be dumped to a log file or otherwise in appropriately captured. Raise concerns as appropriate when working on stories where PII exists.

Credentials should be guarded closely. Credentials should not be logged or stored in public repositories. Deleting credentials after they have been committed can still be retrieved. Special steps MUST be taken to remove credentials from repositories.

## Basic Developer habits
The following are habits that developers should be adhering to while developing code. The following habits help to raise the code quality by making the code more readable, understandable, simpler, and less error prone.
  * Intention revealing and descriptive names. Names should be clearly named so they reveal what they refer to. Terse, short abbreviations, or non standard names should be avoided.
  * Pick one word per concept. Avoid confusion of having multiple terms for some concept.
  * Avoid Mental mapping. Don't make reader of code translate between domain or application concepts.
  * Cohesion. Code should be cohesive. Keep classes small and focused. Avoid classes that do everything.
  * Small functions & classes. Functions & classes should be small and focused. Break larger classes into multiple classes where appropriate.
  * Break dependencies. Use appropriate techniques to break dependencies. Ensure dependencies are injected into class rather than being instantiated in the middle of a class or method.
  * Code should have singe responsibility rather than doing everything.
  * Should be at the right abstraction. Example, don't process data and save it to DB in same function.
  * Reduce duplication. Code should not be duplicated. Pull duplication out into a common class or even into a library. However, there may be cases where some code duplication is acceptable. Occasionally small bits in test code is ok. Also objects that live in different layers or tiers may have similar properties, but these code bases may diverge overtime or for different reasons.
  * Use Exceptions for exceptional behavior, not for normal error handling or even normal flow. For example, failed password attempt is expected and not an Exceptional Condition.
  * Logging. Log information for Key Events and debugging scenarios. Information should contain context about what happened. The who, what, and why questions can help. When logging for exceptions, it is vital to include this context that also includes the data that caused the exception
  * Comments don't make up for bad code. If you feel code should be documented, first ask if the code is well written and if it could be written clearer. Please document complicated or non-intuitive code. Please try to uncomplicated and make code intuitive. Comments should explain the intent of the code, not describe it.
  * Commented out code. Commented out code is not desirable. Please refrain from commenting that code out. Too often dead uncommented code is left in place and no one knows what to do with it and are afraid to remove it. If it is not being used, remove it. The repository will keep a record of it if it is needed at a later date.
  * Minimize the use of TODOs. Few people have the time to go back and fix the TODOs. They typically live on forever in the code. Make the code the way it is supposed to be the first time. and no one knows what to do with it and are afraid to remove it. If it is not being used, remove it. The repository will keep a record of it if it is needed at a later date.
  * Keep Browser Console clean. Ensure warning and errors are not being reported in the browser console. The console reports errors which should be handled and are unprofessional.
