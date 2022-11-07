This tutorial will help you understand the basics of the JavaScript for the number guessing game. The number guessing game is a faily simple one. The computer will generate a random number in a range set by the developer, and the player has to input their guess in the designated box and press the buttonto confirm the guess. The computer should then tell the player if their guess is correct or not, and if the guess is higher or lower than the generated number. If the player guesses the correct number, the computer should also tell the player how many guesses they took.

You will want to start out by giving JavaScript the ability to interact with your elements. This can be done with the ```document.querySelector()``` function. Simply create a variable and put ```document.querySelector()``` where you would put the value. In the parenthesis, put the name of the class or id you want the variable to point to in quotes. heres what it would look like:

```js
let guess = document.querySelector('.guess');
let guessButton = document.querySelector('.enter-guess');
let result = document.querySelector('.result');
let totalGuesses = document.querySelector('.total-guesses');
```
Keep in mind that ```document.querySelector()``` will select the first element with the class you give it. 

We will also want to keep track of how many guesses the player has made, so make a variable and set its value to 0 like so let guessCount = 0;. Generating a random number is a little bit tricky but isn't very complicated. You will use Math.random() and Math.trunc() to round the number. Math.random() will generate a random number from 0 to 1 and Math.Trunc will round the number down. To get a random number in a specific range you create a variable and set its value to ```Math.trunc(Math.random() * 50 + 1);```. 50 can be switched out for whatever number you want and will be the range that you want.

Next on the list is to make your button react to being pressed. In this case I have referred to the button as "guessButton" and made it point to the element with the class "enter-guess". To add functionality to it all we're going to do is give it a "click" event listener:

```js
guessButton.addEventListener('click', () => {

});
```
The eventListener will act like a function everytime the player clicks the button. It will call other functions do verify the guess and give feedback.

First let's make a function that counts how many guesses the player has made. Create a function, give it a name, and inside the function simply increment the guess count by one.

```js
function countGuess() {
    guessCount++;
}
```
The next function will chack the player's guess, compare it to the randomly generated one and give feedback to the player. It should tell the player if the number was too high, too low, not a number at all and if the player guessed correctly. This can be done by chaining a few if else statements.

```js
function checkGuess(playerGuess) {
    if (playerGuess === '') {
        result.value = 'Please enter a guess';
    } else if (isNaN(playerGuess)) {
        result.value = 'Please enter a number';
    } else if (playerGuess > number) {
        result.value = 'Too high';
    } else if (playerGuess < number) {
        result.value = 'Too low'
    } else if (Number(playerGuess) === number) {
        result.value = `You guessed the number in ${guessCount} tries!`;
    }
}
```
The first if will check if the player even entered a guess at all. If not then the value of the result element will change to inform the player they didn't enter anything. depending on the kind of element you used, you may have to change ```.value``` to ```.innerHTML```. the first if else will check if the guess isn't a number with ```isNaN()```. ```isNaN()``` will check if anything you put in the parenthesis isn't a number and return true or false. The rest simply checks if the guess is higher lower or equal to the random number.

Once you have your functions made, add them to the event listener.
```js
guessButton.addEventListener('click', () => {
    countGuess();
    checkGuess(guess.value.trim());
});
```
You should now have a simple working guess the number game.

Click [here](https://gabenicholauson.github.io/Guess-the-number-tutorial/) to view the game