# Intro to Using data from APIs

Normally the data that comes from APIs will be unkown to us. We need to find a way to visualize it in order to know how to use it in our ptogram.

## Console.log method

The easiest way to do it would be to `console.log` the API answer, like in the following example:

```
portfolioItems() {
    return this.state.data.map(item => {
      console.log("portfolio item", item);
      return (
        <PortfolioItem
          key={item.id}
          title={item.name}
          url={item.url}
          slug={item.id}
        />
      );
    });
  }
```

## JS Debugger method

The `debugger` keyword in React allow to launch a debugger functionality in browser. The program will "freeze" at that spot and it will allow us to run commands and functions in the terminal in that specific moment of the program. So, in our example, it allows us to stop once we receive the "item" from the API and query it with "item.name", "item.picture"...

```
portfolioItems() {
    return this.state.data.map(item => {
      debugger;
      return (
        <PortfolioItem
          key={item.id}
          title={item.name}
          url={item.url}
          slug={item.id}
        />
      );
    });
  }
```
