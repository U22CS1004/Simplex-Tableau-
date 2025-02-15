# Simplex-Tableau-
Abdulraheem Nafisat 
U22CS1004
Faculty of computing 
Department of Computer Science

Linear Programming and Simplex Method

Now, linear programming, or LP as we like to call it, is quite a handy mathematical tool. It helps optimize a goal, which we call an objective function, while keeping in mind some linear constraints that we need to respect. You might wonder where it’s used well, let me tell you, it finds its way into operations research, economics, logistics, and all sorts of decision making scenarios.

An LPP can be neatly defined as follows:
1. Objective Function You typically want to maximize or minimize something.

2. Constraints: These are your linear inequalities or equalities, like a well behaved student following the rules.

3. Non Negativity Condition: Every variable has to stay positive no negative thoughts allowed.

simplex Method
The Simplex Method, the brainchild of George Dantzig from way back in 1947, is an algorithm that whizzes through LP problems. It takes a systematic stroll around the corner points in the feasible region to uncover the best solution. Quite the clever chap, that Dantzig.

Simplex Method Overview
1. Initialization: Convert those inequalities into equalities. Think of it as adding a little slack or surplus variables. 

2. Pivoting: Pick out those entering and leaving variables based on how we want to optimize things.

3. Iterative Updates: Perform some neat row operations to shape a shiny new tableau.

4. Termination: You’ll know it’s time to stop when there are no more negative coefficients left in the objective row (especially if you’re maxing things out).

How the code will work 

This code implements the Simplex method, a popular algorithm for solving linear programming problems. The Simplex method is used to find the optimal solution to a linear objective function subject to linear inequality constraints. Here's a breakdown of how the code works:

1. Structure Definition:
    The Row structure represents a row in the Simplex tableau. It contains a vector of coefficients for the variables and a solution value.

2. Tableau Printing:
    The printTableau function displays the current state of the Simplex tableau, including the coefficients of the variables and the solution values for each row.

3. Entering Variable Selection:
 The findEnteringVariable function identifies the pivot column (entering variable) by finding the most negative coefficient in the objective function row. This variable is chosen to enter the basis to improve the objective function.

4. Leaving Variable Selection:
 The findLeavingVariable function determines the pivot row (leaving variable) by calculating the minimum ratio of the solution value to the corresponding coefficient in the pivot column. This ensures that the solution remains feasible.

5. Pivot Operation:
    The pivot function performs the pivot operation, which involves normalizing the pivot row and eliminating the pivot column coefficients in other rows. This step updates the tableau to move closer to the optimal solution.

6. Simplex Algorithm:
 The simplex function iteratively applies the Simplex method:
   It prints the current tableau.
   It selects the entering and leaving variables.
   It performs the pivot operation.
The process repeats until an optimal solution is found or an unbounded solution is detected.

7. Main Function:
 The main function initializes the Simplex tableau with an example linear programming problem. It then calls the simplex function to solve the problem and prints the optimal solution and the value of the objective function.
