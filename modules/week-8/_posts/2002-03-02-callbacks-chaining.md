---
title: Callbacks and Chaining
module: 8
jotted: false
---

* Callbacks and Chaining

What are these?  These extend our JQuery functionality.  They are really helpful and will reduce code required to accomplish the same task.

** Callbacks
With each JQuery method, you can also add a callback function.  What is that?  A callback 
function is a function that is  called when the first function has completed.  This look at an example.

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                 $(".myGreatClass").fadeOut("slow", function(){
                     $("#infoid").toggle();
                 });
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```

So, what just happened?  The paragraph element fades out slowly when the button is clicked.  Then, after the paragraph fades away, then the paragraph with the id **infoid** will toggle.  Keep in mind, it doesn't have to be another method, it can anything you want in there.

** Chaining

So, what is chaining?  This allows us to call multiple methods and have them apply to the same element.  One example might look like this:

```html
<!DOCTYPE html>
<html>

<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(function () {


        });
        $(document).ready(function () {
            $("button").click(function () {
                 $(".myGreatClass").fadeOut("slow").fadeIn("slow");
            });
        });
    </script>
</head>

<body>

    <p id="infoid">This is a paragraph.</p>
    <p class="myGreatClass" style="background-color:red">This is the second paragraph.</p>
    <button>Click me to hide paragraphs</button>
    <br>
</body>

</html>
```

Using the dot operator, we can chain multiple functions together and have them execute one after another.  Cool eh?