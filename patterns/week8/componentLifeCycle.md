# React Component Lifecycle

Influenced by a three-part video series (strongly recommended!):

1.  https://www.youtube.com/watch?v=COKXmnxlxLo
2. https://www.youtube.com/watch?v=2geeamehCOc
3. https://www.youtube.com/watch?v=Hvk14LD7S98

The full component lifecycle is made up of the following:

* Initialisation
* State Changes
* Props Changes
* Unmounting

// Simple explanation of difference between props and state here, perhaps a code example.

### Initialisation

Order methods are invoked:

![diag](http://busypeoples.github.io/img/lifecycle_init.png)


```
getDefaultProps
```

(wip)

```
getInitialState
```

(wip)

```
componentWillMount
```

Access to the properties here. You can also set states.

```
render
```

Page will render as commanded within the function

```
componentDidMount
```

You can access the component elements in the DOM. Any DOM interactions should happen in this phase, not the ```render``` phase - you only want to modify DOM elements after they have already been rendered and are present in the page.

#### Use cases

You *may* want to use these commands if… (wip)

### State Changes

Order methods are invoked:

![diag](http://busypeoples.github.io/img/lifecycle_state.png)

```
shouldComponentUpdate
```

(wip)

```
componentWillUpdate
```

(wip)

```
render
```

Page will render as commanded within the function

```
componentDidUpdate
```

(wip)

#### Use cases

You *may* want to use these commands if… (wip)

### Props Changes

Order methods are invoked (watch for typo in top method!):

![diag](http://busypeoples.github.io/img/lifecycle_props.png)

Very similar to State changes except with the addition of:`

``componentWillReceiveProps```

(wip)

#### Use cases

You *may* want to use these commands if… (wip)

### Unmounting

Order methods are invoked:

![unmounting](http://busypeoples.github.io/img/lifecycle_unmount.png)

```
componentWillUnmount
```

This method gets called before the component is removed from the DOM. You might want to perform clean-up operations, for example if you wanted to remove any timers defined in ```componentDidMount```.

### Further Reading

Documentation - https://facebook.github.io/react/docs/component-specs.html
More detail on above - http://busypeoples.github.io/post/react-component-lifecycle/
