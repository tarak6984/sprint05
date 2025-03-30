# Asynchronous JavaScript and Promises

## Introduction

Welcome to our journey through the land of Asynchronous JavaScript and Promises! Today, we'll embark on an adventure to conquer time and sequence in code. Imagine submitting an online food order; you don't stand frozen, waiting for a response. Instead, you go on with life, and when the order is ready, you're notified. Similarly, asynchronous code allows JavaScript to handle tasks that take time, like data fetching, without stopping the world. Get ready to master the art of asynchronous operations, promises, thenables, and async/await, all to write efficient, non-blocking JavaScript code.
## Core Competencies

1. Using functions that return promises
2. Handling success with then
3. Handling failure with catch
4. Using async await for more readable code
## Coding Problems
### Using functions that return promises

**Relevance:** Imagine you're working for a meteorology website, where users expect to receive live weather updates. You'd need to retrieve data from remote servers without making them wait or blocking other website functions. Asynchronous functions that return promises are what make this smooth experience possible.

**Problem:** How can you effectively use functions that return promises to handle async operations?

**Procedure:**

- Understand the function that returns a promise and its purpose.
- Initiate a call to the asynchronous function and handle its completion with the 'then' method.
- Provide callback functions for both fulfillment and rejection to handle the results of the promise.
- Chain multiple 'then' calls if necessary to handle complex asynchronous sequences.
- Always include a 'catch' at the end of your promise chains to handle any errors that may occur.

**Code:**

```javascript
// Example function returning a promise
function getWeatherUpdate(city) {
  return new Promise((resolve, reject) => {
    // Simulated async API call to get weather data
    setTimeout(() => {
      const success = Math.random() > 0.5; // Simulate 50% chance of success
      if (success) resolve(`Weather data for ${city}`);
      else reject('Weather data unavailable');
    }, 2000);
  });
}

// Usage
getWeatherUpdate('San Francisco')
  .then(data => console.log(data))
  .catch(error => console.error(error));
```
**Check For Understanding:** What are the states a promise can be in, and what state represents a successful operation that can be handled with the 'then' method?

### Handling success with then

**Relevance:** You're developing an application that processes user-generated photos. When a user uploads a photo, it must be asynchronously sent to the server for storage while the user continues to interact with the app. The successful storage of the photo should trigger a 'Photo uploaded!' message.

**Problem:** How can you handle the success notification of an asynchronous photo upload operation?

**Procedure:**

- Invoke the asynchronous function to start the photo upload.
- Use the 'then' method to define what to do when the upload completes successfully.
- Provide appropriate UI feedback in the 'then' handler, such as displaying a 'Photo uploaded!' message.
- Ensure proper error handling with the 'catch' method in case the upload fails.

**Code:**

```javascript
// Example async function to upload a photo
function uploadPhoto(photo) {
  // Returns a promise
  return new Promise((resolve, reject) => {
    // Simulate async photo upload
    setTimeout(() => {
      const success = Math.random() > 0.3; // Simulate 70% chance of success
      if (success) resolve('Photo uploaded!');
      else reject('Upload failed');
    }, 1000);
  });
}

// Usage
uploadPhoto('userPhoto.png')
  .then(message => console.log(message))
  .catch(error => console.error(error));
```
**Check For Understanding:** What is the role of the 'then' method in a promise-based asynchronous operation?

### Handling failure with catch

**Relevance:** While building a user authentication system, you need to handle cases where login attempts fail due to incorrect credentials. This not only involves asynchronous operations but also informing the user of the failure non-intrusively.

**Problem:** What's the approach for handling rejection from a promise that checks user credentials?

**Procedure:**

- Call the asynchronous function that initiates the user login process.
- Attach a 'then' method to handle successful authentication and update the UI accordingly.
- Implement a 'catch' method for the promise to handle login failures and alert the user.
- Ensure that 'catch' provides helpful feedback for the user to correct their credentials.

**Code:**

