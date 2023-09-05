# Styles in React

There is many ways of applying styles in a React project. There is no "best way of doing it", or else, everyone would be doing it.

This will be the way picked by the course.

## SCSS Hierarchy

We'll go to the **src/style** folder of the react project and we will find _main.scss_. We will use it as our foundation file where we will import all other files. Being so, we will take all the code in it and store it in another file, that we will call _base.scss_. Then we will import base into main with; `@import "./base.scss";`

It is also very important to set the import statements correctly. CSS is casding, so we want the more general files (variables, mixins...) on the top and the more specific in the bottom. Otherwise we'll get errors.

## Importing elements to HTML

If you want to import stuff into the HTML, such us fonts, it should be done into the **index.html** file.

## HTML Architecture

In react we create the html from the components, writting stuff in the shape of JSX. That's why it's very important to have a good structure, to put each element (navbar, footer... ) in their folders and to have a main component file where it gets rendered. In that component, in the render method, we can create our classes and ids.

Bear in mind that "class" is a react keyword, and that we should use **className**.

The styles in the scss are applied normally.

The styles, if applied inline, are applied differently in JSX. instead of 

```
style="color:blue;font-size:46px;
```

we do: 

```
style={{
    backgroundImage: "url(" + thumb_image_url + ")"
}}

```

It's just important to remember that JSX styles have a different syntax to scss, and to switch from one to the other.