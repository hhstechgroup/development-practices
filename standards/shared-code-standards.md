This document identifies CWDS common (shared) code standards in an effort to help improve software quality by having a common standard across development teams. The project comprises of several vendors with different coding standards and philosophies which can cause confusion among teams that interact. A common standard helps set expectation among all team members.

The CWDS CARES project was initiated with a commitment to agile principles and practices with the expectation that team members will be committed to such practices. Shared libraries promotes code reuse which minimizes code duplication, standardizes coding implementations, increases development velocity, and benefits from using stable and mature existing code. A key agile practice is to minimize code duplication and developers are expected to follow such practices.

# Standards
CWDS expects developers to minimize code duplication through the use of common code aggregated into  shared libraries. Developers are expected to use and contribute to existing shared libraries, and to create them when they are needed but do not exist. Developers must contribute common code back to shared libraries.

p
Shared components exist in all development domains; Java, Javascript, UI components, CSS, etc. Examples of shareable code includes but is not limited to:
DTOs, DAOs, Helpers such as date & time, messengers, UI components, integration layer, etc.

# Shared Code
Shared code is software that can be reused in various applications. Code may only be a  small functions that are part of utility classes such as date formatters or a larger frameworks that handles configuring of an application such as DropWizard, or a common library such as the UI Component Library. By reusing code we improve development velocity, minimize bugs, and keep application code base smaller as well as have common implementation pattern for performing tasks. Not using libraries will slow down teams since they will have to create the code themselves, which may introduce bugs, and may be implemented in a different manner than the rest of the project, which complicates the understanding between one project and the next.

## Development Concerns
Although sharing code is a desired practice, not all code is a good candidate for code sharing. Some thought needs to be put into what is shared. Some code may appear to be the same (same methods, properties, etc), but the context may be different. If the context is different, the code can change for different reasons. If a piece of code changes for different reasons, then it MAY be beneficial to have "duplicate" code. For example, a domain and entity class may have many of the same properties and methods, however, one class may have special domain knowledge that the entity wouldn't not have. The DB details may change which could cause the entity to change, however we may not want the business object to be forced into a change. Both objects appear the same, but they have different context which can change independently.  Using good design principles will usually mitigate duplication issues.

Shared code needs to be developed in a manner that allows for code reuse. Code should be abstract enough to be used across multiple projects and for multiple purposes. Although decomposing classes is always important, shared code may require code to be broken into further classes to allow for more flexibility. Dependencies should be configurable. Some modification will not be evident until some need is discovered. In these cases the new developer may need to alter the code to provide the necessary abstractions or components for configurations.

## Code Changes
Code changes should be performed with care since the code is shared. Shared code should derive from a contract which clients expect to be stable (i.e. not changing). Users of shared code benefit from improved algorithms or fixed bug. But changes can inadvertently cause unintended side effects which may break client code..Care must be taken to preserve the exposed contract and should be part of the tests. Developers need to account for how their changes will impact other users.

Contracts should not change once code is available to the clients. Only algorithm improvements, refactoring, or side effects NOT visible to the client such as logging  should be performed. In the cases where there is a problem with the contract, then great care should be taken to handle the situation. Preferably, the code should be deprecated and replaced. In the event a breaking change is made, then the clients must be notified.

# Testing

All code should contain tests. Shared code should include tests that verify functionality and enforce the contract. Updates should not break existing contract tests since that would break clients. The implementing code may choose to add additional tests or to mock out the shared code. Shared code test should not only test functionality, but should also demonstrate code usage. Tests are great for showing examples of using the code.
