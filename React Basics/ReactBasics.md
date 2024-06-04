# SPA

- Initial request -> HTML, CSS, JS (React) entire bundle code
- Navigate to another page, react build CSS and HTML code for that page, no need to go to server

# React 18

- strict mode prevent using deprecated methods
- ensure us to follow React best practices
- strict mode rerender everything twice to catch any weird behaviors might occur in side effects

# Class component

## Components rerender:

- When props changes
- When state object is a different object
- When parent component rerender (if not use PureComponent)
- Don't rerender when reassign the `this.state` object

## setState

- `this.setState` shallow merge new state

```js
this.state = {
	name: "Quang",
	city: "Ha Noi",
};

this.setState({ name: "Trang" });
// Then
this.state = {
	name: "Trang",
	city: "Ha Noi",
};
```

- run asynchronous cuz React batches different setState calls -> optimal strategy to rerender
- second argument call after setState calls

```js
this.setState((state) => ({ count: state.count + 1 }));
this.setState(
	(state, _props) => {
		return { count: state.count + 1 };
	},
	() => {
		console.log("state updated", this.state);
		// count increased by 2
	}
);
```

# Lifecycle Method

**[Diagram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)**

## Orders:

constructor -> render -> componentDidMount

## componentDidMount:

- mounted: the first time component was rendered in the DOM

## render:

- severy time render runs, anonymous function is created again
  \
  \

# React Events (SyntheticEvent)

- React generates event wrapper around browser's native event
  \
  \

# Functional component

- is JS function, takes argument (props) and return JSX that's all
- run from top to bottom
- there are no life cycles

## 1. Pure Function

Will always return the same thing given the same arguments no matter how many times it's called

```js
const pureFunc = (a, b) => a + b;

let c = 5;

const imPureFunc = (a, b) => a + b + c;
```

When it doesn't procedure **side effects**

> A side effect is when a function creates some kind of effect outside of its scope

```js
let c = 5;

const funcCauseSideEffect = (a, b) => {
	c = a + b;
	return a * b;
};
```

> Impure Function is function modify or rely on something outside of its scope

hooks generates side effects
Use hooks to create impure function

## 2. Rerender

- React compare `===` the state from useState hook to determine if it needs to rerender
- When props changes

- React runs the entire function when it needs to rerender a functional component
- Similar to `render` method in class component

## 3. useEffect hook

- useEffect to create side effects
