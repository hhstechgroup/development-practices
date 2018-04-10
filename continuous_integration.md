# Continuous Integration Strategy

All projects in CWDS follow the same Continuous Integration process:

                                                                    +--------------+
                                                                    |              |
                                                                    | Deploy to    |
                                                      +-----------> | Integration  |
                                                      |             |              |
                                                      |             +--------------+
  +------------+          +------------+       +-------------+
  |            |          |            |       |             |      +--------------+
  | Container  |          | Deploy to  |       | PRE-Int     |      | Deploy to    |
  |   Build    +--------> |  PRE-Int   +-----> | Smoke Tests +----> | Preview      |
  |            |          |            |       |             |      |              |
  +------------+          +------------+       +-------------+      +--------------+
                                                      |
                                                      |             +--------------+
                                                      |             | Deploy to    |
                                                      +---------->  | Staging      |
                                                                    |              |
                                                                    +--------------+

1- Build Docker container
2- Deploy to PRE-INT
3- Run smoke tests against PRE-INT
4- Deploy to INT / Preview / Staging

## Build Docker container

The initial stage is triggered when the code is merged into `master`.
After that, the following steps happens on Jenkins:

1- Unit Tests are executed
2- A "Bubble" is spun up to recreate all the dependencies of the current application being built. Acceptance tests are executed against the target app.
3- The Docker container is pushed to the registry

## Deploy to PRE-INT

Upon a succesful run of tests and after the container is built-- a deploy to PRE-INT is triggered automatically.

## Smoke tests against PRE-INT

A set of smoke tests (that do not rely on data) are executed against PRE-INT to validate the next step.

## Deploy to Integration / Preview / Staging

After the successful set of smoke test finishes, the container is deployed to Integration / Preview and Staging


