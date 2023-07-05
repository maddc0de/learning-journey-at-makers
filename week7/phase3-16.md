phase3 - 16 Promises - exercise:
> In browser's developer console:
> Initialise a promise by making a fetch request to the URL <https://jsonplaceholder.typicode.com/todos>.
>
> Register a callback to be executed when the response is successfully received, and log the response in the console.
>
> Register a callback to be executed when the request has failed, and log an error message in the console.

NOT REALLY WORKING:

```bash
fetch("https://jsonplaceholder.typicode.com/todos")
.then(response => {
    if (response.ok) {
      return response.json();
    } else {
      throw new Error('Request failed');
    }
  })
  .then(data => {
    console.log('Response:', data);
  })
  .catch(error => {
    console.error('Error:', error.message);
  });
  ```

NOT WORKING TOO async/await:

```bash
async function fetchData() {
  const url = 'https://jsonplaceholder.typicode.com/todos';

  try {
    const response = await fetch(url);

    if (response.ok) {
      const data = await response.json();
      console.log('Response:', data);
    } else {
      throw new Error('Request failed');
    }
  } catch (error) {
    console.error('Error:', error.message);
  }
}

fetchData();
```
