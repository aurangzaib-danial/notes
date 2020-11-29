# Benefits of Testing
- Confidence against errors while refactoring
- Document code
- Feedback loop
- Make sure your code is producing result according to our expectation. Deal with edge cases.
- Confidence while making a change

## Confidence while refactoring code
If we do not have a test suite for a code that we want to refactor, we will never feel at ease while doing refactoring. If we have a suite, we can make a change with confidence and our tests will let us know if we break something.

## Confidence while making a change
Even if we have object oriented design and MVC, we cannot be 100% that the change that we just made is going to affect some other part of program which it should not. This is why writing units for all of our code, helps us in quickly testing the code that we think got effected by the change. This way we quickly remove doubts, worries and suspicions.

## Documents code
As we write tests for components in our application, they also act as documentation that explains how a feature or component work.
This is something that I really love about tests. As I am writing tests, I'm full documentating my code. This helps me and others to quickly onboard my application by reading the tests.

## Feedback loop
Programmers of scripting languages enjoy a quick feedback loop because they can immediately run their code instead of waiting for code to compile.

Feedback loop is a behavior in humans that gives us positive signal of progress on each step.
These feed backs help us to stay motivated and know that we are making progress.

Frameworks like Rails help us save precious time between steps in a feedback loop. 
But it can be daunting to know if the functionality that we are building is actually working or not.

**This is the very reason for which testing frameworks exists. To help you make sure that your code is working exactly as you want it to. It is very difficult to test a feature from front to back end completely and manually testing is extremely error prone.**

Testing frameworks help us in keeping our feedback loops short and intuitive.

## Make sure that our code is producing the right result
Often times our code will produce different results on different inputs. It can be very difficult to test all of those edge cases by hand. Writing tests allows us to keep track of all edge cases and make changes with confidence.
