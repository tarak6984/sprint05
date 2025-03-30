# Manipulating DOM Elements and Adding New Elements to the DOM

## Introduction

Welcome to today's lesson on the dynamic world of DOM manipulation! As web developers, the Document Object Model (DOM) is our canvas for creating interactive and responsive websites. By the end of this lesson, you'll wield the power to add, modify, and style HTML elements right from your JavaScript code, just like a painter with a brush on a canvas. Picture a user interface on a website you enjoy—those elements were placed and styled using the techniques you're about to learn.
## Core Competencies

1. Setting text with .textContent
2. Setting attributes with .setAttribute
3. Setting inline styles with .style
4. Manipulating classes and IDs with .className
5. .classList and .id
6. Accessing the children and the parent nodes with .parentNode and .children
7. Creating DOM elements with .createElement()
8. Building out a new element
9. Adding children with .appendChild() and .prepend
10. Adding elements to the DOM with .insertAdjacentElement()
## Coding Problems
### Setting text with .textContent

**Relevance:** Imagine you're working on a blog platform. You need to dynamically update the headline of an article to reflect the latest news updates. Accomplishing this not only improves user experience but also keeps the content relevant and engaging.

**Problem:** Store the h1 text content in a variable 'heading' and then log it on the console.

**Procedure:**

- Use `document.querySelector` to select the first `h1` element.
- Create a `let` variable named `heading`.
- Assign the `textContent` of the `h1` element to the variable `heading`.
- Use `console.log` to output the value of `heading` to the console.

**Code:**

```javascript
const headingElement = document.querySelector('h1');
 let heading = headingElement.textContent;
 console.log(heading)
```
**Check For Understanding:** True or false: document.createElement adds a new element to the DOM.

### Setting attributes with .setAttribute

**Relevance:** On an e-commerce site, you may need to dynamically update product images as a user browses different items. The ability to change these image sources on the fly is crucial for a seamless shopping experience.

**Problem:** Write a code snippet that sets the attribute 'src' on the imageElement to a placeholder image link.

**Procedure:**

- Create an image element using `document.createElement('img')`.
- Use the `setAttribute` method to set the 'src' attribute to the provided URL.
- Check to ensure that the 'src' attribute has been updated by inspecting the element.

**Code:**

```javascript
let imageElement = document.createElement('img');
imageElement.setAttribute('src', 'https://place-hold.it/400x400');
```
**Check For Understanding:** What would result if we applied image.classList.toggle('bar') to the code below?
<img id="image" src="cat.jpg" class="foo" />

### Setting inline styles with .style

**Relevance:** You're creating a personalized theme for a user's dashboard. Giving users control over the site's appearance, such as font and color, makes their interaction personal and enjoyable.

**Problem:** Add an inline style to change the font of the body content.

**Procedure:**

- Use `document.body` to access the body element.
- Use the `style` property and assign the desired font-family stack to it.
- Test the updated style by viewing the body content's updated font.

**Code:**

```javascript
document.body.style.fontFamily = 'Verdana, Geneva, Tahoma, sans-serif';
```
**Check For Understanding:** True or false: document.createElement adds a new element to the DOM.

### Manipulating classes and IDs with .className, .classList and .id

**Relevance:** When updating a task in a to-do app, you need to switch its visual representation from 'incomplete' to 'complete'. This requires changing the element's class to apply different styles.

**Problem:** Create a variable named myElement1 and get the element with the id 'myh1'. Log myElement1's class name and id.

**Procedure:**

- Use `document.getElementById` to obtain the element with the ID 'myh1'.
- Assign the obtained element to the variable `myElement1`.
- Log the `className` and `id` properties of `myElement1` to the console.

**Code:**

```javascript
const myElement1 = document.getElementById('myh1');
console.log(myElement1.className);
console.log(myElement1.id);
```
**Check For Understanding:** How would you add all of the fruits in this array to the body of the page?
const fruits = ['apples', 'oranges', 'lemons', 'limes'];

### Accessing the children and the parent nodes with .parentNode and .children

**Relevance:** You're tasked with creating a feature that summarizes the contents of a section. Being able to list out child elements programmatically is a quick way to generate such summaries.

**Problem:** List the children elements of the 'About the Solutions' section.

**Procedure:**

- Select the element that represents the 'About the Solutions' section using `document.querySelector`.
- Access the `children` property of the element to get its children.
- Loop through the children and log each to the console.

**Code:**

```javascript
const solutionSectionElement = document.querySelector('.about-solutions');
console.log(solutionSectionElement.children);
```
**Check For Understanding:** What would result if we applied image.classList.toggle('bar') to the code below?
<img id="image" src="cat.jpg" class="foo" />

### Creating DOM elements with .createElement()

**Relevance:** When building a news feed, new stories need to be added dynamically as they come in. Using `createElement`, you can add breaking news quickly to the feed.

**Problem:** Create a new paragraph element and add it to the document body with your favorite number.

**Procedure:**

