# Testing Imperative Logic

In this exercise, we will focus on testing imperative logic and facing the challenges associated with such testing.

Imperative logic is generally very useful for us or else we would only have access to what's in memory and our programs would be pretty boring without being able to access things like disk, network, or databases.

The difficult aspect of maintaining this type of logic lies in the fact that we need to manage the external dependency in some way. Typically there are a few ways to accomplish end to end testing for imperative logic:

1. Allow your test to hit the **REAL** dependency (full integration)
2. Allow your test to hit a fake dependency (mock)
3. Prevent your test from making a call and give it a fake result (stub)

Each of these approaches has their own **advantages** and *disadvantages*:

| Method           | Effort to Setup Environment | Effort to Write Tests | Flakiness | Detects Errors When Dependencies Change |
| ---------------- | --------------------------- | --------------------- | --------- | --------------------------------------- |
| Full Integration | **Easy-Medium**             | *Medium-Hard*           | *High*      | **High**                                |
| Mocking          | *Medium*                      | **Easy-Medium**       | *Medium*    | **Medium**                              |
| Stubbing         | *Medium-Hard*                 | **Easy-Medium**       | **Low**   | *Low*                                     |

In our exercises below, we'll go over each of these methods so we can get a balanced sense of the advantages and drawbacks of each one.

## Needed Tools

1. Programming Language/Platform
2. Code Editor
3. Linter
4. Test Harness
5. Code Coverage Tool
6. Web Servers

## Setup

1. Ensure that `node >= 8.6` is installed
2. Run `npm install`
3. Run `npm test`, you should expect to see all tests passing and some code coverage
4. Run `npm run report` to see the coverage reports
5. Run `npm run test:watch` to have tests automatically rerun when changes are made

## Exercise

### Goals

Our goals in the following exercise are:

1. Learn how to reach 100% coverage on lines and branches for imperative and functional logic mixed together
2. Learn how to test using full integration
3. Learn how to test using mocks
4. Learn how to test using stubbing
5. Get hands on practice with a modern testing harness, tools, and techniques

### Steps

In order to achieve these goals, we will follow these steps:

1. Familiarize yourself with the coverage report by looking at the webpage generated by `npm run report`. You can simply refresh the web page after running your tests to see the updated coverage.
2. Familiarize yourself with the test watcher by running `npm run test:watch` and making a change to a file or typing `rs` in your terminal and watching the linter and tests be rerun.
3. Aim for 100% line and branch coverage of the logic in `src/request_integration.js` by adding tests to `tests/request_integration.test.js`. **YOU WILL NEED TO HAVE A LIVE INTERNET CONNECTION**.
4. Aim for 100% line and branch coverage of the logic in `src/request_integration.js` by using a mock server instead. There is a mock server provided for you in `tests/mocks/mock_server.js`. For the purposes of this exercise, start the mock server with `npm run mock-server` in another shell and change the urls in your test to point at `http://localhost:1234` instead.
5. Aim for 100% line and branch coverage of the logic in `src/request_stub.js` by adding tests to `tests/request_stub.test.js`

### Conclusion

Congratulations! You've just finished the testing exercise in which we focused on understanding the different ways that imperative logic can be tested. Imperative logic is very useful for us but is more difficult to manage than pure functional logic and especially when they're mixed together.
