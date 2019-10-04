Sometimes, it is useful to know exactly what went into or came out of an API.  While it may be tempting to hardcode API responses to API requests, please don't! Use our spies instead :-)

That's right, spies. Not like Boris and Natasha, but rather [`sinon`](https://www.sinon.org) spies. Unmock ships with `sinon` spies that let you make powerful assertions about how your API should behave.

## Spy vs Spy

Let's check out `3.test.js`. We want to make sure that the response includes the *complete* response from the server *and* a `timestamp` and a `newlyFetched` field.

To do this, we'll use `example.spy.getResponseBody()`. See it in action by running `npm test getUsersForUI3.test.js`{{execute}}.

`getResponseBody` has cousins like `postResponseBody`, `postRequestHeaders` and basically anything you'll need to write some amazing assertions.