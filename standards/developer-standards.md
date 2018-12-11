This documents outlines CWDS Developer Standards and expectations along with basic guidance. The intent is to create a standard set of procedures among all the development groups in an effort to increase quality. Each developer can then explicitly understand was is expected and can contribute positively to the project.

# Ethics
Developing software well crafted software requires more than understanding a languages syntax and semantics. Agile practices and various best practices offer techniques and guidance on various topics. In addition, Robert Martin has created a Programmers Oath to help bind programmers together as a profession. The Programmer's Oath is a set of statements that affirm the Programmer's attention to the key qualities that make agile development powerful. The following is a list he created in 2015.

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

# Code Craftsmanship
Code craftsmanship has been at the heart of Agile development since it's inception, and been part of Programming since the earliest days. Kent Beck'sExtreme Programming outline several key practices that are common to all Agile development including Test Driven Development (TDD), Continuous Integration, and Refactoring. Andy Hunt and Dave Thomas have have written about career development, architectural techniques, and personal responsibility in their Pragmatic Programmer book. Martin Fowler has cataloged patterns related to refactoring and enterprise development as well as named key concepts. Robert Martin has championed development practices, patterns and principles as well as define Programmer's Oath and books dedicated to code of conduct and software craftsmanship. These individual's along with many more have authored the Agile Manifesto and spearheaded what can know be called Code Craftsmanship.

Code Craftsmanship can be described as a movement to increase code quality, development skills, and to promote code ownership. Development requires a broad set of skills and practices that change over time, but which always aim at producing quality software. Developers will continue to evolve and grow by following best practices and learning the motivation behind those practices.

# Responsibilities
A developer has many responsibilites in addition to writing code. The developer must ensure the quality of the code by following standards, submitting to reviews, testing code, and ensuring the code and build is always in a runnable state. The following lists the major developer standards.

##Communication
The developer has a responsibility to communicate with various indiviudals and groups during their development activities. Any major changes should be communicated to appropriate individuals or groups. Public API's, libraries, processes, etc are all important to share and discuss.

## Standards
The developer is responsible for adhering to CWDS standards. These includes team agreed upon standards. CWDS has Testing and developer standards that need to be followed. Developer standards also include coding standards specific for each language.

## Stories
Developers have a responsibility to ensure the stories they work on are in the proper state prior to accepting them for the sprint. Refinement Meetings are provided to review stories and Sprint Planning provide the final check on a story prior to pulling it into the sprint. Developers should ensure:
* The intention of the story is clear.
* The Acceptance Criteria is present, clear, and achievable.
* There is no Ambiguity.
* Any requirements missing or to be determined at a later date should be avoided.
Accepting stories without clear requirements causes code to be incorrectly implemented, wastes developer time, and/or creates incorrect behavior in the system.

## Testing
Developers are responsible for testing their code. Several layers of tests should be implemented to insure full testing. Unit testing provides the simpilest and most effective testing and should be the default. Functional and acceptance tests test the entire system and should be provided to ensure the system works as expected.

Test should be written when bugs are found. These tests guard against the bug returning in the future.

## Code
Code should be written in a manner that is flexible, readable, and interoperatable.

Developers are expected to follow the coding standards agreed upon. Any exceptions should be clearly understood by all developers on the project.

Code isn't complete when coding is finished. The developer needs to ensure the code is structured approperatly. Development cycle should contain refactoring sessions to reorganize the code into appropriate modules and components. These modules should make logical sense and fit the model of the application.

Developers should focus on simple well decomposed methods/functions that solve the problem at hand. Solving for future requirements and over engineering should be avoided.

Developer has the responsibility to ensure the code meets acceptable quality standards. The developer has the responsibility to ensure the quality by running all tests and quality analizers and resolving all issues.

## Code Review
All code artifacts are expected to be reviewed by team members. Code reviews offer the ability to review the coding style, adhearance to standards, review any archetectural deciscions, and to find bugs. Code Reviews often acts as a second set of eyes.

