# Web UI Testing

* [Front-End Testing: Demystified](https://www.slideshare.net/sethmcl/testing-web-apps-33612391)

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
* proxyquire - Proxies nodejs require in order to allow overriding dependencies during testing.
* Optional: yarn (for package installing and precise repository versioning)
* Optional: standard (for linting)

In generall test frameworks are expected to:
* provide test structure (Mocha, Jasmine, Jest)
* run tests and display test results (Mocha, Jasmine, Jest, Karma)
* make assertions (Chai, Jasmine)
* support mocks, spies, stubs (Sinon.JS, Jasmine)
* generate code coverage reports (Istanbul)

## UI Testing Basic
* [JavaScript Testing: Unit vs Functional vs Integration Tests](https://www.sitepoint.com/javascript-testing-unit-functional-integration/)
* [An Introduction To Unit Testing In AngularJS Applications](https://www.smashingmagazine.com/2014/10/introduction-to-unit-testing-in-angularjs/)
* [The Let’s Code JavaScript Tool & Module Recommendations](http://www.letscodejavascript.com/v3/blog/2014/03/dependency_recommendations)


* [Unit Test Your JavaScript Using Mocha and Chai](https://www.sitepoint.com/unit-test-javascript-mocha-chai/)
* [Creating a Fully Tested Web App](http://www.overfitted.com/blog/?p=338)
* [Client-side testing with Mocha and Karma](https://sean.is/writing/client-side-testing-with-mocha-and-karma/)
* [Setting up a project using karma with mocha and chai](http://attackofzach.com/setting-up-a-project-using-karma-with-mocha-and-chai/)
* [Testing in Browsers and Node with Mocha, Chai, Sinon, and Testem](http://knpw.rs/blog/testing-in-browsers-and-node)
* [A Karma, Mocha, Gulp and Browserify Workflow](http://www.roblayton.com/2015/03/a-karma-mocha-gulp-and-browserify.html)
* [How to setup testing using Typescript, Mocha, Chai, Sinon, Karma and Webpack](https://templecoding.com/blog/2016/02/02/how-to-setup-testing-using-typescript-mocha-chai-sinon-karma-and-webpack/)
* [Testing with Webpack 2,inject-loader, karma,mocha, chai and sinon](https://cafedev.org/article/2016/12/testing-with-wepack-2-inject-loader-karma-mocha-chai-and-sinon/)
* [Mocks, Stubs, and Injections: Unit Testing in Angular.JS](https://www.martin-brennan.com/mocks-stubs-and-injections-unit-testing-in-angular-js/)
* [How to set up Mocha + Chai + Sinon + Karma + Browserify +Istanbul + Codecov](https://jaredtong.com/2016/01/08/how-to-set-up-mocha-chai-sinon-karma-browserify-istanbul-codecov/)

Protractor for Angular apps?
https://essenceoftesting.blogspot.sg/2016/03/protractor-for-angular-apps.html


## Mocha 
* [Mocha Feature](http://ricostacruz.com/mocha/)

## Sinon 
* [Sinon Tutorial: JavaScript Testing with Mocks, Spies & Stubs](https://www.sitepoint.com/sinon-tutorial-javascript-testing-mocks-spies-stubs/)


## Github
* [Karma + Mocha + Sinon + Chai = ❤](https://github.com/kmees/karma-sinon-chai)
* [karma-mocha-chai-sinon](https://www.npmjs.com/package/karma-mocha-chai-sinon)
* [JavaScript Testing utilities for React](https://github.com/airbnb/enzyme)


## Mocha Vs Jasmine
![1](https://image.slidesharecdn.com/unit-testing-140920200733-phpapp02/95/unit-testing-front-end-javascript-7-638.jpg)

## NPM Packages
![1](https://msdnshared.blob.core.windows.net/media/2016/12/image_thumb251.png)

## TypeScript Configuration File
![1](https://msdnshared.blob.core.windows.net/media/2016/12/image_thumb252.png)

## Karma Configuration File
![1](https://msdnshared.blob.core.windows.net/media/2016/12/image_thumb253.png)


![1](https://msdnshared.blob.core.windows.net/media/2016/12/image_thumb254.png)

# Gulp Configuration File
![1](https://msdnshared.blob.core.windows.net/media/2016/12/image_thumb255.png)

## Code and Unit Tests
![1](https://msdnshared.blob.core.windows.net/media/2016/12/image_thumb256.png)
![1](https://msdnshared.blob.core.windows.net/media/2016/12/image_thumb257.png)

![1](http://jasonwatmore.com/_content/images/angular-unit-testing-2.png)

