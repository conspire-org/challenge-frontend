Front End Code Exercise
=======================

For this code exercise, you'll build the front end for a RESTful web service. The web service endpoints are already mocked for your use, so you'll write only client code.

## Languages and Frameworks

Your code should be written in HTML, CSS and JavaScript. (You're also welcome to use HAML, Sass/Less and/or CoffeeScript if familiar.) You should use the [Backbone.js](http://backbonejs.org/) framework to represent models and collections. Use of a templating framework is encouraged for dynamically generating DOM elements.

You should write unit tests for your solution using [Jasmine](http://jasmine.github.io/2.0/introduction.html) or another JavaScript unit testing framework.

## Endpoints

Your application will interact with a mock server via two REST API endpoints on [Apiary.io](http://docs.conspirechallenge.apiary.io/). These are:

  1. ```GET http://private-efa4b-conspirechallenge.apiary-mock.com/profiles``` returns a JSON array of "profile" objects. See the [documentation](http://docs.conspirechallenge.apiary.io/#get-%2Fprofiles) for sample response JSON.
  1. ```PUT http://private-efa4b-conspirechallenge.apiary-mock.com/profiles/{id}``` accepts a single profile object in the request body, _not including the ```id``` property, which goes in the URL_. See the [documentation](http://docs.conspirechallenge.apiary.io/#put-%2Fprofiles%2F%7Bid%7D) for sample request JSON.

When formulating your ```PUT``` request, note that the mock endpoint will return ```200``` regardless of whether the request contains valid JSON. Be sure to use the [traffic inspector](http://docs.conspirechallenge.apiary.io/traffic/efa4b) to confirm your request JSON is properly formatted.

## User Interface

Your task is to build an interface that presents the data returned by the ```GET``` endpoint above. The following user actions must be supported:

  1. **View the full list of profiles** returned by the ```GET``` endpoint, with at least the ```name``` field visible in the list view. Profiles themselves need not be sorted or reorder-able, and a user need not be able to add or remove profiles.
  1. **View details for an individual profile**, including ```image``` and all other fields. The ```affiliations``` list should be sorted in descending order of elements' ```end_year```, regardless of the order in which they are returned by the ```GET``` endpoint. Affiliations with a ```null``` ```end_year``` should be treated as current and placed at the beginning of the list, sorted in descending order of their ```start_year```, which may not be ```null```.
  1. **Edit a profile.** All fields of the profile, _with the exception of the ```image``` field_, and all fields of each affiliation should be editable. _Note that affiliations should be re-sorted when any affiliation's ```end_year``` changes._ It should be possible to add and remove affiliations. Changes to a profile should be saved via the ```PUT``` endpoint.

The layout and styling of the interface are completely up to you. Elements of functionality not addressed above (for example, exactly when profile changes are saved to the server) are also for you to define. This exercise is partly to test your UX sensibility, as well as your ability to code pixel-perfect UI, so be creative and choose whatever approach results in the best user experience.

## Guidelines

You can and should use any open-source libraries applicable to the task. Feel free to search the web, read online documentation, etc. the way you would if this were a real project.

Please don't hesitate to ask us any questions you might have about the requirements, technical issues, or anything else. One purpose of this exercise is to get a feel for what it would be like to work together, so don't be afraid to engage us at any time.

## Submission

Please push your submission, including unit tests and any [Grunt](http://gruntjs.com/) or other build file(s), to a public GitHub repository and let us when that it's ready to review. We appreciate your time and energy completing the coding exercise and will review your solution as quickly as possible.
