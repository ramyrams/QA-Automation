# Karate

* [Karate](https://github.com/intuit/karate) - Web-Services Testing Made Simple - Opensource Github

# Peter's Hello World Example
Feature: karate 'hello world' example
Scenario: create and retrieve a cat

Given url 'http://myhost.com/v1/cats'
And request { name: 'Billie' }
When method post
Then status 201
And match response == { id: '#notnull', name: 'Billie' }

Given path response.id
When method get
Then status 200


Over ten demos are on the Karate Demo Page: https://github.com/intuit/karate/tree/master/karate-demo
