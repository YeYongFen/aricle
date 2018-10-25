


## what is vector space ##
$R^n$ is a n-dimensional space , which contains all real column vectors with n components .

If v and w are in a **vector space S**  , every combination **cv + dw** must be in S  
 (*S is   $R^2$*)


## what is subspace ##
A **subspace** of S must satisfy two requirements:
( *If v and ware vectors in the subspace and c is an scalar*)  
```
(i) v + w is in the subspace  
(ii) cv is in the subspace
```
*In other words, the set of vectors is "**closed**" under addition v + w and multiplication cv
(and dw)*


**Notice: Ever subspace contains the zero vector**


**example 1**  
Find all subspace in $R^2$

![image](https://raw.githubusercontent.com/yyf1994gggg/aricle/master/images/vector_space_1.png)

look at the picture above,if I multiply the vector on the dash line by zero.Then I will get (0,0),which is not in the dash line obviously.  

So the subspaces of $R^2$ consist of
1. $R^2$ counts as a subspace of itself
2. any line through zero (0,0) 
3. zero point


## Column Space ##
When we are trying to solve $Ax=b$. If A is not invertible, the system is not solvable for every
b. We only want to describe the good right sides b . Those good b's form the "column space" of A ,written as $C(A)$

**DEFINITION** The column space consists of **all linear combinations of the column** .
The combinations are all possible vectors Ax. They fill the column space $C(A)$

To solve $Ax=b$ is to
express bas a combination ofthe columns . The right side b has to be in the column space produced by A on the left side, or no solution. In another word , **The system $Ax= b$ is solvable if and only b is in the column space of A**

**example**  
Here is a 3 by 2 matrix A. The column space of all combinations of the two columns flls up a plane in $R^3$. $Ax = b$ is
solvable when b is on that plane. Then b must be a combination of the columns

$$
\left[\begin{array}{cc} 
1&0\\ 
4&3\\ 
2&3\\ 
\end{array} \right] 
\left[ \begin{array}{c} 
x_1\\
x_2\\ 
\end{array} \right] 
=\left[ \begin{array}{c} 
b_1\\ 
b_2\\ 
b_3\\ 
\end{array}
\right]
$$

![image](https://raw.githubusercontent.com/yyf1994gggg/aricle/master/images/vector_space_2.png)