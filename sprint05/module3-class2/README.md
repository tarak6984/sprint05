# Building DOM Using Components and Data

## Introduction

In today's digital landscape, webpages are no longer static brochures of information, but dynamic platforms for user interaction and data presentation. Understanding JSON and DOM manipulation is essential for any modern web developer, as these skills allow for the structured delivery and display of web content. In this lesson, we'll delve into JSON documents, parsing JSON data, and using that data to build DOM elements. We'll create engaging, reusable components that render content seamlessly onto a webpage, much like a chef artfully plating a meal, turning raw ingredients into an enticing dish.
## Core Competencies

1. Understanding JSON documents
2. Parsing JSON
3. Iterating over data to build JSON
## Coding Problems
### Understanding JSON documents

**Relevance:** Imagine you're running a buzzing online bookstore. Every morning, an updated list of bestsellers arrives as a JSON document. But here's the challenge: you need to quickly decipher this JSON to update your website's front page. Mastering JSON is key to making this daily update fast and error-free.

**Problem:** Determine if the given JSON array contains a boolean value.

**Procedure:**

- Declare a variable and assign the given JSON array to it.
- Use the Array.prototype.some() method to check for a boolean value.
- Provide a callback function within some() to check the data type using typeof.
- Log the result to the console for verification.

**Code:**

```javascript
let jsonArray = [100, 500, "false", 300, "hello", 200, 400];
let containsBoolean = jsonArray.some(item => typeof item === 'boolean');
console.log(containsBoolean); // Outputs: false
```
**Check For Understanding:** Components bring together data in an encapsulated, reusable form. The idea behind components is to build functions that take data as arguments and return what?

### Parsing JSON

**Relevance:** You're a weather app developer and you've just received live weather data in JSON format from a remote API. To display it on the app, you need to parse the JSON into an object your JavaScript code can manipulate.

**Problem:** Parse a JSON data set into a JavaScript object and log a specific property value.

**Procedure:**

- Use JSON.parse() to convert the JSON string into a JavaScript object.
- Access the desired property of the object.
- Use console.log to print the value of the property.

**Code:**

```javascript
const json = '{"id":"0001","type":"donut","name":"Cake","topping":[{"id":"5001","type":"None"}]}';
const jsonObject = JSON.parse(json);
console.log(jsonObject.topping[0].id); // Outputs: 5001
```
**Check For Understanding:** Components bring together code in an encapsulated, reusable form. The idea behind components is to build functions that take code structures as arguments and return what?

### Iterating over data to build JSON

**Relevance:** In a social media company, there's a feature to generate analytics reports. The data comes in various structures, and your task is to iterate over this data to build well-structured JSON for each user activity report.

**Problem:** Convert an array of JavaScript objects into a JSON string.

**Procedure:**

- Declare a variable with an array of objects.
- Use JSON.stringify() to convert the array into a JSON string.
- Log the JSON string to the console.

**Code:**

```javascript
let users = [{ id: 1, name: 'Alice' }, { id: 2, name: 'Bob' }];
let jsonUsers = JSON.stringify(users);
console.log(jsonUsers);
```
**Check For Understanding:** Components bring together templates in an encapsulated, reusable form. The idea behind components is to build functions that take templates as arguments and return what?

## Sprint Challenge Preview

### Challenge: The `buildLearnerCard` Function

#### Objective

Develop a function named `buildLearnerCard` that dynamically generates a detailed DOM element to showcase a learner's profile card. This card should include not only the learner's full name and favorite programming language but also their bio, a list of skills, and an image.

#### Functionality Requirements

- The `buildLearnerCard` function must accept three arguments:
  - `learner`: An object containing the learner's details (name, bio, favorite language id, skills array, and image URL).
  - `languages`: An array of language objects (each with id and name).
  - `container`: A DOM element to append the generated card to.
- It should create and return a DOM element representing the card, incorporating the learner's full name, bio, favorite programming language, skills, and an image.

#### Conditions

- The card must dynamically display the learner's full name, bio, an image, and the name of their favorite programming language by matching the language id.
- It should also list the learner's skills.
- If the favorite language is not found within the languages array, display 'Language not found'.
- Apply specific CSS classes to style the card, bio, and skills list.

#### Hints

- Start by constructing the main card element with `document.createElement`.
- Iterate through the languages array to match the learner's favorite language.
- Utilize `Array.prototype.map()` to generate the skills list.
- Consider using template literals for cleaner HTML string assembly.
- Address cases where the favorite language id does not match any entries in the languages array.

#### Procedure

1. **Construct the Card:** Initiate a new `div` element to act as the profile card container.
2. **Match the Favorite Language:** Search the languages array for an object matching the learner's favorite language id.
3. **Aggregate Details:** If the favorite language is identified, compile the learner's name, bio, favorite language, skills, and image into the card. Handle the scenario where the language is not found.
4. **Styling and Final Touches:** Assign CSS classes to different elements within the card for styling purposes.
5. **Append to Container:** Insert the completed card into the provided container element.

#### Code Example

```javascript
function buildLearnerCard(learner, languages, container) {
  // Create the card container
  let card = document.createElement('div');
  card.className = 'learner-card';

  // Find the favorite language
  let favLanguage = languages.find(lang => lang.id === learner.favLanguageId) || { name: 'Language not found' };

  // Construct card content
  let skillsList = learner.skills.map(skill => `<li>${skill}</li>`).join('');
  card.innerHTML = `
    <img src="${learner.imageUrl}" alt="${learner.fullName}">
    <h2>${learner.fullName}</h2>
    <p>${learner.bio}</p>
    <strong>Favorite Language:</strong> ${favLanguage.name}
    <ul>${skillsList}</ul>
  `;

  // Append the card to the provided container
  container.appendChild(card);
}
```

## Conclusion

Today's journey into JSON and DOM manipulation has equipped you with essential skills for modern web development. You've learned to parse JSON data, iteratively build elements, and create dynamic, data-driven components. These building blocks will form the foundation of your future projects, enabling you to craft interactive, data-centric web experiences. Remember that the fluidity of web development lies in the harmonious union of structure (JSON) and presentation (DOM). Now, go forth and sculpt the web with your newfound knowledge.