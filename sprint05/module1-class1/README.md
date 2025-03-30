# HTML, the DOM, and Selecting DOM elements

## Introduction

Welcome to our engaging lesson on the intricacies of HTML, the Document Object Model (DOM), and how to manipulate the DOM using various selection methods. Through today's activities, you will learn how to interact with web pages dynamically, a skill crucial for any budding web developer. Imagine being able to update a website in real-time, adding interactivity and responsiveness. By the end of this lesson, not only will you understand the theory behind the DOM, but also be able to manipulate web pages like a pro.
## Core Competencies

1. Understanding the DOM
2. Inspecting the DOM with Chrome
3. Inspecting the global object
4. Inspecting a DOM node
5. Selecting nodes by ID
6. Selecting collections by class and tag
7. Selecting nodes with .querySelector ()
8. Selecting node lists with .querySelectorAll()
9. Iterating over a node list with .forEach()
## Coding Problems
### Understanding the DOM

**Relevance:** Imagine you're working as a web developer, and your task is to update the main headline of a corporate website to announce a new product launch. You decide to use JavaScript to manipulate the DOM so the headline reflects the exciting news without needing to alter the source HTML.

**Problem:** Using your knowledge of the DOM, update the text of an h1 element to 'New Product Launch!'

**Procedure:**

- Access the h1 element using the document.querySelector or document.getElementById method.
- Make sure the element exists by checking if the returned value is not null.
- Change the text content of the selected h1 element to the new headline.
- Verify in the browser that the text has changed on the webpage.
- Understand that if the page is refreshed, the change will be lost since we're modifying the DOM and not the HTML file itself.

**Code:**

```javascript
// Assumption: There is an h1 element with id='main-headline'
const headline = document.querySelector('#main-headline');
headline.textContent = 'New Product Launch!';
```
**Check For Understanding:** What would be the output for the following code? console.log(document.querySelector('h1').textContent);

### Selecting nodes by ID

**Relevance:** You're tasked with creating a dynamic user interface where clicking a button expands a detailed view of a product. To achieve this, you need to select a specific element by its ID and then manipulate its classes to reveal additional content.

**Problem:** Select an HTML element with an ID of 'details' and store it in a variable.

**Procedure:**

- Use the document.getElementById method to select the element.
- Assign the returned element to a variable named 'detailsElement'.
- Confirm that the variable contains the proper element by logging it to the console.
- Always check whether the element was successfully selected to prevent errors in subsequent code.

**Code:**

```javascript
// Assumption: There is an element with id='details'
let detailsElement = document.getElementById('details');
console.log(detailsElement);
```
**Check For Understanding:** How would you verify that the 'detailsElement' variable refers to the correct DOM element?

### Selecting collections by class and tag

**Relevance:** Working on an e-commerce site, you've been asked to quickly style all buttons to match a holiday sale theme. You'll need to select all elements with the 'button' class and apply a new class to them that has been predefined in the CSS.

**Problem:** Select all elements with the class 'button' and add a new class 'holiday-theme' to each element.

**Procedure:**

- Use document.querySelectorAll to select all elements with the class 'button'.
- Ensure that the NodeList returned by querySelectorAll is not empty.
- Loop through each element using the forEach method provided by NodeList.
- In each iteration, use the classList.add method to apply the 'holiday-theme' class.
- Log each element to the console to confirm the class has been added.

**Code:**

```javascript
// Assume that there are multiple elements with the class 'button'
document.querySelectorAll('.button').forEach(function(button) {
  button.classList.add('holiday-theme');
  console.log(button);
});
```
**Check For Understanding:** What would result if we applied element.classList.toggle('hidden') to an element with the code below? <div class='button hidden'></div>

## Sprint Challenge Preview

### Update Footer and Widgets

**Objective:** Add dynamic content and widgets to a web page footer using DOM manipulation.

**Functionality:**
- Update the footer text content with the current year.
- Add a class to widgets for styling.
- Create and append a 'Quote of the Day' widget.
- Create and append a 'Corporate Speak' widget to the footer.

**Conditions:**
- The footer should show the updated current year.
- All widgets should have the 'widget' class name applied.
- Widgets must be dynamically created using JavaScript.

**Hints:**
- Use JavaScript's Date object to get the current year.
- Query the DOM for the footer and widget elements before attempting modifications.
- For creating new elements, use document.createElement and append them using appendChild.

**Procedure:**
- Select the footer element using document.querySelector('footer').
- Create a new Date instance to get the current year.
- Update the footer's text content to include the current year.
- Select all elements with the class 'widget' using document.querySelectorAll and add an additional class for styling.
- Create the 'Quote of the Day' and 'Corporate Speak' widgets as new DOM elements.
- Append the widgets to the footer using the appendChild method.

**Code:**

```javascript
function updateFooterWidgets() {
  const footer = document.querySelector('footer');
  const currentYear = new Date().getFullYear();
  footer.textContent = `© MY COMPANY ${currentYear}`;

  // Task: Add widget class name
  document.querySelectorAll('.widget').forEach(widget => {
    widget.classList.add('new-widget-style');
  });

  // Task: Quote of the Day widget
  const quoteWidget = document.createElement('div');
  quoteWidget.classList.add('widget', 'quote-of-day');
  quoteWidget.textContent = 'Inspirational Quote Here';
  footer.appendChild(quoteWidget);

  // Task: Corporate Speak widget
  const speakWidget = document.createElement('div');
  speakWidget.classList.add('widget', 'corporate-speak');
  speakWidget.textContent = 'Synergize your paradigms!';
  footer.appendChild(speakWidget);
}
```

## Conclusion

Through this lesson, you've taken an important stride in understanding how to manipulate and interact with web pages using the DOM. By learning how to select, update, and style elements, you now possess the capability to make web pages dynamic and responsive. Remember, the DOM is the bridge between your JavaScript code and the user's experience, so mastering its manipulation is key to developing engaging web applications. Keep practicing, and you'll soon be crafting websites that are not only functional but also vibrant and alive.