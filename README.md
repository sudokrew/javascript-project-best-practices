# Sudokrew JavaScript Recommended Project Structure, Tooling, and Best Practices

* An ever evolving and changing best practices document for how we build JavaScript applications. Some of this is JavaScript, some is our engineering process agnostic of a particular stack or language.

* __DISCLAIMER__: This is what we determine over time works for us. We are a dev shop that work on many small to medium size projects at once with things that can change daily. If this wouldn't work for you that's cool, we're sorry. Contributions welcome.

## Table of Contents
1. [Documentation](#documentation)
2. [Project Tooling](#project-tooling)
3. [Debugging](#debugging)
4. [Committing Code](#committing-code)
5. [Team Communication](#team-communication)
6. [Code Reviews](#code-reviews)
7. [Writing Tests](#writing-tests)
8. [Front End Dev](#front-end-dev)
9. [Server Side Dev](#server-side-dev)
10. [Configuration](#configuration)
11. [Project Structure](#project-structure)
12. [Deployment](#deployment)
13. [Dev Environment](#dev-environment)
14. [Server Configuration](#server-configuration)
15. [Resources](#resources)

## Documentation

ESDoc extends JSDoc with support for ES6 syntax, gives document coverage(think code coverage for documentation) and generates nice HTML documentation in a navigable format. 

## Project Tooling

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

## Front End Dev

## Server Side Dev

####Node.js

- __process.cwd()__ - Discourage use in standard Express or framework for resolving a file path.`__dirname` gives the current working directory of the file while `process.cwd` gives you the path of where the command to start the script was run from.

```
/home/jaywon $ node project/demo/app.js

//app.js
console.log(process.cwd()) // /home/jaywon
```

## Configuration

## Project Structure

####Standard Express Project

__Compiled Assets(/public)__: If using gulp, sass, or any other tasks that generate move files to standard `public` folder, generated assets should be in source control. This is to reduce the depenency on deployment routines to be responsible for being a task runner as well and having to troubleshoot deployment targets.

## Deployment

## Dev Environment

## Server Configuration

## Resources

####Documentation
+ [ESDoc](https://esdoc.org/)