Reviewers are expected to enforce standards and provide feedback both positive and constructive. It is the responsibility of the reviewer to provide a substantial and honest review. The review should be resonable and objective. There should be justification for comments provided. Examples and references should be provided. Code should only be accepted if the code meets CWDS and team standards.

Reviewees should seek honest reviews and are responsible for implementing requested changes. The developer should not take offense at the reviews. Reviews are a place to learn new techniques. The reviewee is expected to conform to standards and style in the code base they are developing in. Code check ins should not be so large or requested near a time lime that prevents adequate review.

Some reviews are subjective, but resonable requests for changes should be applied. More subjective cases can be arbitrated by a third party. Both sides should explain the rational behind their point of view. In some cases, there may be several acceptable outcomes.

## Documentation
Code should include documentation that outlines system architecture, major system components, important concepts, technologies, and algorithms. Documentation should be clear and concise. Github wiki provides a great place to keep documentation. Documenation living outside the repository should have a link pointing to it from the repo.

Code comments should be used to clarify intent or to explain complicated structures or algorithms. The code should be laid out in such a way as to minimize the need for comments. The need for comments should be minimal.

Code intended to be used as a public API should be documented. Documentation should include a description of what the method does and any parameters it takes.

## Code Commits & the Build
Developers are responsible for checking in resonable size amounts of code. Large commits should be avoided. Several smaller commits are prefferable. In cases where large commits are unavoidable, discussions should occur early so individuals reviewing the code can be aware.

Commit messages should be explicit about what the commit is. Commit messages should let the reviewer know exactly the purpose of the commits. Multiple commits should Rarely have the same descriptions and should refrain from vague titles like, 'initial check in' or 'fixed bug'. Commits should contain a story number and a brief description.

Code should be checked in early and often. This means favoring smaller commits. If a commit is to be checked in and merged with master, it should leave the application in a valid running state. It should be deployable. Code may need to have a feature flag protecting it to prevent unwanted code from executing in the wrong enviornment. The developer is responsible for ensuring the code is always ready to run.

Developers are response for their code and the stability of the builds. If a check in or merge breaks the build, the developer must resolve the issue. Developers should refrain from checking in code if they will not be availible if it breaks

All developers are responsible for the build in general. A broken build is a high priority event and all devs must react to resolve the build as quickly as possible. The individual that checked in the code is primarily responsible, but if they are not availible, then other developers are expected to help fix the build. That may mean rolling back code or making code changes.

# Standards

## Logging
Application should include logging for key events. Applications logs should include a traceable ID, date times, message, and other information that would be useful for troubleshooting or information gathering. Logs should contain context around the event rather than a message that stating some even occurred.

As much data as possible should be logged to provide context around the event, but any PII information should not be logged.
## Security
All Applications are expected to be secured applications. Applications must be continually scanned with security tools to check for vulnurabilities and security issues. Code should follow security standards and best practices.

## API Endpoints
API endpoints are considered public and should receive special care during their creation. API end points should follow RESTful patterns and be named intutitively and clearly expose resource concepts. Similar or duplicate resources should be discouraged. Reuse should be a major consideration in the endpoints name.

Digital Service Applications are considered to be part of shareable resources. It is often difficult to predict which resources will be of use for future clients. By providing generic interfaces to the application we can ensure any client can integrate with out applications. APIs should be generic, clear, documented, and easy to interact with. Endpoints should default to providing all data necessary to create and interact with resources rather than convience shortcuts. This would allow external clients to use the interface with out having to have special knowledge.

## Coding standards
Coding standards are conventions that improve readability by making code consistent. Teams are required to follow a coding standards that is compatible with other teams. Each language should define a working standards that all teams agree to. Code is expected to adhear to these standards. Code reviews are expected to enforce standards.  Coding standards include conventions for:
* Formatting
* Naming
* Whitespace
* Statements
* Idioms & Practices

