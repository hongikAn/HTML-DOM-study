# 13. HTML DOM Node Lists

Created By: 홍익 안
Last Edited: Nov 25, 2020 8:36 PM

# The HTML DOM NodeList Object

A `NodeList` object is a list (collection) of nodes extracted from a document.

A `NodeList` object is almost the same as an `HTMLCollection` object.

Some (older) browsers return a NodeList object instead of an HTMLCollection for methods like `getElementsByClassName()`.

All browsers return a NodeList object for the property `childNodes`.

Most browsers return a NodeList object for the method `querySelectorAll()`.

The following code selects all `<p>` nodes in a document:

```jsx
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript HTML DOM!</h2>

<p>Hello World!</p>

<p>Hello Norway!</p>

<p id="demo"></p>

<script>
var myNodelist = document.querySelectorAll("p");
document.getElementById("demo").innerHTML =
"The innerHTML of the second paragraph is: " +
myNodelist[1].innerHTML;
</script>

</body>
</html>
```

# HTML DOM Node List Length

The `length` property defines the number of nodes in a node list:

```jsx
var myNodelist = document.querySelectorAll("p");
document.getElementById("demo").innerHTML = myNodelist.length;
```

The length property is useful when you want to loop through the nodes in a node list:

```jsx
var myNodelist = document.querySelectorAll("p");
var i;
for (i = 0; i < myNodelist.length; i++) {
  myNodelist[i].style.color = "red";
}
```

# The Difference Between an HTMLCollection and a NodeList

An `HTMLCollection` (previous chapter) is a collection of HTML elements.

A `NodeList` is a collection of document nodes.

A NodeList and an HTML collection is very much the same thing.

Both an HTMLCollection object and a NodeList object is an array-like list (collection) of objects.

Both have a length property defining the number of items in the list (collection).

Both provide an index (0, 1, 2, 3, 4, ...) to access each item like an array.

HTMLCollection items can be accessed by their name, id, or index number.

NodeList items can only be accessed by their index number.

Only the NodeList object can contain attribute nodes and text nodes.

A node list is not an array!

A node list may look like an array, but it is not.

You can loop through the node list and refer to its nodes like an array.

However, you cannot use Array Methods, like valueOf(), push(), pop(), or join() on a node list.