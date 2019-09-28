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
- keycode.info is a useful website to find out what each number is on the keyboard.

< div data-key="65" class="key" ></br>
< kbd> A < /kbd ></br>
< span> class="sound"> clap < /span > </br>
< /div>

`<audio data-key="65" src="sounds/clap.wav"></audio>`

- The above snippits tell us that they are both connected with the attribute data-key="65".
- This is telling the browser that when data-key="65" is pressed it will look to see what letter it represents, in this case A, then it will link with the element audio and play the sound clap.
- Data attributes were made to allow people to make up their own attributes and still allow html syntax to understand.
- To make up your own attribute use data-whatever, but I don't think it is common practice

- First up we are listening for a keyup event from whatever element you are listening for, this could be an input, div etc but in this case we are looking for an event happening in the window.
- Then we add a method to listen for that event which is the addEventListener method

`window.addEventListener()`

- ^ so this is saying, get ready to listen for something happening in the window element.
- Within the parenthesis we need to add what we want to listen for, and we want to listen for an event called keydown. Which is essentially when a key on the keyboard is pressed down.
- The keydown needs to be surrounded by quote marks.

`window.addEventListener("keydown")`

- Then we need to add a function which will have the event, but nothing inside the body of the function.

`window.addEventListener("keydown" function(event){})`

- ^ we are going to listen for a keydown event that'll happen within the window element, and when the event happens, run this function.
- Event is just an object which is full of data, try doing console.log(event) and press a key and see what it prints in the console or console.log(event.keyCode).

- Now we need to search for 65 within the page or document, which will connect the audio to the key, since they both have the same data-key="65".

`window.addEventListener("keydown" function(event){`

`const audio = document.querySelector("audio") })`

- Using querySelector, we want to find the element audio and pick out the 65, but since there is no class, we need to use an attribute selector to pick out 65.

        const audio = document.querySelector(
          `audio[data-key=${event.keyCode}]`

- Got a little lost here, but using backticks ` and the dollar sign \$ means something.
- Use console.log(audio); to see what you get.
- Now when we hit the key, we print the audio element for that key.
