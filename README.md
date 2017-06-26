# Sudokrew JavaScript Recommended Project Structure, Tooling, and Best Practices

* An ever evolving and changing best practices document for how we build JavaScript applications. Some of this is JavaScript, some is our engineering process agnostic of a particular stack or language.

* __DISCLAIMER__: This is what we determine over time works for us. We are a dev shop that work on many small to medium size projects at once with things that can change daily. If this wouldn't work for you that's cool, we're sorry. Contributions welcome.

## Table of Contents
1. [Documentation](#documentation)
1. [Project Tooling](#project-tooling)
1. [Debugging](#debugging)
1. [Committing Code](#committing-code)
1. [Team Communication](#team-communication)
1. [Code Reviews](#code-reviews)
1. [Writing Tests](#writing-tests)
1. [Front End Dev](#front-end-dev)
1. [Server Side Dev](#server-side-dev)
1. [Security](#security)
1. [Configuration](#configuration)
1. [Project Structure](#project-structure)
1. [Deployment](#deployment)
1. [Dev Environment](#dev-environment)
1. [Server Configuration](#server-configuration)
1. [Resources](#resources)

## Documentation

ESDoc extends JSDoc with support for ES6 syntax, gives document coverage(think code coverage for documentation) and generates nice HTML documentation in a navigable format.

## Project Tooling

### Linters

It's important to use a linter with reasonable configurations to catch common errors before running your code. We are basing our ESLint configurations off of Airbnb's linters which can be found [here](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb).

## Debugging

## Committing Code

## Team Communication

MVS (Minimum Viable Scrum) - Daily communication with internal team is critical. Meetings suck. And in the environment we work in, even harder they can be hard to schedule with everyone's schedule.

MVS can be defined as follows:
- Check in via chat in the morning on what you will be doing today
- Check in via chat at the end of the day on what you accomplished and any blockers.

I trust my engineers but I need to know we're all on the same page. Those working together closely on the same project should communicate often throughout the day but this is a touch point for those not deep in the project to determine that the project is moving on along as planned with minimal overhead. This can be a great time saver and still be effective.

## Code Reviews

## Writing Tests

It's important to write tests because it forces you to think critically about the code you are writing. Whether it's frontend or backend, there should be tests to support that the code being submitted is doing what it's supposed to do.

### Tools
We mainly use [Mocha](https://mochajs.org/) and [Chai](http://chaijs.com/) because of the flexibility that both provide. Both may be used for front-end and back-end tests.

If testing code that is supposed to run in the browser, use [Karma](http://karma-runner.github.io/) to run your Mocha tests. Karma reports results back to the cli, which is useful when integrating with continuous integration (CI) tools.

Remember to run test frequently. Don't wait 2 hours to find out the code you wrote broke half of tests. Always use a watch task that is paired to give continuous feedback as you are developing. Whether that's having a visible terminal open, [growl notifications](https://www.npmjs.com/package/gulp-notify) enabled, or [Wallaby](http://wallabyjs.com/), make sure you know when things are breaking the moment it happens.

## Front End Dev
Ensure CSS background images make use of preloading if necessary
```
<link rel="preload" as="image" href="some/image.png" >
```

## Server Side Dev

####Node.js

- __process.cwd()__ - Discourage use in standard Express or framework for resolving a file path.`__dirname` gives the current working directory of the file while `process.cwd` gives you the path of where the command to start the script was run from.

```
/home/jaywon $ node project/demo/app.js

//app.js
console.log(process.cwd()) // /home/jaywon
```

## Configuration

## Security

When adding scripts to a page use the `integrity` attribute of the `<script>` tag to generate a secure hash of the file that will not be executed by the browser if it doesn't match the downloaded files generated hash.

```javascript
<script src='https://mycdn.com/script.js' integrity='sha384xxxx...' />
```

## Project Structure

####Standard Express Project

__Compiled Assets(/public)__: If using gulp, sass, or any other tasks that generate move files to standard `public` folder, generated assets should be in source control. This is to reduce the depenency on deployment routines to be responsible for being a task runner as well and having to troubleshoot deployment targets.

## Deployment

## Dev Environment

## Server Configuration

## Resources

####Documentation
+ [ESDoc](https://esdoc.org/)
