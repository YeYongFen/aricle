


# 1. Vector Space #

$R^n$ is a n-dimensional space , which contains all real column vectors with n components .

If v and w are in a **vector space S**  , every combination **cv + dw** must be in S 
(*S is   $R^2$*)


# 2. Subspace #
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


## 2.1. Column Space ##
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

## 2.2. Nullspace ##

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

# 3. Solve $Ax=0$ #

## 3.1. $Ux=0$ ##
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

## 3.2. $Rx=0$ ##

I still take the matrix above for example

These steps bring us to the best matrix R
```
1. Produce zeros above te pivots. Use pivot rows to eliminate upward in R
2. Produce ones in the pivots. Divide the whole pivot row by its pivot.
```

$$
U=
\left[\begin{array}{cc}
1&2&2&2\\
0&0&2&4\\
0&0&0&0\\
\end{array} \right]
\xrightarrow[  ]{r_1-r_2}
\left[\begin{array}{cc}
1&2&0&-2\\
0&0&2&4\\
0&0&0&0\\
\end{array} \right]
\xrightarrow[]{r_2/2}
\left[\begin{array}{cc}
1&2&0&-2\\
0&0&1&2\\
0&0&0&0\\
\end{array} \right]
=R
$$

The right-hand side R is the **reduced row echelon form** of A  
**The pivot columns of R contain identity matrix I** ,so the number under and over the pivot must be zero,just like the third column in matrix R  $\left[\begin{array}{cc} 0\\ 1\\ 0\\ \end{array} \right]$  



$$
Rx=
\left[\begin{array}{cc}
1&2&0&-2\\
0&0&1&2\\
0&0&0&0\\
\end{array} \right]
\left[\begin{array}{cc}
x_1\\
x_2\\
x_3\\
x_4\\
\end{array} \right]
\xrightarrow{exchange \  col2 \ and \ col3 }
\left[\begin{array}{cc}
1&0&2&-2\\
0&1&0&2\\
0&0&0&0\\
\end{array} \right]
\left[\begin{array}{cc}
x_1\\
x_3\\
x_2\\
x_4\\
\end{array} \right]
\\
\Rightarrow{ }
\left[\begin{array}{cc}
I &F\\
0 & 0\\
\end{array} \right]
\left[\begin{array}{cc}
x_1\\
x_3\\
\hline
x_2\\
x_4\\
\end{array} \right]
=0
\Rightarrow{ }
I
\left[\begin{array}{cc}
x_1\\
x_3\\
\end{array} \right]
=
-F
\left[\begin{array}{cc}
x_2\\
x_4\\
\end{array} \right]
\\
\Rightarrow{ }
\left[\begin{array}{cc} 
1&0\\
0&1\\
\end{array} \right]
\left[\begin{array}{cc}
x_1\\
x_3\\
\end{array} \right]
=
\left[\begin{array}{cc} 
-2&2\\
0&-2\\
\end{array} \right]
\left[\begin{array}{cc}
x_2\\
x_4\\
\end{array} \right]
$$

 In the example above , I make $I=\left[\begin{array}{cc} 1&0\\ 0&1\\  \end{array} \right]$ and $F=\left[\begin{array}{cc} 2&-2\\ 0&2\\  \end{array} \right]$  

From reduced system $Rx = 0$ , it is much easier to find The
special solutions .  


$$
R=
\left[\begin{array}{cc}
I &F\\
0 & 0\\
\end{array} \right]
\ \ \ 
N=
\left[\begin{array}{cc}
-F\\
I\\
\end{array} \right]
$$

It's easy to prove that $RN=0$ , and N = $\left[\begin{array}{cc} -2 & 2\\ 0 & -2\\ 1 & 0\\ 0 & 1\\ \end{array} \right]$ . Then we exchange the column 2 and column 3 . Now we get the special solutions $\left[\begin{array}{cc} -2 \\ 1 \\0 \\ 0\\ \end{array} \right]$ and $\left[\begin{array}{cc} 2 \\ 0 \\-2 \\ 1\\ \end{array} \right]$  
So the solutions for $Ax=0$ is that:  
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


  

   
**example 2**  



