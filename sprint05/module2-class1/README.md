# Events, Their Types, and Adding Event Listeners in JS

## Introduction

Welcome to our adventure into the interactive world of JavaScript events! Today, we'll explore the foundations of how web users interact with pages—through a variety of events. Whether it's clicking a button, pressing a key, or resizing a window, events are the heartbeat of user experience. By the end of this lesson, you'll not only recognize different event types but also add event listeners to HTML elements and prevent default actions where necessary. Imagine you're creating the next viral game or an app that needs quick and responsive feedback from the user; mastering events is key to bringing that interaction to life!
## Core Competencies

1. Understanding events
2. Understanding the types of events
3. Handling events with HTML attributes
4. Handling an event with .addEventListener()
5. Studying the event object
6. Preventing the default action
## Coding Problems
### Handling an event with .addEventListener()

**Relevance:** You're tasked with building a live vote counting system for a talent show. Each time an audience member likes a performance, they click a 'vote' button. Your code must tally these votes in real-time, displaying updates without a page reload - a perfect scenario for using .addEventListener().

**Problem:** Attach an event listener to a button that, when clicked, increments and displays a count.

**Procedure:**

- Start by selecting the button element using document.getElementById('counterBtn').
- Select the display element where the count will be updated using document.getElementById('countDisplay').
- Initialize a variable, count, to keep track of the number of clicks, starting at 0.
- Add an event listener to the button element that listens for the 'click' event.
- Inside the event listener's callback function, increment the count variable by 1.
- Update the text content of the count display element with the new count.

**Code:**

```javascript
let count = 0;
const counterBtn = document.getElementById('counterBtn');
const countDisplay = document.getElementById('countDisplay');
counterBtn.addEventListener('click', function () {
  count++;
  countDisplay.textContent = count;
});
```
**Check For Understanding:** What does the code button.addEventListener('click', callback); do when the button is clicked?

### Studying the event object

**Relevance:** As a developer for an e-commerce site, it's your job to enhance the shopping experience. You've been asked to implement a feature that reacts when users press keys to navigate a gallery of products. Understanding the event object is crucial for distinguishing which key was pressed.

**Problem:** Register an event handler that logs the key pressed by the user.

**Procedure:**

- Select the document object to handle global key events.
- Add an event listener for the 'keypress' event to the document.
- Create a callback function that will be triggered whenever a key is pressed.
- Log the 'event.key' property to the console to see which key was pressed.

**Code:**

```javascript
document.addEventListener('keypress', function(event) {
  console.log(event.key);
});
```
**Check For Understanding:** When a key is pressed, what information does the 'event' object give access to?

### Preventing the default action

**Relevance:** You are in charge of a website's security, and to prevent content theft, you need to disable the default copy function of the browser. This real-world task requires you to know how to intercept and negate certain default browser actions using JavaScript.

**Problem:** Prevent the default copy action on a webpage.

**Procedure:**

- Create an event handler function that calls 'event.preventDefault()' method.
- Attach this handler to the 'copy' event on the document object.
- Now, when a user tries to copy text from the webpage, the default copy action will be canceled.

**Code:**

```javascript
document.addEventListener('copy', function(event) {
  event.preventDefault();
});
```
**Check For Understanding:** What is the outcome when event.preventDefault() is called inside an event handler function?

### Understanding events

**Relevance:** Suppose you're creating a feature for a web application that allows the user to show or hide sensitive information with a toggle functionality. This common feature requires understanding how to handle click events effectively.

**Problem:** Implement a click event handler that toggles the display of an element.

**Procedure:**

- Select the toggle button using getElementById.
- Select the content to be toggled similarly.
- Add an event listener to the toggle button for click events.
- In the event handler function, use a conditional statement to check the current display style of the content element.
- Based on the current state, change the style.display property to either 'none' or 'block', effectively toggling its visibility.

**Code:**

```javascript
const toggleBtn = document.getElementById('toggleBtn');
const toggleContent = document.getElementById('toggleContent');
toggleBtn.addEventListener('click', function () {
  if (toggleContent.style.display === 'none') {
    toggleContent.style.display = 'block';
  } else {
    toggleContent.style.display = 'none';
  }
});
```
**Check For Understanding:** How do you toggle the visibility of an element in response to a click event?

