# Ex_Files_Csharp_TestDriven

Meszaros uses the term Test Double as the generic term for any kind of pretend object used in place of a real object for testing purposes. The name comes from the notion of a Stunt Double in movies. (One of his aims was to avoid using any name that was already widely used.) Meszaros then defined four particular kinds of double:

- Dummy objects are passed around but never actually used. Usually they are just used to fill parameter lists.

- Fake objects actually have working implementations, but usually take some shortcut which makes them not suitable for production (an in memory database is a good example).

- Stubs provide canned answers to calls made during the test, usually not responding at all to anything outside what's programmed in for the test.

- Spies are stubs that also record some information based on how they were called. One form of this might be an email service that records how many messages it was sent.

- Mocks are what we are talking about here: objects pre-programmed with expectations which form a specification of the calls they are expected to receive.

https://martinfowler.com/articles/mocksArentStubs.html

Style
Mocks vs Stubs = Behavioral testing vs State testing

Principle
According to the principle of Test only one thing per test, there may be several stubs in one test, but generally there is only one mock.

Lifecycle
Test lifecycle with stubs:

Setup - Prepare object that is being tested and its stubs collaborators.
Exercise - Test the functionality.
Verify state - Use asserts to check object's state.
Teardown - Clean up resources.
Test lifecycle with mocks:

Setup data - Prepare object that is being tested.
Setup expectations - Prepare expectations in mock that is being used by primary object.
Exercise - Test the functionality.
Verify expectations - Verify that correct methods has been invoked in mock.
Verify state - Use asserts to check object's state.
Teardown - Clean up resources.
Summary
Both mocks and stubs testing give an answer for the question: What is the result?

Testing with mocks are also interested in: How the result has been achieved?

https://stackoverflow.com/questions/3459287/whats-the-difference-between-a-mock-stub