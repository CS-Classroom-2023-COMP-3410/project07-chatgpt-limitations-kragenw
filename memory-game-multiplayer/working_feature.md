**How I got it to Work**:

All I did was give chatGPT the files and say this:

Here are three files. Edit them to add the following feature.

Using JS to keep track of which player's turn it was, and then displaying that to the screen. Once the player made their turn, if they got a match, then the number of matches for that player would increment and display on the screen. There was a small wrinkle that made it slightly more complex, but if a player got a match, then they got to keep their turn until they didn't get a match. Once a player flips two cards and does not get a match, the turn transfers to the other player. This process repeats until the end of the game.

And it worked on the very first try.

All it did was add this, and some variables to hold each players score.

```
function switchPlayer() {
  currentPlayer = currentPlayer === 1 ? 2 : 1;
  updatePlayerDisplay();
}

function updateScore() {
  if (currentPlayer === 1) {
    player1Score++;
    player1ScoreDisplay.textContent = player1Score;
  } else {
    player2Score++;
    player2ScoreDisplay.textContent = player2Score;
  }
}

function updatePlayerDisplay() {
  currentPlayerDisplay.textContent = `Player ${currentPlayer}'s Turn`;
}
```