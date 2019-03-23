---
title: HTML5 Audio and Video
module: 11
---

# Week 11 Audio and Video

Two of the most exciting tags elements introduced in HTML5 is the audio and video tags.  This allows us to embed audio and video just as easily as when we integrated images into our sites.

For Audio, the syntax is like this:

```html
<html>
    <head>
        <title>Audio/Video</title>
    </head>
    <body>
        <audio id="song" src="Brahms.mp3" controls="controls">
        </audio>
        <br>
    </body>
</html>
```

As you can see the audio tag sets the src of the song and then plays the song.  There is an attribute called controls which allow the basic controls to appear for the music player.

Similarly, the video controls works the same way.  The syntax looks like this:

```html
<html>
    <head>
        <title>Audio/Video</title>
    </head>
    <body>

        <video id="film" src="BOOM.mp4"` type="video/mp4" controls="true">
        </video>

    </body>
</html>
```

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech-Spring2019/master/Week%2011%20Examples/handsonscript.js"
        },
        {
            type: "html",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech-Spring2019/master/Week%2011%20Examples/HandsOnExample.html"

    }],
    showBlank: false,
    showResult: true,
    runScripts: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 100, "Lines": 100 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

1. Can you add your own audio?
2. Can you add your own video?


## Change Source with Events

```javascript
    var audio = document.getElementById("song");
    audio.src="Schubert.mp3";
```

and for the video, it would like like this:

```javascript
    var film = document.getElementById("film");
    film.src="Cat.mp4";
```

So, if we put it all together now.  The html file would look like this:

```html
<html>
    <head>
        <title>Audio/Video</title>
        <script src="main.js"></script>
    </head>
    <body>

        <audio id="song" src="Brahms.mp3" controls="controls">
        </audio>
        <br>
        <video id="film" src="BOOM.mp4"` type="video/mp4" controls="true">
        </video>

        <p></p>
        <button onclick="updateAudio();">Change Audio</button>

        <p></p>
        <button onclick="updateVideo();">Change Video</button>

    </body>
</html>
```



While the JavaScript file would look like this:

```javascript
function updateAudio()
{
    var audio = document.getElementById("song");
    audio.src="Schubert.mp3";
}

function updateVideo()
{
    var film = document.getElementById("film");
    film.src="Cat.mp4";
}
```

### Give it a try!

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech-Spring2019/master/Week%2011%20Examples/handsonscript.js"
        },
        {
            type: "html",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech-Spring2019/master/Week%2011%20Examples/HandsOnExample.html"

    }],
    showBlank: false,
    showResult: true,
    runScripts: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 100, "Lines": 100 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

1. Can you change your audio?
2. Can you change your video?


## Changes with jQuery

```javascript
$(document).ready(function(){
    $("#audiochange").click(function(){
        updateAudio();
    });

    $("#videochange").click(function(){
        updateVideo();
    });
});


function updateAudio()
{
    $("#song").attr("src", "Schubert.mp3"); 
}

function updateVideo()
{
    $("#film").attr("src", "Cat.mp4");
}

```

and the HTML file would look something like this:

```html
<html>
    <head>
        <title>Audio/Video</title>
        <script src="libs/jquery.min.js"></script>
        <script src="scripts/main.js"></script>
    </head>
    <body>

        <audio id="song" src="Brahms.mp3" controls="controls">
        </audio>
        <br>
        <video id="film" src="BOOM.mp4"` type="video/mp4" controls="true">
        </video>

        <p></p>
        <button id="audiochange">Change Audio</button>

        <p></p>
        <button id="videochange">Change Video</button>

    </body>
</html>
```

### You give it a try!

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech-Spring2019/master/Week%2011%20Examples/handsonscript.js"
        },
        {
            type: "html",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/441-WebTech-Spring2019/master/Week%2011%20Examples/HandsOnExample.html"

    }],
    showBlank: false,
    showResult: true,
    runScripts: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 100, "Lines": 100 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

1. Can you change your audio with jQuery?
2. Can you change your video with jQuery?


Good job! I knew you could do it!

The biggest difference would be removing the onclick event handler for each button and adding an id attribute to each button.  So, what about the canvas?