Developers are responsible for ensuring they are following the appropriate coding standards, conventions, and idioms, which may differ per application. Developers are expected to follow the conventions used for the applications they are working in. Code reviews are expected to help enforce these requirements

Linting tools and IDE's plugins should be used to enforce rules.

## Testing
CWDS follows Agile testing practices. This includes Test Driven Development and Unit Testing. Code that runs against third party libraries or services is expected to contain integration tests. Acceptance and Functional tests tests applications externally and ensure application behaives as expected. All tests should be automated and ran from the build pipeline.

Other tests include smoke tests, performance tests, and any other specicial tests.

## Code Quality Tools
Code is requried to have static code analysis applied. Developers are responseible for overall code quality. Developers must ensure their code is not adding to the code quality issues. Developers must review the results of their analysis reports, even if the build did not break. Team members should be reviewing outstanding issues and should be trying to resolve all oustanding issues.

## Code Review
  Code Review/Pull Requests (PR's) should be a size that is easily reviewable. Code that is too large cannot be reviewed in a timely manner. The developer should not make changes once a request has been made. Requests should include appropriate documentation to describe what the request is doing.

  questions to ask:
    * Are they violating best practices or idioms?
    * Are there any security issues?
    * Could the code be refactored?
    * Is the code readable?
    * Are there tests?
    * Are things named appropriatly?
    * Are the right abstractions made?
    * Is code cohesive and losesly coupled?
    * Is the code cohesive?

## Feature Flags
Feature flags are used to guard blocks of code from being exectuted unintentionally. This may allow for some code to be rolled out to customers or to temporarily turn off code if it is not ready to be publically consumable. The developer is response to ensure his code is always ready for production. Code that is checked in but not ready to run should be guarded with a feature flag. Code should always be modularized to allow features flags to be inserted.

## Code
Developers are expected to follow coding standards. In addition to style guides and team agreements relating to code, developers should follow best practices, principles, and processes where appropriate. Developers should continuely refactor code to make it better.

The following compiled list of phrases describe what good code should be:
  * Elegant, efficient, and focused code.
  * Simple, direct, and straight forward.
  * Should be hard for bugs to hide.
  * Minimize dependencies.
  * Code should reveal developers intent not obscure it.
  * Readable by other developers regardless of skill level.
  * Consistent ways of doing things.
  * Follow exisiting patterns, else refactor.
  * Element of lease suprise.
  * Boy scout rule & broken windows.
  * Write it like you care. Craftsmenship.

### Basic Developer habits
The following are habits that developers should be adhearing to while developing code. The following habits help to raise the code quality by making the code more readable, understandable, simpler, and less error prone.
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
  * Comments don't make up for bad code. If you feel code should be documented, first ask if the code is well written and if it could be written clearer. Please document complicated or non-intuitive code. Please try to uncomplicate and make code intuitive. Comments should explain the intent of the code, not describe it.
  * Commented out code. Commented out code is not desirable. Please refrain from commenting that code out. Too often dead uncommented code is left in place and no one knows what to do with it and are afraid to remove it. If it is not being used, remove it. The repository will keep a record of it if it is needed at a later date.
  * Minimize the use of TODOs. Few people have the time to go back and fix the TODOs. They typically live on forever in the code. Make the code the way it is supposed to be the first time. and no one knows what to do with it and are afraid to remove it. If it is not being used, remove it. The repository will keep a record of it if it is needed at a later date.
  * Keep Browser Console clean. Ensure warning and errors are not being reported in the browser console. The console reports errors which should be handled and are unprofessional.

bugs and test
defensive programming
pii
failing builds
testing
code quality
pull requests
pair programming mentoring, pointout mistakes
code/peer review
estimating
refactoring and continous improvements
collective owner ship
Getting software to work is only half of the job. -- robert martin
team standards
Make it work. Make it right. Make it fast. Kent beck
