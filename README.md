This tutorial will help you understand the basics of the JavaScript for the number guessing game. The number guessing game is a faily simple one. The computer will generate a random number in a range set by the developer, and the player has to input their guess in the designated box and press the buttonto confirm the guess. The computer should then tell the player if their guess is correct or not, and if the guess is higher or lower than the generated number. If the player guesses the correct number, the computer should also tell the player how many guesses they took.

You will want to start out by giving JavaScript the ability to interact with your elements. This can be done with the document.querySelector() function. Simply create a variable and put document.querySelector() where you would put the value. In the parenthesis, put the name of the class you want the variable to point to in quotes. heres what it would look like:

```js
let guess = document.querySelector('.guess');
let guessButton = document.querySelector('.enter-guess');
let result = document.querySelector('.result');
```