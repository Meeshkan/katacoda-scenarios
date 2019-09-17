We see that, in `getUIUsers.test.js`, we define a mocked service. The syntax is very similar to that of [`nock`](https://github.com/nock/nock) with one notable exception: it is possible to define dynamic return values using the `u.<command>` syntax. For example, instead of hardcoding a name, we use `u.string()` to return an arbitrary string.

The advantage of using arbitrary values is twofold:

1. It forces test writers to focus on the structure of an API response rather than its content. Unless you are sure of the content an API will return, it is usually better to focus on the structure.
1. It allows you to do fuzz testing of APIs, as we will explore in the next section.

For now, we can run `npm test`{{npm test}} to see our tests pass with flying colors!