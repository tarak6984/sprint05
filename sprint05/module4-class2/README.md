# HTTP Communication and Fetching Data and Building DOM Using Fetched Data

## Introduction

Welcome to our dynamic journey towards mastering the fundamentals of HTTP communication and the art of manipulating the Document Object Model (DOM) with data fetched from the web. Through this lesson, students will explore the essentials of using HTTP methods, fetching data with JavaScript, and weaving that data into the fabric of web pages to create responsive and interactive user experiences. Envision being a developer tasked with incorporating live weather updates on a news website; this lesson gears you up for that real-world application, ensuring that the skills acquired are not merely theoretical but also practically invaluable.
## Core Competencies

1. Using the HTTP protocol
2. Using HTTP methods
3. Hitting an API with Postman
4. Hitting an API with fetch
5. Hitting and API with Axios
6. Handling spinners and failures
7. Iterating over fetched data to build DOM
## Coding Problems
### Using HTTP methods

**Relevance:** Imagine you are working on a dashboard which aggregates user data for the customer support team at your company. At any given moment, you might need to retrieve, update, or register user profiles as support tickets fluctuate. Understanding HTTP methods is crucial in accessing and manipulating this data effectively.

**Problem:** Perform a GET request using fetch to retrieve all user data and handle the response by presenting it in a structured format on the console.

**Procedure:**

- Set up a fetch request using the URL provided for user data.
- Ensure the method is set to GET which is the default method for fetch.
- Chain a `.then()` method to parse the response as JSON.
- Using a second `.then()` method, handle the parsed data and display the formatted user information on the console.
- Implement error handling with a `.catch()` to display any potential errors encountered during the fetching process.

**Code:**

```javascript
fetch('https://webapis.bloomtechdev.com/users')
  .then(response => response.json())
  .then(users => console.table(users))
  .catch(error => console.error('Error fetching users:', error))
```
**Check For Understanding:** Why would you use a spinner in your application?

### Hitting an API with fetch

**Relevance:** Envision a scenario where you need to quickly develop a feature that requires pulling data from a third-party service, for instance, displaying a live list of planetary information in a museum exhibit. Knowing how to retrieve this data using fetch is an essential skill for this task.

**Problem:** Use fetch to make a request to an API that returns a list of planets and log the response to the console.

**Procedure:**

- Define the API endpoint URL as a string variable.
- Use the fetch function to make a GET request to the API endpoint.
- Handle the fetch promise by chaining a `.then()` that converts the response to JSON.
- Chain another `.then()` to process and console log the JSON data.
- Implement error handling with a `.catch()` method.

**Code:**

```javascript
const planetsURL = 'https://webapis.bloomtechdev.com/planets'
fetch(planetsURL)
  .then(response => response.json())
  .then(planets => console.log(planets))
  .catch(error => console.error('Error:', error))
```
**Check For Understanding:** How do you import the fetch library into your application?

### Hitting and API with Axios

**Relevance:** You're a developer at a startup focusing on educational tools for schools. The application you're building will display information about planets in our solar system for students. You'll need to fetch data from an API using Axios and render it dynamically.

**Problem:** Utilize Axios to make a GET request for Pluto's data and output a message whether it considers Pluto a planet.

**Procedure:**

- Import Axios into your application or include it using a script tag.
- Assign the base URL of the API to a variable.
- Use Axios' get method with the appropriate URL concatenated with Pluto's planet ID.
- In the promise's .then() method, check the returned data and log a message regarding Pluto’s planetary status.
- Handle errors using the .catch() method in the promise.

**Code:**

```javascript
const baseURL = 'https://webapis.bloomtechdev.com/planets/'
axios.get(baseURL + '9')
  .then(response => {
    console.log(`I am not sure if ${response.data.name} is a planet!`)
  })
  .catch(error => console.error('Error:', error));
```
**Check For Understanding:** One advantage of using async/await over then/catch is:

### Handling spinners and failures

**Relevance:** You are developing a live-tracking feature for a logistics app, where users need to see updates without refreshing the page. Implementing a spinner shows the users that new data is being loaded, and handling failures properly can greatly improve user experience in case of errors.

