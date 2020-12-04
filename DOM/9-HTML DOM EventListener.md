# 9. HTML DOM EventListener

Created By: 홍익 안
Last Edited: Nov 25, 2020 7:21 PM

# The addEventListener() method

The `addEventListener()` method attaches an event handler to the specified element.

The `addEventListener()` method attaches an event handler to an element without overwriting existing event handlers.

You can add many event handlers to one element.

You can add many event handlers of the same type to one element, i.e two "click" events.

You can add event listeners to any DOM object not only HTML elements. i.e the window object.

The `addEventListener()` method makes it easier to control how the event reacts to bubbling.

When using the `addEventListener()` method, the JavaScript is separated from the HTML markup, for better readability and allows you to add event listeners even when you do not control the HTML markup.

You can easily remove an event listener by using the `removeEventListener()` method.

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>JavaScript addEventListener()</h2>

    <p>
      This example uses the addEventListener() method to attach a click event to
      a button.
    </p>

    <button id="myBtn">Try it</button>

    <p id="demo"></p>

    <script>
      document.getElementById("myBtn").addEventListener("click", displayDate);

      function displayDate() {
        document.getElementById("demo").innerHTML = Date();
      }
    </script>
  </body>
</html>
```

# Syntax

```jsx
element.addEventListener(event, function, useCapture);
```

The first parameter is the type of the event (like "`click`" or "`mousedown`" or any other [HTML DOM Event](https://www.w3schools.com/jsref/dom_obj_event.asp).)

The second parameter is the function we want to call when the event occurs.

The third parameter is a boolean value specifying whether to use event bubbling or event capturing. This parameter is optional.

Note that you don't use the "on" prefix for the event; use "click" instead of "onclick".

# Add an Event Handler to an Element

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>JavaScript addEventListener()</h2>

    <p>
      This example uses the addEventListener() method to execute a function when
      a user clicks on a button.
    </p>

    <button id="myBtn">Try it</button>

    <script>
      document.getElementById("myBtn").addEventListener("click", myFunction);

      function myFunction() {
        alert("Hello World!");
      }
    </script>
  </body>
</html>
```

# Add Many Event Handlers to the Same Element

The `addEventListener()` method allows you to add many events to the same element, without overwriting existing events:

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>JavaScript addEventListener()</h2>

    <p>
      This example uses the addEventListener() method to add many events on the
      same button.
    </p>

    <button id="myBtn">Try it</button>

    <p id="demo"></p>

    <script>
      var x = document.getElementById("myBtn");
      x.addEventListener("mouseover", myFunction);
      x.addEventListener("click", mySecondFunction);
      x.addEventListener("mouseout", myThirdFunction);

      function myFunction() {
        document.getElementById("demo").innerHTML += "Moused over!<br>";
      }

      function mySecondFunction() {
        document.getElementById("demo").innerHTML += "Clicked!<br>";
      }

      function myThirdFunction() {
        document.getElementById("demo").innerHTML += "Moused out!<br>";
      }
    </script>
  </body>
</html>
```

# Add an Event Handler to the window Object

The `addEventListener()` method allows you to add event listeners on any HTML DOM object such as HTML elements, the HTML document, the window object, or other objects that support events, like the `xmlHttpRequest` object.

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>JavaScript addEventListener()</h2>

    <p>This example uses the addEventListener() method on the window object.</p>

    <p>
      Try resizing this browser window to trigger the "resize" event handler.
    </p>

    <p id="demo"></p>

    <script>
      window.addEventListener("resize", function () {
        document.getElementById("demo").innerHTML = Math.random();
      });
    </script>
  </body>
</html>
```

# Passing Parameters

When passing parameter values, use an "anonymous function" that calls the specified function with the parameters:

```html
<!DOCTYPE html>
<html>
  <body>
    <h2>JavaScript addEventListener()</h2>

    <p>
      This example demonstrates how to pass parameter values when using the
      addEventListener() method.
    </p>

    <p>Click the button to perform a calculation.</p>

    <button id="myBtn">Try it</button>

    <p id="demo"></p>

    <script>
      var p1 = 5;
      var p2 = 7;

      document.getElementById("myBtn").addEventListener("click", function () {
        myFunction(p1, p2);
      });

      function myFunction(a, b) {
        var result = a * b;
        document.getElementById("demo").innerHTML = result;
      }
    </script>
  </body>
</html>
```

# Event Bubbling or Event Capturing?

There are two ways of event propagation in the HTML DOM, bubbling and capturing.

Event propagation is a way of defining the element order when an event occurs. If you have a <p> element inside a <div> element, and the user clicks on the <p> element, which element's "click" event should be handled first?

In *bubbling* the inner most element's event is handled first and then the outer: the <p> element's click event is handled first, then the <div> element's click event.

In *capturing* the outer most element's event is handled first and then the inner: the <div> element's click event will be handled first, then the <p> element's click event.

With the addEventListener() method you can specify the propagation type by using the "useCapture" parameter:

`addEventListener(*event*, *function*, *useCapture*);`

The default value is false, which will use the bubbling propagation, when the value is set to true, the event uses the capturing propagation.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      #myDiv1,
      #myDiv2 {
        background-color: coral;
        padding: 50px;
      }

      #myP1,
      #myP2 {
        background-color: white;
        font-size: 20px;
        border: 1px solid;
        padding: 20px;
      }
    </style>
    <meta content="text/html; charset=utf-8" http-equiv="Content-Type" />
  </head>
  <body>
    <h2>JavaScript addEventListener()</h2>

    <div id="myDiv1">
      <h2>Bubbling:</h2>
      <p id="myP1">Click me!</p>
    </div>
    <br />

    <div id="myDiv2">
      <h2>Capturing:</h2>
      <p id="myP2">Click me!</p>
    </div>

    <script>
      document.getElementById("myP1").addEventListener(
        "click",
        function () {
          alert("You clicked the white element!");
        },
        false
      );

      document.getElementById("myDiv1").addEventListener(
        "click",
        function () {
          alert("You clicked the orange element!");
        },
        false
      );

      document.getElementById("myP2").addEventListener(
        "click",
        function () {
          alert("You clicked the white element!");
        },
        true
      );

      document.getElementById("myDiv2").addEventListener(
        "click",
        function () {
          alert("You clicked the orange element!");
        },
        true
      );
    </script>
  </body>
</html>
```

# The removeEventListener() method

The `removeEventListener()` method removes event handlers that have been attached with the addEventListener() method:

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      #myDIV {
        background-color: coral;
        border: 1px solid;
        padding: 50px;
        color: white;
        font-size: 20px;
      }
    </style>
  </head>
  <body>
    <h2>JavaScript removeEventListener()</h2>

    <div id="myDIV">
      <p>
        This div element has an onmousemove event handler that displays a random
        number every time you move your mouse inside this orange field.
      </p>
      <p>Click the button to remove the div's event handler.</p>
      <button onclick="removeHandler()" id="myBtn">Remove</button>
    </div>

    <p id="demo"></p>

    <script>
      document
        .getElementById("myDIV")
        .addEventListener("mousemove", myFunction);

      function myFunction() {
        document.getElementById("demo").innerHTML = Math.random();
      }

      function removeHandler() {
        document
          .getElementById("myDIV")
          .removeEventListener("mousemove", myFunction);
      }
    </script>
  </body>
</html>
```
