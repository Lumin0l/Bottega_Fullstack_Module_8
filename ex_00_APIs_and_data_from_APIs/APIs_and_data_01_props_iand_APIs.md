# Working with Props and APIs

## Initial Considerations

When we create a function that will work with information coming from an API, the most basic question we'll have is a true-false state check: to find if the page where we are is authenticated, to check day-night styles...

In React JS you shouldn't simply do "state: true;", it will interpret empty answer's as true and have some other kinds of issues.
What we do in this case is create a control string: "status: "LOGGED_IN";", that way it will act on exact true false terms.

## Updating a Parent Component's State from a Child Component

Useful things, remember whenever we pass a props that comes from another function we need to **bind** it.

`this.handleSuccessfulAuth = this.handleSuccessfulAuth.bind(this);`

### props.history

history is a route value that will store a user's activity in the page. It is useful because it creates an anchor path to the different parts of the page.
