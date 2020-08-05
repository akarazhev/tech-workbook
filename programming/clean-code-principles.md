# Clean Code Principles

## Universal principles to follow:
- Follow standard rules: experiments always end in disaster.
- Avoid duplication in the code (DRY principle or Don’t Repeat Yourself ).
- We must apply The Boy Scouts rule to our profession: Leave the campground cleaner than you found it.
- Follow SOLID principles to write clean classes and well-organized APIs.

## Names rules:
- Use names that can be pronounced well.
- Choose descriptive and clear names.
- Use searchable names.
- Make it easy to remember them.
- Use names according to the context.
- Use names that are consistent with each other. For example, it’s confusing to have “retrieved” and “get” as equivalent methods in distinct classes.
- Use the same language in the names of variables, functions: English, French, etc. In my case, I prefer to use English because it’s a standard.
- Avoid encodings and don’t append prefixes or type information.

## Comments:
- Comments are difficult to maintain and don’t tell the truth about the code, so try to avoid it. They are almost always out of date.
- The code is the best documentation.
- Don’t be redundant.
- Avoid unnecessary comments (most of all).
- Use only as a clarification of code.

## Functions rules:
- They should be short and only do one thing. If your function is doing more than “one thing,” it is a perfect moment to extract to another function.
- Avoid passing booleans. Why do you need to pass a Boolean? Do you need to do more than one thing within a function?
- Keep the number of arguments as low as possible.
- Avoid side effects. Declare the arguments as final(Java) if you can.
- Functions should either answer something or do something, but not both.
- Prefer Exceptions to return error codes and extract error handling try catch into their function.
- Don’t return a null value. What is null? It does not provide any information.

## Design rules:
- You should declare local variables as close as you can to their usage.
- You should declare instance variables at the top of the class.
- Constants should be declared at the top of the class or in a Constants class by example.
- Follow the Law of Demeter: A class should know only its direct dependencies.
- Coding is like writing; try to express the purpose of the programmer and the code.
- Use dependency injection (DIP).
- If you use third-party libraries, wrap them, so if they change, only your wrapper implementation needs to change.
- It is a good idea to separate concepts vertically.
- Place methods in a top-down direction.

## Formatting:
- Avoid too-long files.
- Good files have a heading, the critical stuff first, and details later.
- Although we now have big screens and with high resolution, avoid lines get too long (80 or 120 is perfect, in my case 100). You will get used to being more concise, and your code will be more readable.
- Be consistent with the rules of your team.

## Classes:
- Classes should be small.
- Classes should have only one responsibility and only one reason to change (SRP).
- Keep utility methods and variables private except some cases for doing testing.
- Use correctly package levels: public, protected, or package.

## Objects and Data Structures:
- Hide internal structure.
- If you can, call only your methods of your class, of objects you have created, and avoid call methods reachable through these objects (Law of Demeter).
- Improve the decoupling of objects.
- Variables should be private and manipulated by getters and setters, but remember, there is no necessity to add getters/setters to each variable to expose them as public.
- The base class should know nothing about their derivatives.
- Objects expose behavior and hide data. Conversely, data structures expose data and lacks of (significant) behavior.

## Exception handling:
- Throwing errors makes code cleaner than checking for status values throughout the code.
- Provide enough meaning to determine the cause and location of an error.
- Wrap third-party libraries APIs to remap their exceptions as required.

## Concurrency:
- Concurrency, although it may improve the performance of the program, is difficult, so use it wisely and only when required.
- Keep concurrency control separate from other code.
- Know basic concepts and basic programming models like mutual exclusion, starvation, or deadlocks.
- Create locked sections small.

## Tests:
- Fast: Unit tests should be fast and being executed in a short time.
- Independent: Tests should not depend on each other.
- Repeatable: Tests should be reproducible in any environment.
- One assert per test.
- If you have the code covered by tests, you will not be afraid to modify it and break it.
- TDD: Build your software using tests that guide your development.