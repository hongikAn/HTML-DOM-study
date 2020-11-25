# 4. HTML DOM Elements

Created By: 홍익 안
Last Edited: Nov 25, 2020 6:36 PM

# Finding HTML Elements

Often, with JavaScript, you want to manipulate HTML elements.

To do so, you have to find the elements first. There are several ways to do this:

- Finding HTML elements by id
- Finding HTML elements by tag name
- Finding HTML elements by class name
- Finding HTML elements by CSS selectors
- Finding HTML elements by HTML object collections

# Finding HTML Element by Id

```html
<!DOCTYPE html>
<html>
<body>

<h2>Finding HTML Elements by Id</h2>

<p id="intro">Hello World!</p>
<p>This example demonstrates the <b>getElementsById</b> method.</p>

<p id="demo"></p>

<script>
var myElement = document.getElementById("intro");
document.getElementById("demo").innerHTML = 
"The text from the intro paragraph is " + myElement.innerHTML;
</script>

</body>
</html>
```

If the element is found, the method will return the element as an object (in myElement).

If the element is not found, myElement will contain `null`.

# Finding HTML Elements by Tag Name

```html
<!DOCTYPE html>
<html>
<body>

<h2>Finding HTML Elements by Tag Name</h2>

<div id="main">
<p>The DOM is very useful.</p>
<p>This example demonstrates the <b>getElementsByTagName</b> method.</p>
</div>

<p id="demo"></p>

<script>
var x = document.getElementById("main");
var y = x.getElementsByTagName("p");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) inside "main" is: ' + y[0].innerHTML;
</script>

</body>
</html>
```

# Finding HTML Elements by Class Name

If you want to find all HTML elements with the same class name, use `getElementsByClassName()`.

This example returns a list of all elements with `class="intro"`.

```html
<!DOCTYPE html>
<html>
<body>

<h2>Finding HTML Elements by Class Name</h2>

<p>Hello World!</p>

<p class="intro">The DOM is very useful.</p>
<p class="intro">This example demonstrates the <b>getElementsByClassName</b> method.</p>

<p id="demo"></p>

<script>
var x = document.getElementsByClassName("intro");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) with class="intro": ' + x[0].innerHTML;
</script>

</body>
</html>
```

# Finding HTML Elements by CSS Selectors

If you want to find all HTML elements that match a specified CSS selector (id, class names, types, attributes, values of attributes, etc), use the `querySelectorAll()` method.

This example returns a list of all `<p>` elements with `class="intro"`.

```html
<!DOCTYPE html>
<html>
<body>

<h2>Finding HTML Elements by Query Selector</h2>

<p>Hello World!</p>

<p class="intro">The DOM is very useful.</p>
<p class="intro">This example demonstrates the <b>querySelectorAll</b> method.</p>

<p id="demo"></p>

<script>
var x = document.querySelectorAll("p.intro");
document.getElementById("demo").innerHTML = 
'The first paragraph (index 0) with class="intro": ' + x[0].innerHTML;
</script>

</body>
</html>
```

# Finding HTML Elements by HTML Object Collections

```html
<!DOCTYPE html>
<html>
<body>

<h2>Finding HTML Elements Using document.forms</h2>

<form id="frm1" action="/action_page.php">
  First name: <input type="text" name="fname" value="Donald"><br>
  Last name: <input type="text" name="lname" value="Duck"><br><br>
  <input type="submit" value="Submit">
</form> 

<p>Click "Try it" to display the value of each element in the form.</p>

<button onclick="myFunction()">Try it</button>

<p id="demo"></p>

<script>
function myFunction() {
  var x = document.forms["frm1"];
  var text = "";
  var i;
  for (i = 0; i < x.length ;i++) {
    text += x.elements[i].value + "<br>";
  }
  document.getElementById("demo").innerHTML = text;
}
</script>

</body>
</html>
```

The following HTML objects (and object collections) are also accessible:

- [document.anchors](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_anchors)
- [document.body](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_body)
- [document.documentElement](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_element)
- [document.embeds](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_embeds)
- [document.forms](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_forms)
- [document.head](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_head)
- [document.images](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_images)
- [document.links](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_links)
- [document.scripts](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_scripts)
- [document.title](https://www.w3schools.com/js/tryit.asp?filename=tryjs_doc_title)