let humanScore = 0;
let computerScore = 0;
let currentRoundNumber = 1;

function generateTarget(){
  return Math.floor(Math.random()*9)
}
function difference(a, b) {
  return Math.abs(a - b);
}
function compareGuesses(humanGuess, computerGuess, targetNum){
  if (humanGuess > 9 || humanGuess < 0){
    return 'Alert! Number out of range! Please choose in between 0 and 9!'
  }
  if (humanGuess === computerGuess){
    return true;
  }
  const humanGuessDiff = difference(humanGuess, targetNum);
  const computerGuessDiff = difference(computerGuess, targetNum);
  if (humanGuessDiff > computerGuessDiff){
    return false;
  }else {
    return true
  }
}
function updateScore(winnerString){
  switch (winnerString){
    case 'human':
      humanScore+=1;
      break;
    case 'computer':
      computerScore+=1;
      break;
  }
}
function advanceRound(){
  currentRoundNumber+=1
}