### Handling events with HTML attributes

**Relevance:** Imagine you're developing an interactive kiosk for a museum. When a visitor presses a button, they hear a narration of the exhibit. This requires using HTML attributes to handle events directly in the markup, allowing for rapid prototyping and straightforward setups.

**Problem:** Use an HTML attribute to log 'Hello, world!' when a button is clicked.

**Procedure:**

- Select the button with the specific ID using querySelector.
- Assign a function to the onclick property of the button element.
- This function should log 'Hello, world!' to the console when invoked.

**Code:**

```javascript
const cyanBtn = document.querySelector('#btn1');
cyanBtn.onclick = function () {
  console.log('Hello, world!');
};
```
**Check For Understanding:** Explain the difference between assigning an event handler via HTML attributes versus using addEventListener.

### Handling events with HTML attributes

**Relevance:** While working on user analytics for a web platform, you decide to track which buttons users interact with. Using HTML attributes, you plan to log the text from buttons upon clicks, providing key insights into user preferences.

**Problem:** Assign an 'onclick' handler to log the text content of a button.

**Procedure:**

- Select the desired button using querySelector.
- Assign an 'onclick' event handler to the button.
- In the 'onclick' event handler, log the button's text content to the console.

**Code:**

```javascript
const yellowBtn = document.querySelector('#btn2');
yellowBtn.onclick = function () {
  console.log(yellowBtn.textContent);
};
```
**Check For Understanding:** What does using an HTML attribute such as onclick to assign an event handler entail, and why might it be or not be recommended?

### Understanding the types of events

**Relevance:** You've been hired to build a feature for a chat application that alerts users loud and clear whenever a message is sent. For this, you'll need to use the 'click' event type effectively to create a responsive and intuitive user interface.

**Problem:** Create a button that alerts 'Button clicked!' when it is clicked.

**Procedure:**

- Create a new button element with createElement.
- Set the text of the button to instructive text such as 'Click Me!'.
- Add a 'click' event listener to the button that triggers an alert with the desired message.
- Select the body element and append the button to it.

**Code:**

```javascript
const button = document.createElement('button');
button.textContent = 'Click Me!';
button.addEventListener('click', function() {
  alert('Button clicked!');
});
const body = document.querySelector('body');
body.appendChild(button);
```
**Check For Understanding:** What steps are involved in creating an element in JS and adding an event listener to it?

### Understanding events

**Relevance:** On your first day at a startup, you're given a task to build a quick survey form. It includes a small input field and a button to submit responses. Learning how to handle the 'click' event to grab input values is your stepping stone to success.

**Problem:** Retrieve and console log the value from an input field when a button is clicked.

**Procedure:**

- Create a new input field element and set the necessary properties like 'type' and 'id'.
- Create a button element and set its 'textContent'.
- Write a handler function for the 'click' event that retrieves the value of the input field.
- Use addEventListener to attach the click event to the button.
- Append both the input field and the button to the document body.

**Code:**

```javascript
const inputField = document.createElement('input');
inputField.type = 'text';
inputField.id = 'inputField';
inputField.placeholder = 'Enter text';
const submitButton = document.createElement('button');
submitButton.textContent = 'Submit';
submitButton.addEventListener('click', function() {
  const inputValue = inputField.value;
  console.log('Input value: ' + inputValue);
});
document.body.appendChild(inputField);
document.body.appendChild(submitButton);
```
**Check For Understanding:** Describe the process and code needed to retrieve user input from a form control in a web page with JavaScript.

### Studying the event object

**Relevance:** You're in the trenches coding a feature for a gaming website that requires you to track the player's actions in real time. Here's where understanding the event object becomes essential, allowing you to respond to user-initiated events like mouse clicks, movements, and key presses.

**Problem:** Use event properties to log information about the event itself.

**Procedure:**

- Create a handler function that accepts an event object as its parameter.
- Within the function body, log the event object to the console to inspect its properties.
- Attach this handler to any event of your choice (e.g., a button click, mouse movement) using addEventListener.

**Code:**

