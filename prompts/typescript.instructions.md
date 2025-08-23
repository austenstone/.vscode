---
applyTo: "**/*.ts,**/*.tsx,**/*.js,**/*.jsx"
---
# Project coding standards for TypeScript

## General Guidelines
- Use modern Typescript and JavaScript features to write clean, concise, and readable code.
- Prefer immutable data structures and functional programming concepts.

## Asynchronous Code
- Use `async/await` to handle promises and avoid nested `.then()` chains for better readability.
- Use `Promise.all` when you need to run multiple promises concurrently.

## Console Logging
- For debugging, use `console.log({ var1, var2 })` to log objects with their variable names.
- Use `console.table()` to display arrays of objects in a tabular format.
- Use `console.time()` and `console.timeEnd()` to measure the performance of your code blocks.
- Use `console.trace()` to get a stack trace to understand the call path of a function.

## Destructuring
- Use object destructuring to extract properties from objects.
- Use destructuring in function parameters to make functions easier to use and read.

## Loops
- Prefer array methods like `map`, `filter`, `reduce`, `every`, and `some` over traditional `for` loops for cleaner and more declarative code.

## Functions
- Use rest parameters (`...args`) to handle a variable number of function arguments.

## Spread Syntax
- Use the spread syntax (`...`) to create new arrays or objects by expanding an iterable. This is useful for immutability.

## Template Literals
- Use template literals (`` ` ``) for string interpolation instead of string concatenation with the `+` operator.

## Libraries and Frameworks
- Use `octokit` for GitHub API interactions
- Use native `fetch` for HTTP requests
- Use `Highcharts` for charting

# Typescript

## Types
- Use libraries types instead of creating your own types when possible.
- Avoid using `any` type
