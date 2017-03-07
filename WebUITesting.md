# Web UI Testing

When it comes to testing in JavaScript, I would say that there are two types of tests: unit tests and end to end tests, which are also referred to as integration tests or functional tests depending on who you talk to and what articles you read.

For me, I have found unit testing to be beneficial and relatively straightforward for code that does not involve the DOM much. Unit testing allows you to test modules in isolation and is great for (but not limited to) testing things like data structures, data manipulation, validation, etc. 

But how do you test JavaScript that heavily depends on the DOM and user interactions? How do you test that the different modules of your application work together? This is where end to end testing comes in


* Mocha: A test framework. It runs our unit tests and reports back when it fails.
* Chai: An assertion library. I use it mainly for the syntactic sugar it provides for my tests (it makes my TDD code more expressive and readable)
* Sinon: Enables test spies, stubs and mocks so you can simulate events and the behaviour of third parties in your tests.
* Karma: A test runner. Run our client-side Javascript tests in a real browser from the command line. Useful if you want to check the DOM, for example.
* Istanbul: Code Coverage report generator. Tracks the percentage of your code covered by your Mocha tests.
* Codecov.io: Integrates your Istanbul code coverage into your workflow. Upload your reports to the cloud, visually include code coverage reports into Github pull requests, and award yourself with a spiffy badge, among other things.
* Browserify: Lets us use ‘require’ in the browser like you can in Node. Together with:
* Babelify: Uses the babel transpiler to turn our ES6/ES2015 code ES5 compatible. Write ES6 code in your front end and your tests without fear.
* ngMock – module for injecting and mocking angular services in AngularJS unit tests 
* Optional: yarn (for package installing and precise repository versioning)
* Optional: standard (for linting)


![1](http://jasonwatmore.com/_content/images/angular-unit-testing-2.png)
