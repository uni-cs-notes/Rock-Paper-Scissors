# Rock-Paper-Scissors

 >  Programming fundamentals
 >  Project # Rock Paper Scissors

   ![image](https://github.com/uni-cs-notes/Rock-Paper-Scissors/assets/160413612/299f9ee1-a132-4dd4-948d-7101839b52fe)



#### The objective of rock, paper, scissors is to defeat your opponent by choosing a symbol that beats theirs according to these rules:
> `Rock crushes Scissors`
> `Scissors cut Paper`
> `Paper covers Rock`
> `If both players throw the same symbol, it's a tie and you usually play again.`
### Code objective
* These are the following functions used in the code >>
1. char getComputerOption()
2. void displayGameRules()
3. char getUserOption()
4. void showSelectedOption(char option)
5. void chooseWinner(char uChoice, char cChoice)
6. int main ()
> A total of 3 void functions with 2 char functions within a pair of overloaded
> functions as well as our main function.
### Code explanation
```
#include <iostream>
#include <ctime>
#include <cstdlib>
using namespace std;const char ROCK = 'r';
const char PAPER = 'p';
const char SCISSORS = 's';
char getComputerOption() {
int num = rand () % 3 + 1;
if(num==1) return 'r';
if(num==2) return 'p';
if(num==3) return 's';
return '\0';
}
```
> 1. Header Inclusions:
* `#include <iostream>`: This line includes the iostream header file, which provides functionalities for input/output operations like cout (output) and cin (input) used for user interaction.
* `#include <ctime>`: This line includes the ctime header file, which provides functions for time-related operations. In this code, it's likely used by the rand () function in getComputerOption.
* `#include <cstdlib>`: This line includes the cstdlib header file, which provides various general-purpose functionalities. In this code, it's likely used for the rand () function, which generates random numbers.
> 2. Constants:
* `const char ROCK = 'r'`; This line defines a constant character variable named ROCK and assigns it the value 'r'. This represents the rock symbol in the game.
* `const char PAPER = 'p'`; Similar to ROCK, this line defines a constant character variable named PAPER with the value 'p' representing the paper symbol.
* `const char SCISSORS = 's'`; Similar to the above, this line defines a constant for the scissors symbol 's'.
> 3. getComputerOption Function:
* This function is responsible for generating the computer's choice for the game.
* int num = rand () % 3 + 1; This line generates a random integer between 1 and 3 (inclusive) using the rand () function. The modulo operator (%) is used to get the remainder after dividing by 3.
*  The following if statements check the value of num and return the corresponding symbol:
```
o if(num==1) return 'r'; If num is 1, it returns the rock symbol 'r'.
o if(num==2) return 'p'; If num is 2, it returns the paper symbol 'p'.
o if(num==3) return 's'; If num is 3, it returns the scissors symbol 's'.
o If none of the conditions are met (which is unlikely), the function returns the
null character '\0'.
```
```
void displayGameRules() {
cout << "Welcome to Rock, Paper, Scissors!" << endl;
cout << "The rules are as follows:" << endl;
cout << "Rock beats Scissors" << endl;
cout << "Paper beats Rock" << endl;
cout << "Scissors beats Paper" << endl;
}
char getUserOption() {
char c;
cout << "Enter your choice (r, p, or s): " << endl;cin >> c;
while (c! ='r' && c! ='p' && c! ='s')
{
cout << "Invalid input. Please enter r, p, or s." << endl;
cin >> c;
}
return c;
}
void showSelectedOption(char option) {
if (option == 'r') cout << "Rock" << endl;
if (option == 'p') cout << "Paper" << endl;
if (option == 's') cout << "Scissors" << endl;
}
```
### 1. displayGameRules Function:
> This function serves to inform the user about the game's rules.
* It uses cout statements to display welcome messages and the core rules of
`Rock, Paper, Scissors.`
### 2. getUserOption Function:
> This function handles user input for their choice in the game.
* It prompts the user to enter their choice using cout with a message specifying valid options` (r, p, or s).`
* A char variable c is declared to store the user's input.
* A while loop is used to validate the user's input. The loop continues as long as `c is not equal to 'r', 'p', or 's'`.
*  Inside the loop, an error message is displayed using cout if the input is invalid.
*  The loop then prompts the user to enter a valid choice again using cin.• Once the user enters a valid choice (r, p, or s), the function returns the entered character c.
### 3. showSelectedOption Function:
*  This function takes a character (option) as input, which represents the user's choice.
* It uses an if statement to check the value of option:
*  If option is 'r', it prints "Rock" using cout.Similar checks are done for 'p' (prints "Paper") and 's' (prints "Scissors").
```
void chooseWinner(char uChoice, char cChoice) {
if (uChoice == ROCK && cChoice == PAPER) {
cout << "Computer Wins! Paper wraps Rock."<< endl;
}
else if (uChoice == PAPER && cChoice == SCISSORS) {
cout << "Computer Wins! Scissors cut Paper."<< endl;
}
else if (uChoice == SCISSORS && cChoice == ROCK) {
cout << "Computer Wins! Rock smashes Scissors."<< endl;
}
else if (uChoice == ROCK && cChoice == SCISSORS) {
cout << "You Win! Paper wraps Rock."<< endl;
}
else if (uChoice == PAPER && cChoice == ROCK) {
cout << "You Win! Paper wraps Rock."<< endl;
}
else if (uChoice == SCISSORS && cChoice == PAPER) {
cout << "You Win! Scissors cut Paper."<< endl;
}
else {cout << "Tie. Play again win the Game." << endl;
}
}
```
### 4. chooseWinner function:
* The function takes two-character arguments: uChoice representing the user's choice and cChoice representing the computer's choice.
* It uses a series of if and else if statements to compare these choices and determine the winner:
* Each if statement checks for a specific winning combination of user and computer choices.
* If a winning combination is found for the computer (e.g., uChoice == ROCK && cChoice == PAPER),` a message is displayed stating the computer wins along with a reasoning statement.`
*  Similar checks are done for other winning combinations for the computer.
*  If none of the conditions for the computer winning are met, the code checks for winning combinations for the user using similar logic.
*  If a winning combination is found for the user, a message is displayed stating the user wins along with a reasoning statement.
*  Finally, if none of the above conditions are met, it means it's a tie, and a message is displayed prompting the user to play again.
### Integration with Existing Code:
> This function can be integrated with the previously explained code to complete the game logic. The overall flow could be:
1. Call displayGameRules to show the game rules.
2. Call getUserOption to get the user's choice.
3. Call getComputerOption to get the computer's choice.
4. Call chooseWinner with the user's and computer's choices to determine the winner.
5. Display the results using the messages provided by chooseWinner.
```
int main() {
char uChoice;char cChoice;
displayGameRules();
while (true) {
uChoice = getUserOption();
cout << "Your choice is: "<< endl;
showSelectedOption(uChoice);
cout << "Computer's choice is: "<< endl;
cChoice = getComputerOption();
showSelectedOption(cChoice);
chooseWinner(uChoice, cChoice);
cout << "Do you want to play again? (y/n)" << endl;
char playAgain;
cin >> playAgain;
if (playAgain == 'n') break;
}
return 0;
}
```
## The Main Functionality:
> The main function is the entry point of the program.
* It declares character variables uChoice to store the user's choice and cChoice to store the computer's choice.
* It is called displayGameRules to show the game rules to the user.
* It uses a while loop that continues indefinitely `(while(true))` to allow the user to play multiple rounds.
>  Inside the loop:
*  The user's choice is obtained by calling getUserOption and stored in uChoice.
* The user's choice is displayed using showSelectedOption with a message.
* The computer's choice is generated by calling getComputerOption and stored in cChoice.▪ The computer's choice is displayed using showSelectedOption with a message.
* `The winner is determined by calling chooseWinner with uChoice and
cChoice.`
> After each round, the user is prompted to play again using cout with amessage. It asks for input (y/n) and stores it in the character variable
playAgain.
* `An if statement checks if the user entered 'n' (no) for playAgain.`
*  If the user chooses `'n'`, the break statement `exits the loop, ending the game.`
> Finally, the main function returns 0, indicating successful program
execution.
### Overall Game Flow:
> This main function ties together the previously explained functionalities to create a complete Rock, Paper, Scissors game. Here's the summarized flow:
> 6. Display Game Rules: The user is shown the game rules.
> 7. Play a Round:
* Users enter their choice (rock, paper, or scissors).
* Computers generate its choice randomly.
* User's and computer's choices are displayed.
* The winner is determined based on the choices.
* Winner and reasoning are displayed.
> 8. Play Again Prompt: The user is asked if they want to play again.
> 9. Repeat or End:
* If the user chooses to play again, the loop continues to step 2 (play a round).
* If the user chooses to stop, the loop exits, and the program ends.
