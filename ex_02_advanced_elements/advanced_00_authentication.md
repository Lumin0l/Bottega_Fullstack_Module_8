# How to apply authentication in React

Now we have the ability to build authentication directly into third-party apps even if they're not directly connected to the service that is logging them in.

For that we will use axios to create a session in a server.

Basically, we create a link to a server with axios and we set up a receiver for the response, if the response is satisfactory it ulocks components, otherwise no.

Example in course:

```
handleSubmit(event) {
    axios
      .post(
        "https://api.devcamp.space/sessions",
        {
          client: {
            email: this.state.email,
            password: this.state.password
          }
        },
        { withCredentials: true }
      )
      .then(response => {
        console.log("response", response);
      });

    event.preventDefault();
  }
```
