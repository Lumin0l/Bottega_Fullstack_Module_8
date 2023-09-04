# Intro to Using data from APIs

Normally the data that comes from APIs will be unkown to us. We need to find a way to visualize it in order to know how to use it in our ptogram.

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
