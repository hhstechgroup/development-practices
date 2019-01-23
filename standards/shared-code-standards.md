This document identifies CWDS common (shared) code standards in an effort to help improve software quality by having a common standard across development teams. The project comprises of several vendors with different coding standards and philosophies which can cause confusion among teams that interact. A common standard helps set expectation among all team members.

The CWDS CARES project was initiated with a commitment to agile principles and practices with the expectation that teams will be committed to such practices. Shared libraries promotes code reuse which minimizes code duplication, increases development velocity, and benefits from multiple developers maintaining the code. A key agile practice is to minimize code duplication and developers are expected to follow such practices.

# Standards
CWDS expects developers to minimize code duplication through the use of shared libraries. Developers are expected to use and contribute to existing shared libraries, and to create them when they are needed but do not exist. Developers must contribute common code back to shared libraries.

Shared code is software that can be reused in various applications. Code may include small functions that are part of utility classes such as date formatters, larger frameworks that handle configuring an application such as Dropwizard, or a common library such as the UI Component Library. By reusing code we improve development velocity, minimize bugs, and keep application code base smaller as well as have common methods for performing tasks. Using existing code will improve development by providing already built and tested software components which will increase velocity and minimize bugs.

==rework sentences below:
Sharing code is a desired practice, but not all code is a good candidate for code sharing and some thought should be put into what should be shared. Some code may appear to be the same (same methods, properties, etc), but it is used in a different context and it can change for different reasons. If a piece of code can be used in different context, then it MAY be beneficial to have "duplicate" code. For example, a domain and entity class may have many of the same properties and methods, however, one class may have special domain knowledge that the entity wouldn't not have. The DB details may change which could cause the entity to change, however we may not want the business object to be forced into a change.

Shared code may need to be developed in a manner that allows for code reuse. Code should be abstract enough to be used across multiple projects and for multiple purposes. Although decomposing classes is always important, shared code may require code to be broken into further classes to allow for more flexibility. Dependencies should be configurable. Some modification will not be evident until some need is discovered. In these cases the new developer may need to alter the code to provide the necessary abstractions or components for configurations.

Code changes should be performed with care since the code is shared. Although users of shared code can benefit from an improved algorithm a fixed bug, changes can cause unintended side effects. Care must be taken to preserve the exposed contract. Developers need to account for how their changes will impact other users.

Examples:
DTOs, DAOs, Helpers like date time, messengers, UI components, integration layer, etc.

All code should contain tests. Shared code should include tests that verify functionality. The implementing code may choose to add additional tests or to mock out the shared code. Shared code test should not only test functionality, but should also demonstrate code usage. Tests are great for showing examples of using the code.
