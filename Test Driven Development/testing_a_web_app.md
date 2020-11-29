# Testing a web app

![testing stack for web apps](https://i.imgur.com/wibrtYC.png)

As we move from lower to higher levels, we implicitly rely on lower parts of MVC. For example, Integrations Tests will flex our controllers and our models.

## Testing MVC
Using the car analogy to explain why testing in different ways is necessary.
* Models are tires, engine, fuel tank that make a car useful.
* A view is like steering wheel that users can touch.
* A controller is like a steering column that connects the wheel to the tires. Users do not know about them. However, they are as necessary as models and views.

## Unit Tests
* These are run in isolation. 
* These test only a single unit of functionality. 
* It makes sense to test the tires of a car in isolation for testing its grip on road and resistance to punctures.
* These allow us to test edge cases in our application. ( Edge case means an unexpected behavior of our functionality. We make amends to overcome them )

## Feature | Acceptance | Integration tests
These are also called end-to-end tests. These implicitly test multiple pieces of our application. 
These are also called acceptance tests because these are directly connected to user interaction with our application.

Its important to test our views because these are at which users look at and interact with. But it does not make sense to test views in isolation. Views are useless if they are not connected to controllers and models. A lot of controller tests like 'checking if a template is rendered by action or not' are automatically handled by a feature test. We can remove redundant tests in a controller and implement those implicitly in a feature test.

For example, a car's wheel cannot be tested in isolation until its connected with the steering column that then transmits wheel movements to the tires.
Just like above example, a feature cannot be tested until its connected to all the pieces of the application. This is called an acceptance test because it is directly connected to user interaction with our application.

Feature tests are like interacting with our application as an end-user.
We have to think in terms of our users. 
How will a user interact with our application? 
This creates immense amount of expressiveness in our tests and also we are able to implicitly test multiple parts of our application.

**If the application is working from a user's perspective then that's all we need.**

We do not care about how our views look, we care about the functionality for example, I should be able to fill email and password and then press log in button and it should log me in.

* We should not make our feature tests strict otherwise it will be very difficult to modify our views.
* Prefer a test framework like Capybara that is built for acceptance testing over basic test frameworks.
* Features tests are great guidelines for learning how a feature is working in our app. It gives an holistic picture of a feature.

[Basic guide on testing a rails app](https://learn.co/tracks/full-stack-community-bootcamp/rails/validations-and-forms/rails-testing)
