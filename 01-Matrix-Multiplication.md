MIT 18.06 Lecture 1: The Geometry of Linear Equations – Study Guide
The fundamental problem of linear algebra is solving a system of linear equations. This study guide explores three distinct ways to conceptualize these systems: the Row Picture, the Column Picture, and the Matrix Form. Understanding these perspectives is essential for grasping how linear combinations function and identifying the conditions under which a system can be solved.

1. The Three Viewpoints of Linear Equations
To solve a system of n equations with n unknowns, one can analyze the problem through three different lenses.
The Row Picture
The row picture focuses on each individual equation within the system.
•	Geometric Interpretation: In a 2D system, each equation represents a line. The solution is the point where the lines intersect. In a 3D system, each equation represents a plane. The intersection of two planes forms a line, and the intersection of that line with a third plane (if it exists) is a single point representing the solution.
•	Complexity: While intuitive for two dimensions, the row picture becomes difficult to visualize as dimensions increase (e.g., three planes intersecting in 3D space).
The Column Picture
The column picture focuses on the columns of the coefficient matrix rather than the individual equations.
•	Geometric Interpretation: This view treats the columns of the matrix as vectors. The goal is to find the right linear combination of these column vectors that produces the right-hand side vector b.
•	Key Concept: This is the most fundamental operation in linear algebra. It shifts the focus from "where do these lines/planes meet?" to "how can we combine these vectors to reach a specific point in space?"
The Matrix Form (Ax = b)
This is the algebraic shorthand used to describe the entire system.
•	A: The coefficient matrix (a rectangular array of numbers).
•	x: The vector of unknowns.
•	b: The vector representing the right-hand side.
•	Interpretation: The product Ax is a linear combination of the columns of A.
2. Analysis of a 2D System
Equations:
3. 2x - y = 0
4. \-x + 2y = 3
The Row Picture
•	Equation 1: A line passing through the origin (0,0) and the point (1,2).
•	Equation 2: A line passing through (-3,0) and (-1,1).
•	Intersection: The two lines meet at the point x = 1, y = 2. This point satisfies both equations simultaneously.
The Column Picture
The system is rewritten as a linear combination of column vectors: x \\begin{bmatrix} 2 \\ -1 \\end{bmatrix} + y \\begin{bmatrix} -1 \\ 2 \\end{bmatrix} = \\begin{bmatrix} 0 \\ 3 \\end{bmatrix}
•	Column 1 (col\_1): \\begin{bmatrix} 2 \\ -1 \\end{bmatrix}
•	Column 2 (col\_2): \\begin{bmatrix} -1 \\ 2 \\end{bmatrix}
•	Target (b): \\begin{bmatrix} 0 \\ 3 \\end{bmatrix}
Visualizing the Solution: Taking 1 of col\_1 and 2 of col\_2 (hooking the vectors end-to-end) results in the vector \\begin{bmatrix} 0 \\ 3 \\end{bmatrix}. The algebra confirms this: 1(2) + 2(-1) = 0 and 1(-1) + 2(2) = 3.
5. Analysis of a 3D System
Equations:
6. 2x - y + 0z = 0
7. \-x + 2y - z = -1
8. 0x - 3y + 4z = 4
The Row Picture
Each equation represents a plane in 3D space (x, y, z).
•	The first two planes meet in a line.
•	The third plane intersects that line at a specific point.
•	Solution: In this specific example, the solution is (0, 0, 1).
The Column Picture
The system is expressed as: x \\begin{bmatrix} 2 \\ -1 \\ 0 \\end{bmatrix} + y \\begin{bmatrix} -1 \\ 2 \\ -3 \\end{bmatrix} + z \\begin{bmatrix} 0 \\ -1 \\ 4 \\end{bmatrix} = \\begin{bmatrix} 0 \\ -1 \\ 4 \\end{bmatrix}
Observation: In this particular case, the right-hand side b is identical to the third column. Therefore, the linear combination is simple: 0(col\_1) + 0(col\_2) + 1(col\_3) = b. The solution vector x is (0, 0, 1).
9. Matrix Multiplication: Ax
There are two primary ways to compute the product of a matrix and a vector.
Method	Description	Conceptual Focus
Column Method	Ax is a linear combination of the columns of A. Multiply each column by its corresponding component in x and add them together.	Synthesis of vectors (Strang's preferred method).
Row Method	Each component of the result is the dot product of a row of A and the vector x.	Individual equation satisfaction.
10. Solvability: Singular vs. Non-singular Cases
A critical question in linear algebra is: Can Ax = b be solved for every possible b?
Non-singular (Invertible) Case
In a "nice" case, the columns are independent and their linear combinations fill the entire space (e.g., all of 2D or 3D space).
•	For a 3 \\times 3 matrix, if the three column vectors do not lie in the same plane, their combinations can reach any point in 3D space.
•	A random matrix is almost always non-singular.
Singular (Non-invertible) Case
A matrix is singular if the linear combinations of its columns do not fill the entire space.
•	In 3D: If three columns all lie in the same plane, any linear combination of them will also remain in that plane.
•	Solvability: If b lies outside that plane, there is no solution. If b lies within that plane, there are solutions (typically infinitely many).
•	Independence: A singular case occurs if the columns are not independent (e.g., if column 3 is just the sum of columns 1 and 2).
Higher Dimensions
The concepts scale to n dimensions. In a 9-dimensional space (9 \\times 9 matrix), we look at the linear combinations of 9 vectors, each with 9 components. If one vector is a duplicate or a combination of others, the combinations might only fill an 8-dimensional "plane" inside the 9-dimensional space, rendering the matrix singular.