- Use `document.createElement` to create a new paragraph element.
- Set the `textContent` property of the paragraph element to a string including your favorite number.
- Use `document.body.appendChild` to add the paragraph to the document's body.

**Code:**

```javascript
const paragraph = document.createElement('p');
paragraph.textContent = 'My favorite number is 7';
document.body.appendChild(paragraph);
```
**Check For Understanding:** True or false: document.createElement adds a new element to the DOM.

### Adding children with .appendChild() and .prepend

**Relevance:** Imagine you're adding notifications to a user's homepage. These must appear at the top of their queue. Being able to prepend elements ensures they're seen immediately.

**Problem:** Prepend a new heading element to the body of the document.

**Procedure:**

- Create a new heading element using `document.createElement`.
- Set the `textContent` of the heading to the appropriate message.
- Prepend the new heading to the body using `document.body.prepend`.

**Code:**

```javascript
const heading = document.createElement('h2');
heading.textContent = 'Process has ended here.';
document.body.prepend(heading);
```
**Check For Understanding:** How would you add all of the fruits in this array to the body of the page?
const fruits = ['apples', 'oranges', 'lemons', 'limes'];

### Adding elements to the DOM with .insertAdjacentElement()

**Relevance:** Working on an interactive step-by-step guide, you need to add an instruction between steps. The insertAdjacentElement function is perfect for adding content exactly where it needs to go.

**Problem:** In the 'recap' section, insert a p element with the text 'List begins here' after the header and before the list items.

**Procedure:**

- Select the ordered list type using `document.querySelector('ol')`.
- Create a new paragraph element with `document.createElement('p')`.
- Set the textContent of the paragraph to 'List begins here'.
- Use `insertAdjacentElement` to place the new paragraph before the ordered list (using 'beforebegin').

**Code:**

```javascript
const orderedList = document.querySelector('ol');
const p1 = document.createElement('p');
p1.textContent = 'List begins here';
orderedList.insertAdjacentElement('beforebegin', p1);
```
**Check For Understanding:** True or false: document.createElement adds a new element to the DOM.

### Setting attributes with .setAttribute

**Relevance:** Imagine you're automatically updating links to reference materials to their newest editions. Using setAttribute to update the href could save hours and prevent errors.

**Problem:** Set the 'href' attribute on the element with an ID of 'link-element' to a mock URL address.

**Procedure:**

- Get the link element by its ID using `document.getElementById`.
- Use `setAttribute` to change the 'href' attribute to the new URL.
- Verify the 'href' has been updated by inspecting the element in the browser.

**Code:**

```javascript
let linkElement = document.getElementById('link-element');
linkElement.setAttribute('href', 'http://www.example.com');
```
**Check For Understanding:** What would result if we applied image.classList.toggle('bar') to the code below?
<img id="image" src="cat.jpg" class="foo" />

### Creating DOM elements with .createElement()

**Relevance:** Consider creating a custom chat interface where new messages appear in real-time. You would need to create new elements for each message, style them, and insert them into the DOM efficiently.

**Problem:** Append the childElement to the parentElement.

**Procedure:**

- Assume that the parentElement exists and is selected using `document.getElementById`.
- Create a new div element using `document.createElement('div')`.
- Append the newly created div element as a child to the parentElement using `appendChild`.

**Code:**

```javascript
let parentElement = document.getElementById('parent');
let childElement = document.createElement('div');
parentElement.appendChild(childElement);
```
**Check For Understanding:** True or false: document.createElement adds a new element to the DOM.

## Sprint Challenge Preview

### Challenge 1: Build a Countdown widget

**Objective:** Create a function that updates a countdown timer every second until it reaches zero.

**Functionality:**
- This Countdown widget should update in real-time but must not exceed the browser's limitations.

**Conditions:**
- Ensure the timer stops at zero to prevent negative values, and handle any exceptions that may occur.

**Hints:**
- You'll need to use setInterval to update the timer at one-second intervals.
- Remember to clear the interval when the countdown reaches zero to stop the function.

**Procedure:**
- Create the base timer variable and set the starting countdown value.
- Use setInterval to create a function that decreases the timer value every second.
- Check if the timer is zero; if so, clear the interval.
- Update the DOM element representing the timer with the new value each second.

**Code:**

```javascript
// 👉 TASK 4 - Build a 'Countdown' widget
var countdown = 10;
var intervalId = setInterval(function() {
  if(countdown > 0) {
    document.getElementById('timer').textContent = countdown;
    countdown--;
  } else {
    clearInterval(intervalId);
  }
}, 1000);
```

## Conclusion

Throughout this adventure into DOM manipulation, we've infused life into static web pages by programmatically altering elements—adding, removing, styling, and more. These skills form the backbone of dynamic web development, allowing you to respond to user actions and events. Remember, with great power comes great responsibility; use these skills to enhance user experience and build intuitive interfaces. Keep practicing, and soon you'll be sculpting the DOM like a seasoned artist.