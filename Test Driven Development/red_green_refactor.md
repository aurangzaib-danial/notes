# Red Green Refactor

We use TDD (test-driven development) for a reason. We write tests to define the desired behavior of our program so that we can write clean, beautiful code. Such code usually isn't the code you write the first time around. The code you first write is the code that makes your program work, the code that gets those tests passing. Then, we refactor our code to make it clean, DRY, and easy to understand. This is where our tests come in. We write thorough tests that cover all of the aspects of our code's desired behavior. We can first write code that passes those tests and then break our code, fail our tests, write better code and pass our tests again.

This is called the red, green, refactor pattern. First tests fail, then you write bad code to get them to pass, then you refactor that bad code into good code. Remember, don't be afraid of broken code! Broken code is the status quo in programming. Your job is often to break something to make it better. Embrace broken code.

**Red, green, refactor** is the way to go. After you have your expectations set in spec files, now you just have to implement the solution of a problem with the first way that comes to your mind and then just pass those tests. After your tests are passing, you want to go back and refactor your code. This will break your tests but just  pass them again. Keep repeating this cycle until you are satisfied with your implementation of the solution of the problem. 

**Red, green, refactor** makes you write multiple drafts of your code. This is just like writers who write their first draft to have something to work with and then continuously go over it for further improvements until they are satisfied.