$$
A=\left[\begin{array}{cc}
1&2&3\\
2&4&6\\
2&6&8\\
2&8&10\\
\end{array} \right]
\xrightarrow[  ]{ }
\begin{matrix} \underbrace{
\left[\begin{array}{cc}
1&2&3\\
0&2&2\\
0&0&0\\
0&0&0\\
\end{array} \right]
} \\ U\end{matrix}
\xrightarrow[  ]{ }
\begin{matrix} \underbrace{
\left[\begin{array}{cc}
1&0&1\\
0&1&1\\
0&0&0\\
0&0&0\\
\end{array} \right]
} \\ R\end{matrix}
\xrightarrow[]{F=\left[\begin{array}{cc}1\\1\\\end{array}\right]\ \ I=\left[\begin{array}{cc}1&0\\0&1\\\end{array}\right]}
\left[\begin{array}{cc}
I&F\\
0&0\\
\end{array} \right]
\\
\\\\
N=
\left[\begin{array}{cc}
-F\\
I\\
\end{array} \right]
\\
x =
\left[\begin{array}{cc}
x_1\\
x_2\\
\hline
x_3\\
\end{array} \right]
=
\left[\begin{array}{cc}
-F\\
I\\
\end{array} \right]
=
\left[\begin{array}{cc}
-1\\
-1\\
0 \\
\end{array} \right]
$$

The solution of $Ax=0$ is $x=c*\left[\begin{array}{cc}-1\\-1\\1 \\\end{array} \right]$


**conclusion**
```
There are two methods to solve Ax=0
1、converted the Ax=0 to Ux = 0 through elimination ,and  then compute the special solution by back substitition
2、converted the Ax=0 to Rx = 0 through elimination ,and  then find the special solution by RN=0
```


# 4. Solve  $Ax=b$ #

**first example**

$$
A=
\left[\begin{array}{cc}
1&3&0&2\\
0&0&1&4\\
1&3&1&6\\
\end{array} \right]
\left[\begin{array}{cc}
x_1\\
x_2\\
x_3\\
x_4\\
\end{array} \right]
=
\left[\begin{array}{cc}
1\\
6\\
7\\
\end{array} \right]
\Rightarrow
\begin{matrix} \underbrace{
\left[\begin{array}{cccc|c}
1&3&0&2&\mathbf{1}\\
0&0&1&4&\mathbf{6}\\
1&3&1&6&\mathbf{7}\\
\end{array} \right]
} \\  augment \ matrix \end{matrix}
=
\left[\begin{array}{c|c}
A&\mathbf{b}\\
\end{array} \right]
$$

After several elimination operations, 

**Gauss elimination** 
$$
\left[\begin{array}{cc}
A&\mathbf{b}\\
\end{array} \right]
=
\left[\begin{array}{cccc|l}
1&3&0&2&\mathbf{b_1}\\
0&0&1&4&\mathbf{b_2}\\
1&3&1&6&\mathbf{b_3}\\
\end{array} \right]
\xrightarrow[]{}
\left[\begin{array}{cccc|l}
1&3&0&2&\mathbf{b_1}\\
0&0&1&4&\mathbf{b_2}\\
0&0&0&0&\mathbf{b_3-b_2-b_1}\\
\end{array} \right]
$$

Only and if $b_3=b_2+b_1$ , $Ax=b$ is solvable

### 4.1. Complete solution ###
First set two free variables $x_2=x_4=0$ ,then the privot variable $x_1=1$ and $x_3=6$ , so the $x_{particular} = (1,0,6,0)$ is a particular solution for $Ax=b$  
second we find out the  solutions for Ax=0 is that $x_{nullspace}  =   c_2 \left[\begin{array}{cc} -3\\1\\0\\0\\\end{array} \right]+c_4\left[\begin{array}{cc}-2\\0\\-4\\1\\\end{array} \right]$

So the complete solution is that:


$$
x=x_p+x_n=
\left[\begin{array}{cc} 
1\\
0\\
6\\
0\\
\end{array} \right]
+
c_2 
\left[\begin{array}{cc} 
-3\\
1\\
0\\
0\\
\end{array} \right]
+
c_4
\left[\begin{array}{cc}
-2\\
0\\
-4\\
1\\
\end{array} \right]
$$

The complete solutions of $Ax=b$  form a flat plane that go through $x_{particular}$  in $R^4$ . But the solutions is not a subspace .It just like that the subspace $x_n$ is shifted away from the origin until go through $x_{particular}$ .It doesn't contain zero.



# 5. row column rank #

## 5.1. Full Column Rank ##

**example**
$$
A=
\left[\begin{array}{rr}
1&1\\
1&2\\
-2&-3\\
\end{array} \right]
and \
b=
\left[\begin{array}{rr}
b_1\\
b_2\\
b_3\\
\end{array} \right]
$$  
  
