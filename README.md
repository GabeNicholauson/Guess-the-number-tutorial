This tutorial will help you understand the basics of the JavaScript for the number guessing game. The number guessing game is a faily simple one. The computer will generate a random number in a range set by the developer, and the player has to input their guess in the designated box and press the buttonto confirm the guess. The computer should then tell the player if their guess is correct or not, and if the guess is higher or lower than the generated number. If the player guesses the correct number, the computer should also tell the player how many guesses they took.

You will want to start out by giving JavaScript the ability to interact with your elements. This can be done with the document.querySelector() function. Simply create a variable and put document.querySelector() where you would put the value. In the parenthesis, put the name of the class or id you want the variable to point to in quotes. heres what it would look like:

```js
let guess = document.querySelector('.guess');
let guessButton = document.querySelector('.enter-guess');
let result = document.querySelector('.result');
```
Keep in mind that document.querySelector() will select the first element with the class you give it. 

We will also want to keep track of how many guesses the player has made, so make a variable and set its value to 0 like so let guessCount = 0;. Generating a random number is a little bit tricky but isn't very complicated. You will use Math.random() and Math.trunc() to round the number. Math.random() will generate a random number from 0 to 1 and Math.Trunc will round the number down. To get a random number in a specific range you will do ```js Math.trunc(Math.random() * 50 + 1); ```. 50 can be switched out for whatever number you want. 