**Problem:** Implement a spinner to indicate data loading for a network request and handle any failures gracefully.

**Procedure:**

- Select and store the spinner element in a variable and set its display style to 'block' to make it visible.
- Write an Axios GET request to the API and in its .then() method, set the spinner's display style to 'none'.
- In the success handler, perform actions to render the received data.
- Define the error handling logic in the .catch() method, which also hides the spinner and displays an error message.

**Code:**

```javascript
const spinner = document.querySelector('#spinner');
spinner.style.display = 'block';
axios.get('https://webapis.bloomtechdev.com/data')
  .then(response => {
    // Data manipulation and DOM updates here
    spinner.style.display = 'none';
  })
  .catch(error => {
    console.error('Fetch error:', error);
    spinner.style.display = 'none';
  });
```
**Check For Understanding:** Why would you use a spinner in your application?

### Iterating over fetched data to build DOM

**Relevance:** You're assigned to create an interactive feature for a learning application where students can explore facts about each planet. You need to fetch this data and present it in a compelling visual format.

**Problem:** Fetch data for all the planets and use the data to build DOM elements to display each planet's details.

**Procedure:**

- Use Axios to make a GET request to the planets' API endpoint.
- Handle the promise to iterate over the fetched data upon successful response.
- Within the iteration, create new DOM elements for each planet's details.
- Append the newly created DOM elements to the parent container in your application's front-end.
- Implement catch logic within the promise to handle any errors by logging them to the console.

**Code:**

```javascript
axios.get('https://webapis.bloomtechdev.com/planets')
  .then(response => {
    response.data.forEach(planet => {
      // Create DOM elements and set their text content
      // Append elements to the DOM
    });
  })
  .catch(error => console.error('Error:', error));
```
**Check For Understanding:** How do you import the fetch library into your application?

## Sprint Challenge Preview

### Challenge 1: The Weather Reporter

**Objective:** Perform an Axios GET request to a weather API to fetch and display weather data for a selected city.

**Functionality:**
- The weather API endpoint needs to be constructed dynamically based on the selected city.
- Use Axios to perform the GET request.
- Handle the promise returned by Axios, displaying the fetched weather data to the user.
- Implement error handling to catch any issues with the API request.

**Conditions:**
- The city is determined by the value of a select element in the HTML document.
- The API URL should be adjusted accordingly to include the selected city's data.
- On successful response, the fetched weather data should be displayed on the page.
- Handle errors by logging them to the console or displaying an error message to the user.

**Hints:**
- Start by attaching an event listener to the select element to capture the selected city.
- Formulate a strategy to construct the API endpoint dynamically using template strings or string concatenation.
- Familiarize yourself with Axios' error handling using .catch().

**Procedure:**
- Identify the HTML element that triggers the weather data fetching.
- Attach an event listener to the element and obtain the selected city from the event's target value.
- Construct the API endpoint URL dynamically using the selected city's value.
- Invoke Axios' GET method using the composed URL to initiate the weather data request.
- In the .then() method, update the DOM with the new weather data.
- Utilize the .catch() method to handle any errors encountered during the request.

**Code:**

```javascript
const selectElement = document.querySelector('#city-selector');
selectElement.addEventListener('change', function(event) {
  const city = event.target.value;
  const weatherAPI = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=your_api_key`;
  document.querySelector('#spinner').style.display = 'initial';
  axios.get(weatherAPI)
    .then(response => {
      // Update DOM with weather data
      document.querySelector('#spinner').style.display = 'none';
    })
    .catch(error => {
      console.error('Error fetching weather:', error);
      document.querySelector('#spinner').style.display = 'none';
    });
});
```

## Conclusion

Throughout this lesson, you've experienced the potency of JavaScript for web-based HTTP communications, the simplicity of fetching data using fetch and Axios, and the magic of dynamically rendering that data into the DOM. Your newfound skill set equips you to elegantly craft web interfaces that not only consume and display data from various sources but also interact with users in a meaningful way. The power and versatility found in these techniques are the keystones for developing advanced, user-friendly web applications.