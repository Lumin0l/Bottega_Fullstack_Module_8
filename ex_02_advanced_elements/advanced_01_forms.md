# Forms in React

Unlike django, in react, the forms update the state of the object, so there is no different file that loads in the backend, it's all managed from the front.

we use the standard HTML "type", "name" and "placeholder".

There are a few considerations we need to bear in mind that aren't completely straightforward:

**State handler**: even though the JSX form fields handle imput from the user, that imput isn't going to change state on it's own, so we need to create a function that changes set state and attach it to the JSX so it gets triggered when the imput is introduced:

```
// handle change function:
handleChange(event) {
  this.setState({
    [event.target.name]: event.target.value
  });
}

// JSX:
 <<form onSubmit={this.handleSubmit}>
        <div>
          <input
            type="text"
            name="name"
            placeholder="Portfolio Item Name"
            value={this.state.name}
            onChange={this.handleChange}
          />

```

**Prevent default JS cuntionality to refresh page when submit**: In JS the sybmit type buttons trigger the refresh of the page, to avoid it we need to specify it and include it in the JSX form:

```
// Avoid Refresh function:
handleSubmit(event) {
	event.preventDefault();
}

// JSX:
<form onSubmit={this.handleSubmit}>
        <div>
          <input
            type="text"
            name="name"
            placeholder="Portfolio Item Name"
            value={this.state.name}
            onChange={this.handleChange}
          />
```

## Images

When working with images through forms we need to take different approaches, because images are composed of different data.

One approach we can get is creating an object in which we append the elements so the text based data is in one block, and the image based data in another:

```
// Object Builder:
buildForm() {
  let formData = new FormData();

  formData.append("portfolio_item[name]", this.state.name);
  formData.append("portfolio_item[desccription]", this.state.desccription);
  formData.append("portfolio_item[url]", this.state.url);
  formData.append("portfolio_item[category]", this.state.category);
}

// Created Object:
completeDataObject = {
	textData {
		name: "xxxx",
		url: "yyyy",
		...
	}

	imgData {
		...
	}
}
```

That way we can pass all at once to the API.

## Send form content to API

In the API we will need to find a POST verb url and create another axios that sends the object we created. Like this:

```
handleSubmit(event) {

  axios.post(
    "https://jordan.devcamp.space/portfolio/portfolio_items",
    this.buildForm(),
    { withCredentials: true}
  );

  event.preventDefault();
}
```
