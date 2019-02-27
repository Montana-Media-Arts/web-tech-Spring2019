---
title: jQuery DOM
module: 8
jotted: false
---

# JQuery and the DOM

What about the DOM?  Remember the document.getElementById?  How do we access the DOM in JQuery?

So, to access or change items in the DOM, you have three main methods that allow you to do that:

1. text()
2. html()
3. val()

These will allow us to get the text items from an element, the html including the HTML markup or the value from a textbox for instance.

Let's see these in action.

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                window.alert($("#infoid").text());
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```

This code should return just the inner text of the paragraph tag.  However, using the **html** method, we should get everything including the bold tags **<b>**.

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                window.alert($("#infoid").html());
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```

Finally, if we want to get something out of a textfield, we can use the val() method.

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                window.alert($("#txtName").val());
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <input type="text" id="txtName">
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```

You have to admit, it's definitely shorter! I know it's different syntax, but you do some really cool stuff here.

So, what about if you want to change an item in the DOM?  Before, we used the equal sign and changed the innerHTML, now we can change it passing a parameter into the method.  For example, we can do something like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>

        $(document).ready(function () {
            $("button").click(function () {
                $("#infoid").text("I am a changed man!");
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a <b>paragraph</b>.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to get information</button>
    <br>
    <div id="message"></div>
</body>

</html>
```

I can do that with the html() and val() methods as well. Now, that is good stuff!  Keep in mind, there are a lot more things we can do with JQuery, but I wanted to just introduce you to the concept today and then we will go into more functionality next week.