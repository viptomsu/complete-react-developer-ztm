# When React update the DOM:

- When state object is a different object
- Don't rerender when reassign the `this.state` object
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
