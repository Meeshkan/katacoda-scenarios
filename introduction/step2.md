Please click on the file `getUsersForUI1.test.js`. In it, you'll see a simple mocked service. The syntax is very similar to that of [`nock`](https://github.com/nock/nock) with one notable exception: it is possible to define dynamic return values using the `u.<command>` syntax. For example, instead of hardcoding a name, we use `u.string()` to return an arbitrary string.

The advantage of using arbitrary values is twofold:

1. It forces test writers to focus on the structure of an API response rather than its content. Unless you are sure of the content an API will return, it is usually better to focus on the structure.
1. It allows you to do fuzz testing of APIs, as we will explore in the next section.

If you haven't run `npm install`{{execute}} yet, please do! Now, we can run `npm test getUsersForUI1.test.js`{{execute}} to see our tests pass with flying colors.
