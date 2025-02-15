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
1. Constructor: Simplex(vector<vector<double>> &A, vector<double> &b, vector<double> &c)
•	Purpose: Initializes the simplex tableau using the input coefficients of constraints (A), right-hand side values (b), and the objective function coefficients (c).
•	Parameters:
o	A: Coefficients of constraint equations.
o	b: Right-hand side values for the constraints.
o	c: Coefficients of the objective function.
•	How it Works:
o	Constructs the initial tableau.
o	Adds slack variables to transform inequalities into equations.
o	Sets up the last row for the objective function.

2. void printTableau()
•	Purpose: Prints the current simplex tableau along with the Zj row and Cj - Zj row to track the computation process.
•	How it Works:
o	Prints the entire tableau in a formatted way.
o	Computes the Zj row (the sum of basic variable contributions).
o	Computes Cj - Zj row to check for optimality conditions.
o	Displays both rows.

3. bool isOptimal()
•	Purpose: Checks whether the current tableau represents an optimal solution.
•	How it Works:
o	Iterates over the objective row (last row of the tableau).
o	If any coefficient is negative, the solution is not optimal and further iterations are required.
o	If all values are non-negative, the algorithm terminates.

4. void pivot(int pivotRow, int pivotCol)
•	Purpose: Performs the pivoting operation to bring a new variable into the basis.
•	Parameters:
o	pivotRow: Index of the row containing the pivot element.
o	pivotCol: Index of the column containing the pivot element.
•	How it Works:
o	Divides the pivot row by the pivot element to make the pivot element 1.
o	Updates all other rows to make the pivot column entries 0, ensuring a valid basic feasible solution.
o	Uses the row operations of the Simplex method to maintain feasibility.

5. void solve()
•	Purpose: Iteratively applies the Simplex algorithm to reach an optimal solution.
•	How it Works:
o	Repeatedly checks for optimality using isOptimal().
o	Identifies the pivot column (most negative value in the objective row).
o	Identifies the pivot row using the minimum ratio test (smallest positive ratio of RHS to the pivot column value).
o	If no valid pivot row exists, the problem is unbounded.
o	Performs the pivot operation.
o	Prints the updated tableau after each iteration.
o	Stops once an optimal solution is reached.


