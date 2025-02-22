java c
Programming Assignment 1 
Write two programs that solves the Best Independent Set problem, as described in Problem Set 1. The first will use iterative deepening; the second will use simple hill climbing with random restart. 
Input 
Input should be a text file named "input.txt" in the same working directory as the code with the following contents:
·   Line 1: The target (a positive integer) and flags: "V" for verbose output or "C" for compact output. For the hill-climbing program, the number of random restarts to run.
·   Each vertex. Name (you may assume that this is a single alphabetic character) and value (a positive integer), 1 per line.
·   Blank line
·   Each edge: the names of the two ends. 1 per line.
Your program should be robust as regards trailing white space at the end of a line of input or blank lines at the end of the input.
Examples are given below.
Search 
The programs should search through the state space until either:
a) A solution is found.
b) In iterative deepening, search to depth K finds no states at depth K. (That is, none of the states at depth K-1 have any successors). Thus, if there is no goal state to be found, the search to depth K will be identical to the search to depth K-1; then the program will terminate.
c) In hill climbing, each hill climb is carried out from a random starting state until it reaches a solution or a local maximum. A random starting point is constructed by going through the list of vertices and accepting or rejecting each with probability 1/2.
In doing the hill climbing part of the assignment, it's a good idea to write your code so there is a module where you can specify the starting state. That way, you can both replicate your code's behavior, which is useful in debugging, and compare it against my samples. However, the code that you submit should construct random starting states.
Output 
The program should print out to standard output:
·   If a solution is found, the solution (just a sequence of vertices).
If no solution is found, then "No solution found"
·   If the "verbose" flag is set then a trace of the search sequence, as illustrated below.
Coding 
Programs will be accepted in Java or Python. Check with me about other languages.
Submit 
The source code for the two programs. Also a README file for how to compile and run your code if there is anything non-obvious about that. Do not assume that the grader will read instructions passed in comments in code. Definitely do not write your code in such a way that the grader has to edit it in order to compile or run it (e.g. hard code a path that exists on your own machine).
Grading 
Grading: 8 points for correctly running code. 2 points for well-written code. A programming assignment counts equally with a problem set in computing the overall grade.
Input for iterative deepening program, for graph 1. Target = 18
18 V
A 3
B 5
C 6
D 10
E 13


A B
A C
B D
C E
D E
Output
Depth=1.
A Value=3.
B Value=5.
C Value=6.
D Value=10.
E Value=13.


Depth=2.
A Value=3.
A D Value=13.
A E Value=16.
B Value=5.
B C Value=11.
B E Value=18.


Found solution B E Value=18
The input for hill clim代 写Programming Assignment 1Java
代做程序编程语言bing is the same, except that you have to indicate the number of random restarts on the top line. E.g.
18 V 4
for a target of 18, with four random restarts, verbose output.
In verbose output for hill climbing, you should indicate the value of the Error function as well as the cost for a state, and show all the neighbors that are being tested. (The order in which you enumerate neighbors doesn't matter.)
Sample output
Randomly chosen start state: A
A Value=3. Error=15.
Neighbors: 
{} Value=0. Error=18.
A B Value=8. Error=13.
A C Value=9. Error=12.
A D Value=13. Error=5.
A E Value=16. Error=2. 


Move to A E. Value=16. Error=2.
Neighbors
E Value=13. Error=5.
A B E Value=21. Error=3.
A C E Value=22. Error=9.
A D E Value=26. Error=10.
A Value=3. Error=15.


Search failed


Randomly chosen start state B C D
B C D Value=21. Error=5.
Neighbors
A B C D Value=24. Error=11.
C D Value=16. Error=2.
B D Value=15. Error=8.
B C Value=11. Error=7.
B C D E Value=34. Error=21.


Move to C D Value=16. Error=2.
Neighbors
A C D Value=19. Error=3.
B C D Value=21. Error=5.
D Value=10. Error=8.
C Value=6. Error=12.
C D E Value=29. Error=16.


Search failed


Randomly chosen start state A B C E. Value=27. Error=12.
Neighbors
B C E Value=24. Error=6.
A C E Value=22. Error=9.
A B E Value=21. Error=3.
A B C D E Value=37. Error=27.
A B C Value=14. Error=10


Move to A B E Value=21. Error=3
Neighbors
B E Value=18. Error=0


Found solution B E Value=18.


Another sample input and output. 
Input for Iterative Deepening


18 V


F 3


G 6


H 8


I 9


K 8


L 7


F G


F L


G H


G I


H K


H L


I K


Output


Depth=1.


F Value=3.


G Value=6.


H Value=8.


I Value=9.


K Value=8.


L Value=7.


Depth=2.


F Value=3.


F H Value=11.


F I Value=12.


F K Value=11.


G Value=6.


G K Value=14.


G L Value=13.


H Value=8.


H I Value=17.


I Value=9.


I L Value=16


K Value=8.


K L Value=15.


L Value=7.


Depth=3.


F Value=3.


F H Value=11.


F H I Value=20.


Found solution F H I Value=20


Same input for hill-climbing except that the first line is 18 V 3


Randomly chosen start state G H L


G H L Value=21. Error=13


Neighbors


F G H L Value=24. Error=19.


H L Value=15. Error=10.


G L Value=13. Error=5


G H I L Value=30. Error=19.


G H K L Value=29. Error=21.


G H Value=14. Error=10.


Move to G L Value=13. Error=5.


Neighbors


F G L Value=16. Error=8.


L Value=7. Error=11.


G H L Value=21. Error=13.


G I L Value=22. Error=6.


G K L Value=21. Error=0.


Found solution G K L Value=21.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
