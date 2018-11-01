


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
\end{array}\right]
$$

![image](https://raw.githubusercontent.com/yyf1994gggg/aricle/master/images/vector_space_2.png)

## Nullspace ##

**The nullspace $N(A)$ consist of all solutions to $Ax= 0$**.  
Pretend A is a $m*n$ matrix , those vectors $x$ are in $R^n$ ,so the nullspace is a subspace of $R^n$ . However , the column space $C(A)$ is a subspace of $R^m$

The m by n matrix A can be square or rectangular. The right hand side is $b= 0$. One immediate solution is $x = 0$.  
 1、For invertible matrices this is the only solution.   
 2、For other matrices, not invertible, there are nonzero solutions to $Ax= 0$. Each solution x belongs to the nullspace of A

**Check that the solution to $Ax=b$  always give a a subspace**  
If $Av=0$ and $Aw=0$  
Then $A(v+w)=0$  -----  *(associative law)*  
So  $(v+w)\subseteq   N(A)$
 Similarly  $A(cx) = c*0$ for the reason that the scalar can move outside and I get $c*Ax =c* 0$  
 So  $cv\subseteq   N(A)$


**If the right-hand side b is not equal to 0, namely $Ax=b≠0$ ,will these solution form a vector space ?**   
**NO**  
$\because$ $A*0≠0$  
$\therefore$  zero not in the solutions to $Ax=b$
$\therefore$  so solutions can not be a vector space

## Solve $Ax=0$ ##  
**example**  
solve  $Ax=0$ or $N(A)$  

$$
\left[\begin{array}{cc}
1&2&2&2\\
2&4&6&8\\
3&6&8&10\\
\end{array} \right]
$$
We can apply elimination to the solve linear equations $Ax = 0$. By the way, **elimination can not change the solutions $x$**


$$
A=
\left[\begin{array}{cc}
1&2&2&2\\
2&4&6&8\\
3&6&8&10\\
\end{array} \right]
\xrightarrow[ -3r_1+r_3 ]{-2r_1+r_2}
\left[\begin{array}{cc}
1&2&2&2\\
0&0&2&4\\
0&0&2&4\\
\end{array} \right]
\xrightarrow[]{-r_2+r_3}
\left[\begin{array}{cc}
1&2&2&2\\
0&0&2&4\\
0&0&0&0\\
\end{array} \right]
=U
$$

$U$ means **row-echelon form**, column one $\left[\begin{array}{cc}1\\0\\0\\ \end{array} \right]$and column three $\left[\begin{array}{cc} 2\\ 2\\  0\\ \end{array} \right]$are **pivot columns** .  

column two
$\left[\begin{array}{cc}2\\0\\0\\\end{array} \right]$ and column four $\left[\begin{array}{cc}2\\4\\0\\\end{array} \right]$
are **free columns** .  
For the fee variables $x_2$ and $x_4$.  
First   $x_2=1$ and $x_4=0$ , then $x_1=-2$ , $x_3=0$  
Second  $x_2=0$ and $x_4=1$ , then $x_1=2$ , $x_3=-2$

So the 
$\left[\begin{array}{cc} -2\\ 1\\  0\\ 0\\ \end{array} \right]$ and $\left[\begin{array}{cc} 2\\ 0\\  -2\\ 1\\\end{array} \right]$
 are the special solutions to $Ux=0$ , and the special solutions to $Ax=0$ as well.They have the same solutions.

The null space $N(A)$ contains all the combination of the special  solution ,
 so the solution to $Ax=0$ ($Ux=0$) is that  
  *($c_1$ , $c_2$ are any real number)*

 $$
 c_1
\left[\begin{array}{cc} 
-2\\
1\\
0\\
0\\
\end{array} \right]
+
c_2
\left[\begin{array}{cc}
2\\
0\\
-2\\
1\\
\end{array} \right]
$$

**question1:how many special solutions are there?**  
Each of free variables corresponds to a special solution

**question2:How many free variables are there ?**  
 
```
for a matrix , that's M rows,N columns  with rank R. Then it  has (N-R) free variables  

N columns mean N variables  
The rank R is the number of pivot . 
```


In this case, R is 2 , N is 4 , So there are 2 free variables. 
