# WEEK 7 JavaScript Web Application

## Contents

---
---

* [Weekly Goals](#weekly-goals)
* [Daily Goals](#daily-goals)
* [Reflections](#reflections)
* [Useful Tips](#useful-tips)

---

## Weekly Goals

* [x] To be able to test-drive a simple Javascript program running in a web browser, using modern JS build tools.
* [x] To be able to use the DOM API to manipulate the web page structure and content.
* [x] To be able to use `fetch` to send HTTP requests to a remote server.
* [x] To be able to keep a minimal code structure for separation of concerns on a client-side JavaScript application.

### Plan

* Work through the different steps in sequence.
* Familiarise and use Postman tool to call HTTP APIs

### Evidence

* [Notes App](https://github.com/maddc0de/notes-app)
* [JavaScript Web Apps](https://github.com/maddc0de/javascript-web-apps)

---

## Daily Goals

### 2nd May

* [x] To be able to test-drive a Javascript "Model" class to hold the program's state
* [x] To be able to use JavaScript to dynamically change the page content

### 3rd May

* [x] To be able to write a test to check the updates to the web page.
* [x] To be able to test-drive a feature for a frontend web application.
* [x] TO be able to change the webpage dynamically in response to a user event (using JavScript to handle an event)

### 4th May

* [x] To be able to use JavaScript to read the value from a form input (with .value) and handle a click
* [x] To be able to modify the page in reaction to user interaction.
* [x] To be able to use the response data received by `fetch` to modify the web page. (with `fetch` function used to make an HTTP request)

### 5th May

* [x] To be able to handle network errors from `fetch` using `.catch()`

---

## Reflections

What I have learnt:

* Frontend, single page web apps
* Events and event handlers
* Manipulating the Document Object Model (DOM)
* Improvement on isolating my tests

Using JavaScript to dynamically change the page content, I have gained a solid understanding of managing the program's state and manipulating the DOM. Additionally, I was able to write tests to ensure proper updates to the web page and test-drive features for a frontend web application. This experience has strengthened my grasp of the Model-View-Client design pattern and its implementation which is somewhat similar to Model-View-Controller Design pattern. I can confidently say that I have gained a strong understanding of the separation of concerns principle in programming. By adhering to this principle and implementing the MVC design pattern, I have achieved clean code organisation and maintainability.

Working with form inputs and user interactions, such as reading values from input fields and handling clicks, allowed me to create dynamic responses to user actions. Moreover, utilizing the fetch function for making HTTP requests and handling the response data has given me valuable insights into working with network requests and modifying web pages accordingly.

Looking ahead, there are a few areas where I could further improve. Firstly, I could enhance my error handling for network requests by effectively utilising the .catch() method. This would ensure better handling of network errors and provide a better user experience. Additionally, I could focus on writing more comprehensive tests to cover a wider range of scenarios and edge cases. This would contribute to the robustness and reliability of my code.

## Useful Tips

* `console.log` outputs is printed to the browser's developer console. There is a shortcut to open it in Chrome on Mac: `option`+`command`+`J`

* **Developers console's Network** tab can be used to inspect HTTP requests (and responses) sent (and received) by the browser - can use `fetch` to send HTTP requests (useful to debug HTTP request made by `fetch`)

* [manipulating the dom and JS](https://github.com/makersacademy/javascript-web-applications/blob/main/pills/manipulating_dom_with_javascript.md)

* **steps in writing a test to check updates to the webpage using DOM and JS**

> 1. Arrange
> set document.body.innerHTML to have same content of the "real" webpage
> `document.body.innerHTML = fs.readFileSync("./index.html");`
> instantiate the view class
> `const view = new View();`
>
> 2. Act
> call any method that modifies the page for example:
>`view.addParagraph("new paragraph");`
>
> 3. Assert - what can be verify? what the page should contain?
> expect test example:
> `expect(document.querySelectorAll("p").length).toBe(2);`

* Model-View-Controller Design Pattern
> Model class - holds the program state or data
> View class - responsible for displaying the data and handling user interactions. It interacts with the Model to retrieve data and updates the page accordingly. (using ie `document.querySelector` and other DOM methods)
> Controller class - acts as an intermediary between the Model and the View. It receives user input from the View, processes that input, and updates the Model accordingly. It also updates the View to reflect any changes in the Model. Essentially, the Controller handles the logic and coordination between the Model and the View. It ensures that the Model and View remain separate and independent, facilitating better code organization, maintainability, and reusability.

* [Handle failed HTTP responses with fetch()](https://www.tjvantoll.com/2015/09/13/fetch-and-errors/)