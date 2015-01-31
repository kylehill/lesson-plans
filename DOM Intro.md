## Document Object Model

The **Document Object Model** ("DOM") is a collection of methods, consistent across all modern browsers, that are used to allow the JavaScript code on a page to interact with the page's HTML content. JavaScript code interacts with the DOM via several special variables that are only defined within browsers (and not in node.js).

**Note:** The Document Object Model seems very scary up-front, but eventually clicks (you'll experience an "ah-ha" moment after using it for a while, I promise).

#### `document`

All browsers define a `document` variable, which is an object that, among many other things, contains a many-tiered nested object of all the HTML elements in a page.

Let's use this hypothetical page for our examples:

```html
<html>
    <head>
        <title> Page title </title>
    </head>
    <body>
        <div id="container">
            <h1 class="purple"> Headline text </h1>
            <div class="row">
                <span class="purple"> Some additional text</span>
            </div>
        </div>
    </body>
</html>
```

`document` is the root HTMLElement object and has a `children` property, which is an array that contains one or more HTMLElement objects *that act in a similar way.*

```js
// Prints out an array with 1 node representing the <html> tag
console.log(document.children); 

// Prints out an array with 2 nodes, representing the <head> and <body> tags
console.log(document.children[0].children);
```

`document` has several methods for accessing child nodes.

```js
console.log(document.getElementById("container"));
console.log(document.getElementsByClassName("purple"));
console.log(document.getElementsByTagName("div"));

// Works just like CSS selectors
console.log(document.querySelectorAll("title"));
console.log(document.querySelectorAll(".row"));
console.log(document.querySelectorAll("span.purple"));
```

The retrieval methods are also attached to all retrieved nodes -- if used on a retrieved node, it'll only search for elements that are descendent of that node.

```js
var container = document.getElementById("container");
container.getElementsByClassName("purple");
```

`document` also contains a method for creating new elements dynamically; both `document` and any node retrieved from it contain methods for adding to the page in a specific place.

```js
// Create the element itself - note that it doesn't exist on the page anywhere, only in memory
var spanElement = document.createElement("span");

// Set the text content of the element
spanElement.innerText = "hello, world";

// Find a specific element
var container = document.getElementById("container");

// Append the span as a child of the container
// Only now is it ACTUALLY inserted into the page
container.appendChild(spanElement);
```

#### `window`

In any browser, there's a special variable named `window` that represents the browser itself, and the global context in which code is running. Any globally-defined variable will be attached as a property to the window object.

```js
var foo = { bar: "baz" };

console.log(foo); // { bar: "baz" }
console.log(window.foo); // { bar: "baz" }
console.log(window.foo.bar); // "baz"
console.log(window.bar); // undefined
```

#### `location`

Every page on the web has a URL. (Even if you're just viewing a file from your computer in the browser, it'll fake a URL with the `file:///` prefix.) Information about components of the page's the URL is available in the `location` variable.

For instance, if a user went to the URL:

`https://www.notarealwebsite.com/path/page.html?id=5#index`

```js
console.log(location.host); // "www.notarealwebsite.com"
console.log(location.pathname); // "/path/page.html"
console.log(location.search); // "?id=5"
console.log(location.hash); // "#index"

console.log(location.href); // "https://www.notarealwebsite.com/path/page.html?id=5#index"
```

One way to redirect users to another webpage is to just change the `location.href` value.

```js
location.href = "http://www.google.com";
```


#### Additional Resources


* [CSSTricks - Understanding the DOM](http://css-tricks.com/dom/)
* [Mozilla - Intro to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
* Mozilla - specific documentation
    * [`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
    * [`location`](https://developer.mozilla.org/en-US/docs/Web/API/Location)
    * [`document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)
    * [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/Element)