$$
\left[\begin{array}{rr|r}
1&1&b_1\\
1&2&b_2\\
-2&-3&b_3\\
\end{array} \right]
\xrightarrow[]{}
\left[\begin{array}{rr|l}
1&1&b_1\\
0&1&b_2-b_1\\
0&-1&b_3+2b_2\\
\end{array} \right]
\xrightarrow[]{}
\left[\begin{array}{rr|l}
1&0&2b_1-b_2\\
0&1&b_2-b_1\\
0&0&b_3+b_2+b_1\\
\end{array} \right]
$$

If $b_1+b_2+b_3=0$ ,$Ax=b$ is solvable. Or there is no solutions.

Supposing the equation is solvable.
This example has no free variables since $n - r = 2 - 2$. Therefore no special solutions.
The nullspace solution is $X_n = 0$. The particular solution to $Ax = b$ and $Rx = d$ is at the top of the final column d.**The only solution is that:**
$$
x=x_p+x_n=
\left[\begin{array}{l}
2b_1-b_2\\
b_2-b_1\\
b_3+b_2+b_1(=0)\\
\end{array} \right]
+
\left[\begin{array}{cc} 
0\\
0\\
0\\
\end{array} \right]
$$

A is a typical example to explain  full column rank.**A has full column rank**
Every column has a pivot. The rank is r = n. The matrix is tall and thin (m $\geq$ n).  
*(Row reduction puts I at the top, when A is reduced to R with rank n:)*

**Full Column Rank**
$$
R=
\left[\begin{array}{cc} 
I\\
0\\
\end{array} \right]
=
\left[\begin{array}{cc} 
{n\ by\ n\ identity\ matrix} \\
{m-n\ rows\ of\ zero}
\end{array} \right]
$$

**conclusion**

```
Every matrix A with full column rank (r = n) has all these properties:
1. All columns of A are pivot columns.
2. There are no free varables or special solutions.
3. The nullspace N(A) contains only the zero vector x = 0.
4. If Ax = b has a solution (it mght not) then it has only one solution
```

## 5.2. Full Row Rank ##

**example $Ax=b$**  
$$
\left[\begin{array}{rrrr}
1&1&1\\
1&2&-1\\
\end{array} \right]
\left[\begin{array}{rrrr}
x_1\\
x_2\\
x_3\\
\end{array} \right]
=
\left[\begin{array}{rrrr}
3\\
4\\
\end{array} \right]
$$

$$
\left[\begin{array}{rrr|r}
1&1&1&3\\
1&2&-1&4\\
\end{array} \right]
\xrightarrow[]{}
\left[\begin{array}{rrr|r}
1&1&1&3\\
0&1&-2&1\\
\end{array} \right]
\xrightarrow[]{}
\left[\begin{array}{rrr|r}
1&0&3&2\\
0&1&-2&1\\
\end{array} \right]
=
\left[\begin{array}{r|r}
R&d\\
\end{array} \right]
$$

we set free variable $x_3 = 0$,$x_{particular}$ comes directly from d on the right side: $x_p = (2, 1, 0)$.  
From R ,we know that $x_{nullspace}  =   c_2 \left[\begin{array}{cc} -3\\2\\1\\\end{array} \right]$  

**Complete solution**
$$
x=x_p+x_n=
\left[\begin{array}{cc} 
2\\
1\\
0\\
\end{array} \right]
+
c_2 
\left[\begin{array}{cc} 
-3\\
2\\
1\\
\end{array} \right]
$$

A matrix has full row rank  $r = m$,and $n\gt\ m$ ,every row has a pivot. No matter what b is,the solutions for $Ax=b$ must exit

**Every matrix A with full row rank (r = m) has all these properties:**

1. All rows have pivots, and R has no zero rows.
2. $Ax = b$ has a solution for every right side b.
3. The column space is the whole space $R^m$.
4. There are $n - r = n - m$ special solutions in the nullspace of A.


## summarization ##
| | r=m=n | r=m<n | r=n<m | r<m,r<n |
|------ | ------ | ------ | ------ |------ |
|**shape** | Square | Short and wide | Tall and thin | Not full rnk |
| **solutions**| one solutions | &infin; solutions | 0 or 1 solution | 0 or &infin; solutions |
|**reduced R** | $\left[\begin{array}{cc} I\\\end{array} \right]$ | $\left[\begin{array}{cc} I&F\\\end{array} \right]$ | $\left[\begin{array}{cc} I\\0\\\end{array} \right]$| $\left[\begin{array}{cc} I&F\\0&0\\\end{array} \right]$ |
|**remark** | invertible |  |  | example 4.1|

