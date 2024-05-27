# React Concepts:

## 1.Don't touch the DOM. React do it!

Imperative: Difficult to see relationship between events and edge cases

Dom manipulation is one of the biggest performance bottlenecks
-> React takes care of this

Declarative: this is what the state of the page, the difference is all the states are accounted in one place (one big Js object)

## 2.Build websites like lego blocks

Design around the concept of reuseable components

## 3.One way data flow (unidirectional)

**Virtual DOM**

- Js version of the DOM
- is Js object describe the app
- give React blueprint how it should update the actual DOM
- when state changes, combine with components and update the DOM
- states always move down -> easy to debug

## 4.Just UI

- React is a UI library only cares about ideas of components, the virtual DOM
- Has two parts: React core and React DOM
- Write everywhere: Web, Desktop, VR, Mobile with the same idea

## Job of React Dev:

1. Decide on Components
2. Decide the State and where it lives
3. What changes when state changes
