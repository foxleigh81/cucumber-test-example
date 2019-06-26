# Cucumber Example

[![CircleCI](https://circleci.com/gh/foxleigh81/cucumber-test-example.svg?style=svg)](https://circleci.com/gh/foxleigh81/cucumber-test-example)

Hi. Here are my tests for the cucumber test. I notice by question 4 that you are using `cucumber-boilerplate` but I've actually got no experience in using that so I went with my usual implementation of Cucumber + NightwatchJS. I hope that's ok. The boilerplate looks good though and I'll be having a look at it for my future projects :)

# How to run these tests within the repo 

As there was no runnable code or a link to run tests on, I created a really basic HTML/Boilerplate/jQuery page so I could see the tests working. It's nothing fancy so please don't judge me on the quality of that code :) The repo includes `http-server` so the page can be run in a server.

You can run the server and tests by following the steps below.

``` bash
npm install
npm run start-all
```

Or if you would prefer to run the server and tests seperately, you can run `npm start` and `npm test` in different sessions.

To save you time, I've also set up a circleci build that you can look at the results of. If you click on the badge above or [click here](https://circleci.com/gh/foxleigh81/cucumber-test-example) you can see the results of that build.

## Answer to question 4

- The `import` contains `Given`, `When`, `Then`, `And` and `But` but the steps themselves only use `Given`, `When`, `Then` and `And`. `But` can be removed from the import.

- xpath is used everywhere but CSS selectors would be easier to read and quicker to run, the only valid use-cases I see for xpath are the two steps at the end as it looks like they are looking for elements with specific text content.

- If xpath is required then you can use a much less verbose selector by starting later down the chain with `//`

- The nesting is crazy but I am not sure if that's a sneaky part of the test of if the PDF has just messed up the formatting.

- The second test seems to be clicking an element and then waiting for that same element to be visible. Either there is some weird stuff going on or the first selector is wrong.

- The third test checks for the existance of `vmd-justication-card` but we already know it's there as the 2nd test checks for it.

- Some of the tests target classes, this isn't a good idea as classes are really for CSS. Either add specific classes just for testing or ideally, add data attributes.

- There may be more but I think I might need to be more familiar with the predefined steps from cucumber-boilerplate
