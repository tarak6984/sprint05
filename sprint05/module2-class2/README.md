# Event Propagation

## Introduction

Welcome to the exciting world of Event Propagation in JavaScript! In this lesson, you'll learn how events traverse the Document Object Model (DOM), and how you can control this flow to create interactive, responsive web pages. Imagine a music festival website where clicking different stages shows different line-ups without refreshing the page. By the end of this lesson, you'll understand how to harness event propagation to make such experiences seamless for the user.
## Core Competencies

1. Understanding the phases of propagation
2. Finding the target and the current target of an event
3. Stopping propagation
## Coding Problems
### Understanding the phases of propagation

**Relevance:** At a tech conference, when an attendee clicks a 'Session Info' button, they expect to see details without unwanted pop-ups. Handling event propagation correctly ensures that clicking one button doesn't trigger listeners unrelated to the user's intention. It's essential for providing a smooth user experience.

**Problem:** Identify and log the stages of event propagation when clicking an element.

**Procedure:**

- Attach a click event listener to a button element, logging 'Button clicked' when it is clicked.
- Attach click event listeners to all of the button's parent elements up to the document, logging which element was clicked.
- Determine if the bubbling phase or the capturing phase is used by default by JavaScript's event listeners.
- Use `event.stopPropagation()` to prevent the event from bubbling up past the button's immediate parent.
- Observe the console to verify that parent elements no longer log the click after the button's parent.

**Code:**

```javascript
button.addEventListener('click', e => {
  console.log('Button clicked');
  e.stopPropagation();
});

document.addEventListener('click', () => console.log('Document clicked'));

```
**Check For Understanding:** What is the default phase for event propagation in JavaScript? How can you alter this behavior?

### Finding the target and the current target of an event

**Relevance:** While working on a quiz website, a developer must display a tooltip with additional information when a question is clicked. Knowing the event's `target` and `currentTarget` helps to display tooltips correctly even when nested elements are present.

**Problem:** Access and log the `target` and `currentTarget` of an event object when an element is clicked.

**Procedure:**

- Select an element and attach a click event listener to it.
- In the event listener's callback function, use `event.target` to access the clicked element.
- Also, use `event.currentTarget` to access the element the listener is attached to.
- Log both `target` and `currentTarget` to the console.
- Click on different child elements to see how `target` and `currentTarget` differ.

**Code:**

```javascript
element.addEventListener('click', event => {
  console.log('Target:', event.target);
  console.log('Current target:', event.currentTarget);
});
```
**Check For Understanding:** How do `event.target` and `event.currentTarget` differ in the context of event propagation?

### Stopping propagation

**Relevance:** In an eCommerce application, click events on nested elements like buttons in cards can cause issues if not managed properly. Preventing event propagation stops further event handling where it's not required, avoiding unintended consequences like navigating to a new page when adding an item to the cart.

**Problem:** Prevent the event from propagating beyond a certain point in the DOM tree.

**Procedure:**

- Select an element and add a click event listener to it and its parent and child elements.
- In each callback function, log that the element has been clicked.
- For the chosen element, use `event.stopPropagation()` within its event listener to halt event propagation.
- Click on the element and check the console to confirm that only its listener logs a message.
- Ensure that the parent and child elements' listeners do not log messages when the chosen element is clicked.

**Code:**

```javascript
element.addEventListener('click', event => {
  console.log('Element clicked');
  event.stopPropagation();
});

parent.addEventListener('click', () => console.log('Parent clicked'));
child.addEventListener('click', () => console.log('Child clicked'));

```
**Check For Understanding:** What is the effect of calling `event.stopPropagation()` inside an event listener?

## Sprint Challenge Preview

### Propagation Control Challenge

**Objective:** Create an interplay between an element and its ancestors so that events are managed according to specificity. Demonstrate understanding of event propagation mechanisms by enabling and disabling them.

**Functionality:**
- ["Identify the event's propagation path and prevent unnecessary handlers from being executed."]
**Conditions:**
- Listeners should log when and where they are triggered, and some should prevent the event from moving further up the DOM.

**Hints:**
- Be deliberate about where to call `stopPropagation()` in the event handling sequence.

**Procedure:**
- Attach event listeners to a series of nested elements, each logging its activation.
- Invoke `stopPropagation()` on a specific listener to prevent further propagation.
- Test the event propagation by clicking the target element and observing the console output.

**Code:**

```javascript

const button1 = document.querySelector('#A1');
const button2 = document.querySelector('#A2');
const button3 = document.querySelector('#A3');
const div = document.querySelector('#B');
const section = document.querySelector('#C');

Array.from(document.getElementsByTagName('*')).forEach(elem => {
  elem.addEventListener('click', evt => {
    const { id, nodeName } = evt.currentTarget;
    console.log(`Event handler firing at ${id} (${nodeName})`);
    if (evt.target === button1) {
      evt.stopPropagation();
    }
  })
});

```

## Conclusion

Today we dove into the fascinating process of event propagation in JavaScript, surfacing the intricate ways events move through the DOM. You now have the knowledge to create user experiences that feel intuitive and logical. By manipulating event flow, you have a new set of tools to build web applications that are not only functional but intuitive and user-friendly. Remember, the key to mastery is practice, so keep experimenting with event listeners and propagation models to create interactive web pages that shine.