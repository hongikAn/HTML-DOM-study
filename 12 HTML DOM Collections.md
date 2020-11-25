# 12. HTML DOM Collections

Created By: 홍익 안
Last Edited: Nov 25, 2020 8:36 PM

# The HTMLCollection Object

The `getElementsByTagName()` method returns an `HTMLCollection` object.

An `HTMLCollection` object is an array-like list (collection) of HTML elements.

The following code selects all `<p>` elements in a document:

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript HTML DOM</h2>

<p>Hello World!</p>

<p>Hello Norway!</p>

<p id="demo"></p>

<script>
var myCollection = document.getElementsByTagName("p");
document.getElementById("demo").innerHTML =
"The innerHTML of the second paragraph is: " +
myCollection[1].innerHTML;
</script>

</body>
</html>
```

The length property defines the number of elements in an HTMLCollection:

```jsx
var myCollection = document.getElementsByTagName("p");
document.getElementById("demo").innerHTML = myCollection.length;
```

**The length property is useful when you want to loop through the elements in a collection:**

```jsx
var myCollection = document.getElementsByTagName("p");
var i;
for (i = 0; i < myCollection.length; i++) {
  myCollection[i].style.color = "red";
}
```

[Tryit Editor v3.6](https://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_htmlcollection_loop)

An HTMLCollection is NOT an array!

An HTMLCollection may look like an array, but it is not.

You can loop through the list and refer to the elements with a number (just like an array).

However, you cannot use array methods like valueOf(), pop(), push(), or join() on an HTMLCollection.