**Lymple**

Welcome to the lympleRequest (lymple) - a lightweight JavaScript library for making GET and POST requests easily and efficiently.

### Introduction

Lymple is an easy-to-use tool for interacting with APIs and web servers directly from your browser. With it, you can asynchronously send and receive data, enabling the building of dynamic and interactive web applications.

### Installation

You can use Lymple by either including the code directly in your JavaScript scripts or by saving it in a separate file and including it in your HTML.

```html
<script src="https://cdn.jsdelivr.net/gh/simplyYan/lympleRequest@main/lymple.js"></script>
```

### Basic Usage

#### GET Requests

To make a GET request, you need to provide the URL of the resource you want to access and a callback function to handle the response.

```javascript
lymple.get('https://api.example.com/data', function(response) {
    console.log(response); // Here you can process the response
});
```

#### POST Requests

To make a POST request, in addition to the URL, you need to provide the data to be sent as a JavaScript object and a callback function to handle the response.

```javascript
var data = { name: 'John', age: 25, city: 'New York' };
lymple.post('https://api.example.com/submit', data, function(response) {
    console.log(response); // Here you can process the response
});
```

### More Details

#### Error Handling

Lymple automatically handles network errors, such as connection failures or unexpected server responses. You can add error handlers to your callback function to deal with these situations.

```javascript
lymple.get('https://api.example.com/data', function(response) {
    console.log(response);
}, function(error) {
    console.error('An error occurred:', error);
});
```

#### Sending Custom Headers

You can send custom headers with your requests, such as authorization or content headers. Simply add an object containing the desired headers as the last parameter.

```javascript
var headers = { 'Authorization': 'Bearer token123' };
lymple.get('https://api.example.com/data', function(response) {
    console.log(response);
}, null, headers);
```

### Conclusion

Lymple is a powerful and versatile tool for handling HTTP communications in the browser. With its simple and easy-to-use design, you can easily integrate it into your projects to interact with APIs and web servers efficiently and reliably.

If you have any questions or suggestions, feel free to contact us!

### Examples

- **GET Request**: Fetching weather data from a weather API.

```javascript
lymple.get('https://api.weatherapi.com/forecast.json?key=YOUR_API_KEY&q=London', function(response) {
    console.log(response);
});
```

- **POST Request**: Sending form data to the server.

```javascript
var data = { name: 'Maria', age: 30, city: 'Rio de Janeiro' };
lymple.post('https://api.example.com/submit', data, function(response) {
    console.log(response);
});
```

- **GENERAL EXAMPLE**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/gh/simplyYan/lympleRequest@main/lymple.js"></script>
</head>
<body>
    <input type="text" name="nome" id="nome" placeholder="Type yout name">
    <button onclick="send()">Send</button>
    <script>
        function send() {
            var nome = document.getElementById("nome").value;
            var data = { name: nome }

            lymple.post('index.php', data, function(response) {
                console.log(data)
                console.log(response);
            }, { 'Content-Type': 'application/json' });
        }
    </script>
</body>
</html>
```

With these examples, you can start using Lymple in your projects and leverage its features to enhance communication between your web application and servers.
