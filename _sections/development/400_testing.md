---
title: Testing
---

We write code to test our code. It sounds like double-work but saves a ton of time. We know instantly when something breaks.

### Key Concepts
* _Types of testing:_ [There are many different ways to test software](https://en.wikipedia.org/wiki/Software_testing), but developers typically mean unit tests.  These tests focus on a single function or class.  When many classes or functions are tested together, this is known as integration testing.  Another popular type of testing is behavior testing, which tests the application as a whole and can use special tooling to help automate these tests.
* _Test coverage:_ Even a simple function will have if statements, so multiple tests will be needed to make sure all code paths in a function are exercised.  Test coverage is used to show how much of the code is being tested and which parts are not covered.
* _Testing provides early warnings:_  Sometimes changes in one part of the application will accidently break other parts.  With tests, these side effects are surfaced immediately and can be addressed in the same pull request.  Without tests, the bugs are passed along and will be found at a much later time which can be costly and time consuming.
* _Testing improves Maintainability:_ Write tests not so much for yourself, but for the dozens of other developers that will read and maintain your code over many years.  Oftentimes, a test acts as a secondary means of communicating the purpose of a block of code.  If the maintainer cannot understand the original code, the tests exercising it may provide additional insight.

### The STSI Way
* _Coverage:_ We believe that your code should have tests that cover at least 80% of your code base, with special attention given to key functions or modules.
* _Passing Tests:_ We believe that code is not ready for review until all the tests are passing
* _Testing as a start:_ A great way to familiarize yourself with an existing project is to run the tests and add missing coverage.  This will give you experience building, running and understanding the code while contributing to the overall health of the project.