```javascript
// Example async function to login user
function login(username, password) {
  return new Promise((resolve, reject) => {
    // Simulated check against a user database
    setTimeout(() => {
      const isCredentialsValid = username === 'user' && password === 'pass';
      if (isCredentialsValid) resolve('Login successful');
      else reject('Invalid credentials');
    }, 1000);
  });
}

// Usage
login('user', 'pass123')
  .then(message => console.log(message))
  .catch(error => console.error(error));
```
**Check For Understanding:** How does the 'catch' method contribute to a better user experience in handling asynchronous operations?

### Using async await for more readable code

**Relevance:** Imagine you're working on an application for a library. You need to asynchronously fetch book details and then update the UI once the data is received. Using async/await can significantly improve code readability and error handling.

**Problem:** How can async/await syntax make complex asynchronous code easier to read and maintain?

**Procedure:**

- Mark your function with the 'async' keyword to define an asynchronous function.
- Inside the function, use 'await' to pause the function execution until the promise resolves.
- Handle exceptions with try/catch blocks to catch any errors that occur during the await.
- After the promise resolves, write synchronous-looking code to process the results.

**Code:**

```javascript
// Example async function to fetch book details
async function getBookDetails(bookId) {
  try {
    const response = await fetch(`api/books/${bookId}`);
    const bookDetails = await response.json();
    console.log(bookDetails);
    // Update the UI with book details
  } catch (error) {
    console.error('Failed to fetch book details:', error);
  }
}

// Usage
ggetBookDetails(42);
```
**Check For Understanding:** Explain how try/catch blocks are used in conjunction with async/await to handle errors.

## Sprint Challenge Preview

### Challenge: Asynchronous City Information Fetcher

**Objective:** Enhance a dropdown event listener to perform an asynchronous fetch for detailed city information upon selection.

**Functionality:**
- Upon selecting a city from the dropdown, the code should asynchronously fetch detailed information about the city (e.g., population, description) and log this information to the console.

**Conditions:**
- The asynchronous operation should be handled using `async/await`.
- The code should gracefully handle errors such as a failed fetch request.
- Assume the existence of a mock function `fetchCityInfo(cityName)` that returns a Promise with the city's information.

**Hints:**
- Incorporate `try/catch` blocks to manage errors in the asynchronous code.
- Use the `change` event on the dropdown to trigger the asynchronous fetch operation.
- Ensure the `fetchCityInfo` function is called with the name of the selected city.

**Procedure:**
1. Assign the dropdown element to a variable.
2. Add a 'change' event listener to the dropdown element that calls an asynchronous function.
3. Within the asynchronous function, use `await` to call `fetchCityInfo` with the selected city's name.
4. Log the fetched city information to the console.
5. Implement error handling to catch and log any errors that occur during the fetch operation.

**Enhanced Code Example:**

```javascript
// Mock async function to simulate fetching city information
async function fetchCityInfo(cityName) {
  // Simulate network request delay
  await new Promise(resolve => setTimeout(resolve, 1000));
  // Simulate returning city information
  return {
    name: cityName,
    population: '4 million',
    description: 'A vibrant city with a rich history.'
  };
}

// Example code for the enhanced event listener challenge
const dropdown = document.getElementById('citySelector');
dropdown.addEventListener('change', async function(event) {
  const selectedCity = event.target.value;
  
  try {
    const cityInfo = await fetchCityInfo(selectedCity);
    console.log(`Selected city: ${cityInfo.name}, Population: ${cityInfo.population}, Description: ${cityInfo.description}`);
  } catch (error) {
    console.error('Failed to fetch city information:', error);
  }
});
```

## Conclusion

As we wrap up today's session, reflect on the incredible tools at your disposal with Asynchronous JavaScript. You've learned to create functions that return promises to handle data fetching, user uploads, and much more without disrupting the app flow. You now know how to handle success with 'then', gracefully manage failure with 'catch', and write cleaner code with async/await. With these skills, you're well on your way to developing dynamic, responsive applications that users will love. Remember, the beauty of coding lies in its power to turn complex tasks into simple, elegant solutions.