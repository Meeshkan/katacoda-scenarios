Let's mosy over to `getUsersForUI1.test.js` and see a slightly more advanced version of the previous tests. We use the same general API with three important changes.

## Fluent specification

Instead of defining just one possible response code, we can define several. This allows us with minimal effort to reproduce how an API will actually behave. For example, it is rare that an API never throws an error, and you almost always will want to test how your code handles error responses.

In order to define multiple responses, simply continue adding to `unmock.nock`.

## Fuzz testing

Fuzzy wuzzy wuz a bear, and fuzz testing is when you do the same thing multiple times with slight variations. Unmock's `runner` will take care of that for you - it runs your test several times with slightly different results depending on how you initialize the state.  Which leads us to...

## Initializing mocks

Mocks can be initialized with the `state` function that takes various useful transformations. Here, `withCodes` specifies the code to return, and `minItems` makes sure there is at least one item in our array so that our test is testing the right thing!

To see that in action, let's run `npm test getUsersForUI2.test.js`{{execute}}.