# High Order Components

Read in the documentation.

It's an advanced technique to reuse component logic. They are not part of React per se, they are just a pattern that emerges from it's compositional nature.

It allows to wrap up a functionality into a var and use it in other functions.

Ex: `const EnhancedComponent = higherOrderComponent(WrappedComponent);`

They will start with a lowercase letter to differenciate them from other components, like "highOrderComponentOne".
