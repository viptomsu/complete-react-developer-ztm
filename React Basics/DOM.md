# DOM tree

- is Document object model
- encapsulate all different elements in our application
- expensive to make changes (painting process) (add, update, move nodes ...)

  > quick to figure out thing to be changed but changing process (add, update, remove things from the DOM) is expensive

- reflow when adding or removing elements, or when layout needs to be shifted

  > reflow is the web browser process for re-calculating the positions and geometries of elements in the document

- repaint happens when browser redraws web page (follow reflow). This is expensive process

# Virtual DOM

- is a duplicate copy of the real DOM
- reflects all elements in JS
- use to determine what's changed

> a Javascript presentation of the real DOM

=> quicker to make changes

# Rendering process

1. Make another cope of the Virtual DOM, use the Virtual DOM as a snapshot (of what real DOM looks like)
2. Something triggers rerender (setStates)
   > React will batch the setState calls if they're fast enough. And a bunch of optimizations
3. Rerender all the children of the component that has states changed but smart enough to only update the component that is changed
4. Update everything from these changes -> get the new Virtual DOM
5. Compare Virtual DOM copy with the Virtual DOM snapshot
6. Apply the changes to the real DOM
