# Lesson 3 - Web API and JSON

In this lesson, we'll be looking at Web APIs and how to use them. Almost all modern websites use web APIs to send data to your browser.

Most (not all) APIs return data in a structured format called JSON, which is designed to be readable both for humans and for computers.

### 0. Client-Server Architecture

Client-Server architecture describes how applications talk to each other over the web.

![Client Server Architecture](images/client-server.png)

Examples of clients: an Internet Browser (Chrome, Firefox, etc.), Slack, Python script, any others?

Servers are typically things we as consumers don't see. A server could be a computer in a remote datacenter, or it could even be a computer on your local network!

In client-server architecture, the client "asks" the server for data. It does this by giving the server a path to the resource it wants. What does this remind you of?

When someone goes to `google.com`, our browser (the client) is asking a Google server for all the HTML, CSS, Javascript, etc. that our web browser needs to render the Google website.

When a client asks for data from a server, we call that the `request`.

When the server gives data back to the client, we call that the `response`.

What do you think are advantages of client-server architecture?

### 1. What are Web APIs?

Web APIs are ways of requesting data from a server. Most modern web applications use web APIs to send data from the "backend" (server) to the "frontend" (client).

Let's explore https://vaccinefinder.org/, and see if we can find out whether or not it's using a Web API.

### 2. Request Data from a Web API in Python

(You can do this in a new Jupyter notebook)

To do this, we are going to leverage a library called [`requests`](https://requests.readthedocs.io/en/master/).

You can install `requests` using `pip`.

Let's try making a request to fetch some data from the Vaccine finder Web API!

```
import requests

req = requests.get('...')

req.text
```

### 3. What is JSON?

Most Web APIs will return data in a format called JSON (another data format that is common is CSV).

JSON data is just text that is structured in a special way (kind of like a code file).

JSON looks like very similar to a Python dictionary. It is composed of an "Object" and "key-value" pairs.

This is a very simple JSON "Object":

```json
{
  "key": "value"
}
```

Keys must *always* be strings (surrounded by quotes).

Values can be Strings, numbers, lists, or nested objects. Here's an example of each:

```json
{
  "string": "string",
  "number": 1.0,
  "list": [
    "string",
    2.0
  ],
  "object": {
    "nested": "string"
  }
}
```

*Note: JSON objects don't care about indentations or spaces. In order to save bandwidth and keep costs low, most Web APIs will remove all the extra spacing and indentation!*
