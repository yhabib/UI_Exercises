# Piano

In this exercise we are going to create this digital piano. The task is divided in two parts:
1. Recreate the layout with your own design.
2. Adding a sound to each key.

We make use of the `data-*` attribute to bind a piano key to a sound, so when we have to find them later on in our JS.
```javascript
<div data-key="KeyA" class="piano-key"><div>A</div></div>
<audio data-key="KeyA" src="wav/c1.wav"></audio>
```

All the necessary sounds can be found in the `/wav` folder.

## Keywords
* `audio`: A new HTML5 tag
* `data-*`: A customizable HTML property
* `addEventListener`: When the apropriate key is pressed the related event should be triggered, reproducing the sound.