```javascript
const handleEvent = (event) => {
  console.log(event);
};
```
**Check For Understanding:** When an event handler function is executed, what is passed to it by default?

### Understanding events

**Relevance:** Your latest project is a rich text editor for a blogging platform. As part of the requirements, you need to allow users to customize their experience but also want to reserve some control—like preventing certain default behaviors such as the cut command.

**Problem:** Prevent the default 'cut' action within the web application to preserve text.

**Procedure:**

- Select the document object to handle the action globally.
- Create an event handler that will call the event.preventDefault() method when the 'cut' event fires.
- Assign this handler to the document's 'cut' event using document.addEventListener.

**Code:**

```javascript
document.addEventListener('cut', function(event) {
  event.preventDefault();
});
```
**Check For Understanding:** What is the rationale for preventing a default action in a web application, and how can you achieve that using JavaScript?

## Sprint Challenge Preview

### Challenge: Advanced Event Handling

**Objective:** Deepen your understanding of JavaScript event handling by creating a dynamic user interface that reacts to various user actions using both inline HTML attributes and the `.addEventListener()` method, with a focus on efficiency and advanced event concepts.

**Functionality:**
- Task 1: Dynamic Content Creation with Events.
    - Build an HTML page that includes a text input, a button labeled "Add Item", and an empty ordered list (`<ol>`).
    - Implement functionality using `.addEventListener()` that adds the text input's value as a new list item (`<li>`) to the ordered list when the "Add Item" button is clicked.
    - Ensure that entering text and clicking the button repeatedly adds multiple items to the list.

- Task 2: Using Event Delegation for Efficiency.
    - Implement a single event listener on the ordered list to manage clicks on individual list items.
    - When a list item is clicked, change its text color to red. This demonstrates the use of event delegation to avoid attaching an event listener to each list item individually.

**Conditions:**
- Input validation: Do not add empty items to the list. Display an alert if the "Add Item" button is clicked without entering any text.
- Clean coding practices: Ensure the JavaScript code is well-organized, with comments explaining key functionalities and decisions.
- Use of event delegation: Properly implement event delegation for the list item click event to minimize the number of event listeners added to the page.

**Hints:**
- Research and utilize the `event.target` property within your event delegation logic to identify which list item was clicked.
- Consider creating a separate function for adding list items to keep your code organized and avoid code duplication.
- Remember to clear the text input after adding an item to the list to improve the user experience.

**Procedure:**
1. Create the HTML structure including a text input, an "Add Item" button, and an empty ordered list.
2. Use JavaScript to implement the "Add Item" button functionality that adds the input value as a new list item, ensuring the input is not empty.
3. Implement event delegation on the ordered list to change the text color of clicked items, highlighting the efficiency of handling events on multiple elements.

**Code:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Advanced Event Handling Challenge</title>
</head>
<body>
    <input type="text" id="itemInput" placeholder="Enter an item">
    <button id="addItemBtn">Add Item</button>
    <ol id="itemList"></ol>

    <script>
        document.getElementById('addItemBtn').addEventListener('click', function() {
            var input = document.getElementById('itemInput');
            var itemText = input.value.trim();

            if(itemText === '') {
                alert('Please enter an item.');
                return;
            }

            var li = document.createElement('li');
            li.textContent = itemText;
            document.getElementById('itemList').appendChild(li);
            input.value = ''; // Clear input field after adding an item.
        });

        // Implementing event delegation for the list
        document.getElementById('itemList').addEventListener('click', function(event) {
            if(event.target.tagName === 'LI') {
                event.target.style.color = 'red';
            }
        });

        /* This approach reduces the need to attach an event listener to each list item,
        utilizing event bubbling to handle clicks at a higher level (the <ol> element). */
    </script>
</body>
</html>

## Conclusion

We've navigated the dynamic seas of JavaScript events together, anchoring our skills on .addEventListener(), exploring the rich event object, and even preventing default browser behaviors to shape user experience exactly as we desire. Whether it's counting votes, toggling visibility, or handling keypresses, the real power lies in harnessing these events to drive meaningful interactions on your web applications. Keep exploring, keep building, and remember that every line of code you write has the potential to create waves of change across the digital landscape.