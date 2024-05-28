# When React update the DOM:

## State:

- When state object is a different object
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

# SPA

- Initial request -> HTML, CSS, JS (React) entire bundle code
- Navigate to another page, react build CSS and HTML code for that page, no need to go to server

# Lifecycle Method

## Orders:

constructor -> render -> componentDidMount

## componentDidMount:

- mounted: the first time component was rendered in the DOM

## render:

- every time render runs, anonymous function is created again

# React Events (SyntheticEvent)

- React generates event wrapper around browser's native event
