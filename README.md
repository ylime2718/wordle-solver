# wordle-solver
The goal of this project is to offer an optimal solution to the [Wordle Game](https://www.nytimes.com/games/wordle/index.html).

![Wordle](wordle.jpeg)

## Allowable Words
"Real Words" are actual words that can WIN the daily Wordle. (2,309)

"Valid Words" are 5-letter strings that the game will accept as valid guesses. (10,665)

These lists are mutually exclusive, so there are actually 12,974 total valid guesses for this game.

## How to Play
1. Enter your initial guess.
2. Wordle will give feedback on the letters in your guess (**Green** = correct letter in correct position; **Yellow** = correct letter in wrong location; **Gray** = wrong letter, not in word at all)
3. Make another guess, try to get all letters Green (win the game!)

## Components of Solver
### User Interface
For this first version, the interface is be text-based. Users enter their guess and the feedback given by Wordle. The program prints the next recommended guess.

### Word Filter
After each guess, the word filter analyzes the list of "Real Words" and eliminates words based on the feedback from Wordle. Green letters require an exact match in position. Yellow letters require the winning word contain that letter but NOT in the position it was originally guessed. Gray letters may not be in the word at all.

### Recommender
The recommendation system chooses the optimal next guess based on what words remain in the list of possible winners. This is the most complex part of the solver.
