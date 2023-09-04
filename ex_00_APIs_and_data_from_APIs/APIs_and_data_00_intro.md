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

The universal JS tool to find out the keys of an object, since that will be the most common need that we will encounter, is `object.keys(item-in-question)`. This will output only the keys so we can identify them and use them.

After extracting the keys, the best practice would be to do what it's called **destructuring**, or to extact the keys of an object into vars.

In our example, where we are looping through each object extracted from the API using .map(), we can add the destructurer into the loop to extract the keys and use them as normal vars in our code. To achieve that, first we need to know the names of the keys, using some of the methods learned, and then we use them like this, in our case:

```
const { id, description, thumb_image_url, logo } = props.item;
```

After doing this, we can use the elements as vars:

``` 

```

## React Dev Tools method

React dev tools can be opened from one of the inspect tabs and it will allow us to visualize some specific react elements, like: props, the parent-child component relationships...

There you can click on the specific element and it will showcase the object stored in the component.
