# Kat's Journey with JavaScript 30

## Day 1 - JavaScript Drum Kit

### Notes:

_First steps, look at the finished project (to see what we are building), and start to notice the details that build it together._

- There are a set of 'keys' which represent parts of a drum.
- Each key plays a different drum sound, which is written under the letter.
- When you press the key, it plays a sound and also the button changes slightly a short animation.
- The key lights up with an border-color and it is slightly zoomed in, this is done with CSS

#### Trying on my own first:

- The styling and css has already been done for me, the buttons/keys are there already and it looks great.
- I need to get the functionality to work.
- When a key is pressed, I want it to play the corresponding sound and trigger the .playing css rule.
- I want the DOM to listen to when an action has been made within the window.
- I sort of understand what I want to happen, but I just can't seem to get the syntax right, maybe I don't fully understand it.
- This is what i got started with:

  `window.querySelector("key").addEventListener("keypress", function {})`

- I understand that I want to listen for an action within the window, I also thought I'd need to pick out the key class which is why I used querySelector and then the addEventListener to listen for a keypress and take an action (function). I was unsure of what to add with the function.
- Will watch the video now.

### Video notes:

- There is a key code that is associated with each key on the keyboard, I didn't know this, but we use the key code to link up the sounds and the keys.
- keycode.io is a useful website to find out what each number is on the keyboard.
