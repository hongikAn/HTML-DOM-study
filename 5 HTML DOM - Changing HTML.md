# 5. HTML DOM - Changing HTML

Created By: 홍익 안
Last Edited: Nov 25, 2020 6:36 PM

# Changing the HTML Output Stream

JavaScript can create dynamic HTML content:

**Date: Wed Nov 25 2020 18:20:00 GMT+0900 (Korean Standard Time)**

In JavaScript, `document.write()` can be used to write directly to the HTML output stream:

```html
<!DOCTYPE html>
<html>
<body>

<script>
document.write(Date());
</script>

</body>
</html>
```

Never use document.write() after the document is loaded. It will overwrite the document.

# Changing HTML Content

The easiest way to modify the content of an HTML element is by using the `innerHTML` property.

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript can Change HTML</h2>

<p id="p1">Hello World!</p>

<script>
document.getElementById("p1").innerHTML = "New text!";
</script>

<p>The paragraph above was changed by a script.</p>

</body>
</html>
```

# Changing the Value of an Attribute

```html
<!DOCTYPE html>
<html>
<body>

<img id="image" src="smiley.gif" width="160" height="120">

<script>
document.getElementById("image").src = "landscape.jpg";
</script>

<p>The original image was smiley.gif, but the script changed it to landscape.jpg</p>

</body>
</html>
```