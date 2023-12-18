# Fetch

Let's connect the frontend application with the backend.

## Materials & Resources

| Material                                                                                         |  Time |
| :----------------------------------------------------------------------------------------------- | ----: |
| [Fetch](https://www.youtube.com/watch?v=tVQgfKqbX3M)                                             |  6:22 |
| [Asynchronous Vs Synchronous Programming](https://www.youtube.com/watch?v=Kpn2ajSa92c)           |  7:33 |
| [JavaScript Fetch with Request and Headers Objects](https://www.youtube.com/watch?v=YJ7ZgGnhN5k) | 16:25 |
| [What are API Keys? Using API Keys](https://www.youtube.com/watch?v=1yFggyk--Zo)                 | 10:47 |
| [How to Use the Giphy API](https://www.youtube.com/watch?v=HRh6zHRwRLo)                          | 15:15 |

### Documentation

| Material                                                                            |    Time |
| :---------------------------------------------------------------------------------- | ------: |
| [Fetch API](https://developer.mozilla.org/en/docs/Web/API/Fetch_API)                | reading |
| [Response.status](https://developer.mozilla.org/en-US/docs/Web/API/Response/status) | reading |

## Material Review

- How to send an HTTP request using `fetch`?
- What does asynchronous execution mean?<!--
  Asynchronous execution means that the code doesn't wait for a method to finish
  running, but immediately continues to the next line. -->
- How to run a code block after the HTTP response arrived?<!--
  Use the `then(cb)` method. -->
  - How to read the JSON body content from the response?<!--
    Use the `res.json()` method. -->
  - How to check if the request was successful?<!--
    Use the `res.ok` property. -->
  - How to handle different status codes? ([status cats](https://http.cat/))<!--
    Check the `res.status` property. -->
- How to send a POST, a PUT or a DELETE request?<!-- See below. -->
  - How to set the JSON body content?<!-- See below. -->
  - How to set request headers?<!-- See below. -->
- What's an API key?<!--
  It's like a password for an API so that only authorized apps can use it. -->
- (Optional) What's a Cross Origin request?<!--
  A request sent to a different origin (domain, scheme, or port) than its own.
  E.g. sending a request to abc.com from cba.com website. -->

## Workshop

Please note that hunting for API keys is part of the exercises.

### Example

```javascript
fetch('https://sheetsu.com/apis/v1.0/7654fbe24554') // Also try http://444.hu/feed
  .then(response => response.json())
  .then(body => {
    console.log(body);
    // do something useful with the contents of the body
  });
```

### Example with a POST request

```javascript
fetch('https://example.com/profile', {
  method: 'POST', // or 'PUT', or 'DELETE'
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(data),
})
.then(response => response.json())
.then(data => {
  console.log('Success:', data);
})
.catch(error => {
  console.error('Error:', error);
});
```

Design of user interface is not important, don't spend more than 5 minutes
making it look pretty.

### Tasks

- [Giphy API](giphy-api/README.md)
- [New York Times API](new-york-times/README.md)
- [Star Wars](star-wars/README.md)
- [Get Position](get-position/README.md)
