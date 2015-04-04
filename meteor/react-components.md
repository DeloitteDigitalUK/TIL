# React components in Meteor #

With [`react-meteor`](https://github.com/reactjs/react-meteor) package Meteor's templating can be extended with React components.

### Install react-meteor ###
In you app root directory:
```sh
$ meteor add reactjs:react
```


### Add template partial ###
```html
<template name="home">
    <h1>My React-Meteor page</h1>
    {{> MyComponent}}
</template>
```


### Add jsx file ###
On your client add `example.jsx` with the following code:
```javascript
/**
 * @jsx React.DOM
 */

var MyComponent = ReactMeteor.createClass({
    templateName: 'MyComponent',

    getMeteorState: function() {
        return {
            answer: 42
        };
    },

    render: function () {
        return <div>Meaning of life: {this.state.answer}</div>
    }
});
```
Pretty much every line above is required.
`ReactMeteor` is used to define a component, `templateName` refers to the template name in your view. Make sure that you implement `getMeteorState` and `render` methods.

### Run Meteor ###
Now sit back and enjoy the ride:
```sh
$ meteor
```
