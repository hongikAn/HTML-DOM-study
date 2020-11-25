# 2. HTML DOM Methods

Created By: 홍익 안
Last Edited: Nov 25, 2020 7:22 PM

# The DOM Programming Interface

The HTML DOM can be accessed with JavaScript (and with other programming languages).

In the DOM, all HTML elements are defined as **objects**.

The programming interface is the properties and methods of each object.

A **property** is a value that you can get or set (like changing the content of an HTML element).

A **method** is an action you can do (like add or deleting an HTML element).

# Example

The following example changes the content (the `innerHTML`) of the `<p>` element with `id="demo"`:

```html
<html>
<body>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>

</body>
</html>
```

getElementById is a `method`, while innerHTML is a `property`.

# The getElementById Method

The most common way to access an HTML element is to use the `id` of the element.

In the example above the `getElementById` method used `id="demo"` to find the element.

# The innerHTML Property

The easiest way to get the content of an element is by using the `innerHTML` property.

The `innerHTML` property is useful for getting or replacing the content of HTML elements.

The innerHTML property can be used to get or change any HTML element, including <html> and <body>.

출처:

[W3Schools Online Web Tutorials](https://www.w3schools.com/)

[W3Schools JS Exercise](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_dom_html1)