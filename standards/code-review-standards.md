This document identifies CWDS code review standards and expectations in an effort to help improve software quality by having a common practices across development teams. The project comprises of several vendors with different coding standards and philosophies which can cause confusion among teams that interact. A common set of standard helps set expectation among all team members.

The CWDS CARES project was initiated with a commitment to agile principles and practices with the expectation that team members will be committed to such practices. Properly performed code reviews identifies bugs, encourages collaboration, and promotes the adoption of best practices and coding standards. Reviews provide a platform for learning and discovering new techniques and to establish a common coding culture.

# Standards
CWDS has adopted the practice of code reviews as an effort to increase code quality. Code is expected to be reviewed by other developers. Code reviews are aimed at identifying bugs, coding standard issues, potential structure issues, and other coding issues. Developers are expected to work together to improve the quality of code and to fix identified issues.

# Code Review as a tool
At best Code reviews helps to share knowledge between individuals by being a mechanism for teaching and learning new stuff as well as sharing new code with other developers. It also helps to propagate standards and conventions and develops a coding culture.

At worst Code reviews can be used as a intimidation tool which will kill moral.

Mandated by the review process take time and kill excitement

Strict process can stifle productivity, but lax process means no one knows whether reviews are effective or even happening. And the social ramifications of personal critique can ruin morale.

# Reviewing Code
Code reviews should be positive. Code reviews should never be used to embarrass or to criticize another developers skills. It is a tool to help increase coding standards and to help educate and distribute knowledge between team members. Reviewers should never pass code they have not actually reviewed or code they do not understand.

Reviews should contain feedback that is clear and concise. Reviews should explain what the issue or concern is. Providing examples and links to further reading material is encouraged.

Limit reviews to less than 400-500 lines of code or to less than an hour max. Reviewing code takes time and focus. Studies have shown effectiveness starts to drop around 400 lines of code or over an  hour of code review. Developers should be encouraged to commit early and often thus reducing the size of code needing review. If a large code review is unavoidable, then multiple reviewers should review and reviewers should focus on key areas and spot checks.

Don't just run through the motions. If it looks good, try and give some advice.

# Disputes
Developing code requires the user to think through problems and create solutions which are highly subjective. A difference in opinion is common and often has no right or wrong solution, but may depend on viewing code from a certain perspective or with some context in mind. Disputes will arise when code is subjective. Developers are responsible to work together to resolve issues that arise. Disputes can be resolved by engaging other developers to provide feedback. Often code changes can be negotiated. The code is not expected to be perfect, but should be robust, communicative, and efficient.

Developers should not use code reviews to hold code hostage, meaning they should not prevent the passing review for dogmatic reasons that are not reasonable. Legitimate bugs, security and coding standard violations and conventions should be fixed, as should code that is too complex or difficult to understand the intent.

Different people have different ideas on how to solve a problem. Programming can be subjective and differences in opinion can occur. Be careful when criticizing or recommending changes that are subjective. Although these are great for advice, expecting these sorts of changes to be implemented may lead to confusion or even contention.

# Check Lists
Developers are encouraged to use checklists. Check lists make it easier to ensure reviews are standardized and key areas are covered. Some areas of concern for code reviews include:

* Bugs. Identify actual and potential bugs in algorithm.
* Unforeseen context. A second set of eyes can often spot edge cases and perhaps other unforeseen situations.
* Security issues. Includes any potential unauthorized access
* Logging. Ensure logging isn't too verbose or useless, contains enough context, and is sensitive to PII.
* Correct abstraction. Ensure code is at the corrects level of abstraction. The same code that writes to the DB shouldn't be doing validation. Components should be broken into appropriate classes or equivalent structures.
* Code Cohesion. Code should be cohesive. Related code should be contained together and unrelated code should be abstracted out.
* OO Principles. OO languages should be using objects and not be coding procedurally.
* Too large classes, methods, functions, etc. Code blocks should be small and focused. Doing too much is often a sign code is not cohesive and abstract enough.
* Doing too much. Classes that do to much is a code smell. Code should be broken into smaller classes.
* Best Practices. Code that violates best practices should be flagged.
* Coding Standards. Code that violates coding standards should be flagged.
* Efficient code. Code should be efficient. Efficient code is often simpler and less buggy. However, overly optimizing should be discouraged from code review in most cases..
* Elegant. Code should be simple and straight forward. Extraneous and convoluted code should be cleared up.
* Naming conventions. Code should use clear and concise naming conventions that are inline with coding conventions and application concepts. Names should not allow interpretations or be confusing to team members.
* Code should follow existing patterns and conventions used in the code base to be consistent.

# Tips
* When in doubt, talk to another developer
* Perform reviews in person. Especially when there are many issues or larger areas of concern.
* Try to learn something from the code.
* Try to teach something.
* Leverage code review or static analysis tools such as SonarQube, CodeClimate, linters, etc
* Run the code
* Review and run Tests
* Modify tests to see if they break.
* Are tests good tests?

## Reviewing by skill level
* Jr Reviewing Sr
  - Don't be intimidated. Excellent opportunity to learn something.
  - Keep Sr honest and ensure they are following the basics.
  - Don't be afraid to point out mistakes.
* Sr reviewing Jr
  - Be careful to not crush Jr's soul.
  - Be constructive.
  - Focus on major issues rather than a lot of the little trivial issues.
  - Use it as a teaching moment.
  - Provide clear explanations about why.
* Jr reviewing Jr
  - Stick to basics and perhaps new ideas and thoughts you have learned or came across.
  - Use your intuition. If something doesn't feel or look right, call it out as a potential issue.
  - If you have questions, ask some one with more experience what they think.
  - Don't let something go just cause you can't identify why it is a problem.
* Sr reviewing Sr
  - Challenge the Sr to be better.
  - Ensure they aren't skipping the basics.
  - NAMING. Ensure their naming and concepts are consistent with the app and not overly complex.

# Resources
https://www.ibm.com/developerworks/rational/library/11-proven-practices-for-peer-review/index.html
https://blog.digitalocean.com/how-to-conduct-effective-code-reviews/
https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/
http://www.bettercode.reviews/
https://en.wikipedia.org/wiki/Code_review
