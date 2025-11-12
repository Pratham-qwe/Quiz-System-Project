# Quiz-System-Project
A small C program made in Turbo C++ that runs a simple memory game using C programming where the user must find matching pairs from a grid of hidden values.
Title
 Case Study on Memory Game (Pairs Matching)
 Objective
 To design and implement a simple memory game using C programming where the user must find
 matching pairs from a grid of hidden values.
 Problem Statement
 Develop a C program that allows a player to test their memory by revealing pairs of hidden
 symbols. If the symbols match, they remain revealed; otherwise, they are hidden again. The goal is
 to match all pairs with minimal attempts.
 Tools and Concepts Used
 • Programming Language: C
 • Concepts: Arrays, Loops, Conditional Statements, Functions, Random Number Generation
 • Tools: GCC Compiler, Text Editor (Code::Blocks / VS Code)
 System Design
 The system consists of a 2D array representing a grid of cards. Each card holds a hidden value,
 and the program randomly assigns pairs of numbers. The player selects two positions per turn, and
 the program checks for a match. The game continues until all pairs are matched.
 Flowchart or algorithm
 Algorithm:
 1. Initialize a 2D array with pairs of numbers placed randomly.
 2. Display the grid with all cards hidden.
 3. Ask the user to input two positions to reveal.
 4. Check if the revealed values match:
 • If yes, keep them revealed.
 • If no, hide them again.
 5. Continue until all pairs are matched.
 6. Display the total number of attempts.
 Code Snippet or Module Explanation
 #include
 #include
 #include
 int main() {
 int grid[4][4], shown[4][4] = {0}, i, j, x1, y1, x2, y2, matched = 0, attempts = 0;
 int values[8] = {1,1,2,2,3,3,4,4};
 srand(time(0));
 // Shuffle values
 for(i=0;i<8;i++){int r=rand()%8;int t=values[i];values[i]=values[r];values[r]=t;}
// Fill grid
 for(i=0;i<2;i++) for(j=0;j<4;j++) grid[i][j]=values[i*4+j];
 while(matched < 8) {
 attempts++;
 printf("Enter coordinates of two cards (row col): ");
 scanf("%d %d %d %d", &x1;, &y1;, &x2;, &y2;);
 if(grid[x1][y1] == grid[x2][y2] && (x1!=x2 || y1!=y2)) {
 shown[x1][y1] = shown[x2][y2] = 1;
 matched++;
 printf("Match found!\n");
 } else {
 printf("Not a match!\n");
 }
 }
 printf("You completed the game in %d attempts!\n", attempts);
 return 0;
 }
 Output Examples
 Sample Output:
 Enter coordinates of two cards (row col): 0 0 0 1
 Not a match!
 Enter coordinates of two cards (row col): 1 2 1 3
 Match found!
 You completed the game in 10 attempts!
 Conclusion
 The memory game successfully demonstrates fundamental programming concepts like arrays,
 loops, and conditionals. It provides an engaging way to practice logical thinking and pattern
 recognition using C programming.
 Limitations and Future Scope
 Limitations:
 • The grid size is fixed and small.
 • No graphical interface; console-based only.
 Future Scope:
 • Add graphical user interface using graphics libraries.
 • Implement different difficulty levels.
 • Include timer-based scoring for competitive gameplay.
 Name: Pratham
 UID: 25BCU10019
