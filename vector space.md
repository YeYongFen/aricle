





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

![image](vector_space/vector_space_1.png)

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

![image](vector_space/vector_space_2.png)

## 2.2.Row space ##
**DEFINITION :** The row space of a matrx is the subspace of $R^n$ spanned by the rows.  
The row space of A is $C(A^T)$. It is the column space of $A^T$.

The rows of an $m \times n$ matrix have n components. They are vectors in $R^n$.Transpose the matrix. Instead of the rows of A, look at the columns of $A^T$,same numbers, but now in the column space $C(A^T)$. This row space of A is a subspace of $R^n$.  

**example**   

Describe the row space of A.
$$
A=
\left[\begin{array}{cc} 
1&4\\
2&7\\
3&5\\
\end{array} \right] 
$$

The row space of A is spanned by the three rows of A.This row space
is all of $R^2$


## 2.3. Nullspace ##

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
|**linear dependent**|The columns  are certainly independent|The columns  are certainly dependent , there are $n-m$ free variables |The columns of  matrix A   with full column rank are independent.Because there are n pivots and no free variables. Only $x = 0$ is in the nullspace ||
|**remark** | invertible |  |  | example 4.1|


# Independence, Basis and Dimension #

## Linear Independence ##
**DEFINITION** : The sequence of vectors $v_1...v_n$ is linearly indeendent if the only
combination that gives the zero vector is $0v_1 + 0v_2 + ... + 0v_n$  ,namely, $x_1v_1 + x_2v_2 + ... + x_nv_n = 0$ only happens when all x's are zero.  
There is a direct way to check if a sequence of vectors is dependent. Another way to describe linear dependence is this: "One vector is a combination of the other vector." see the example below


![image](vector_space/vector_space_3.png)

1. If three vectors are not in the same plane, they are independent. No combination of $v_1, v_2, v_3$ in Picture 1 gives zero except $0v_1 + 0v_2 + 0v_3$.  
2. If three vectors $w_1, w_2, w_3$ are in the same plane,The combination $w_1 - w_2 + w_3$ is $(0, 0, 0)$ they are dependent.

**How to fnd that solution to $Ax = 0$ ? The systematic way is elimination.**

$$

A=\left[\begin{array}{cc}
1&0&3\\
2&1&5\\
1&0&3\\
\end{array} \right]
\xrightarrow[  ]{ }
\begin{matrix} \underbrace{
\left[\begin{array}{cc}
1&0&3\\
0&1&-1\\
0&0&0\\

\end{array} \right]
} \\ R\end{matrix}

$$
The solution $x = (-3,1,1)$ was exactly the special solution. It shows how the free column (column 3) is a combination of the pivot columns. That kills independence


**summarization**  
After a sequence of elimination , A is  converted to **R(reduced row echelon form)** , R is a $m \times n$ matric


| m=n | m<n | n<m |
 ------ | ------ | ------ |
|The columns  are certainly independent|The columns  are certainly dependent , there are $n-m$ free variables |The columns of  matrix A   with full column rank are independent.Because there are n pivots and no free variables. Only $x = 0$ is in the nullspace |


## Vectors that Span a Subspace ##

**DEFINITION** A set of vectors spans a space if their linear combinations flll the space.  

**Example 1** $v_1=\left[\begin{array}{cc}1\\0\\\end{array} \right]$ and $v_1=\left[\begin{array}{cc}0\\1\\\end{array} \right]$ span the full two-dimensional space $R^2$.  

**Example 2** $v_1=\left[\begin{array}{cc}1\\0\\\end{array} \right]$ , $v_2=\left[\begin{array}{cc}0\\1\\\end{array} \right]$ , $v_3=\left[\begin{array}{cc}4\\7\\\end{array} \right]$ also span the full space $R^2$ .  

**Example 3** $w_1=\left[\begin{array}{cc}1\\1\\\end{array} \right]$ and $w_2=\left[\begin{array}{cc}-1\\-1\\\end{array} \right]$ only span a line in $R^2$ . So does $w_1$ by itself.  

think of three vectors coming out fom $(0, 0, 0)$ in 3-dimensional space. Mathematically ,there are possibilities:  ①they could only span a line, ②they could span a plane in $R^3$,③ they could  span could span all of $R^3$

## A Basis for a Vector Space  ##
Two vectors can't span all of $R^3$ , even if they are independent. Four vectors can't be independent, even if they span $R^3$. We want enough independent vectors to span the space (and not more). A "**basis**" is just right.  

**DEFINITION:** A basis for a vector space is a sequence of vectors with two properties:The basis vectors are **linearly independent** and they **span the space**.  

The **pivot columns** of A are a **basis** for **its column space**,but  not the pivot rows of its echelon for R.  
The **pivot rows** of A are a **basis** for **its row space**. So are the pivot rows of its echelon for R.



**example**  
Find bases for the column and row spaces of matrix A
$$
A=\left[\begin{array}{rrrrr}
1&1&-2&0&-1\\
1&2&0&-4&1\\
0&1&3&-3&2\\
2&3&0&-2&0\\
\end{array} \right]
\xrightarrow[  ]{ }
\left[\begin{array}{rrrrr}
1&1&-2&0&-1\\
0&1&2&-4&2\\
0&0&1&1&0\\
0&0&0&0&0\\
\end{array} \right]
=R
$$
And in fact,these rows still span the same space that the initial four rows did.Because when you do elimination,all that you're doing is recombining your rows by doing linear combinations of them.  
So the basis for the row space is  $(1,1,-2,0,-1)$ , $(0,1,2,-4,2)$ and  $(0,0,1,1,0)$ .similarly we can use the first three rows,but it's not recommended.  Sometimes in elimination,you have to switch rows ,Thus you have to keep track of which row you switched to.So why don't we use the safer and simpler one.  
We can no longer use first three columns of R as the basis for column space of A.Because when I did elimination ,I changeed the columns space. The column spaces of A and R are diﬀerent. Their bases are diﬀerent.But By the upper R,we keno that the privots are in first ,second and third columns. So the $(1,1,0,2)$ , $(1,2,1,3)$ and  $(-2,0,3,0)$ are the basis for the column space of A  



**Question** Given four vectors in $R^5$, how do you find a basis for the space they span? 
(we use the example above: find the basis for the space those vectors $(1,1,-2,0,-1)$,$(1,2,0,-4,1)$,$(0,1,3,-3,2)$,$(2,3,0,-2,0)$ span)

*First answer* Make them the rows of A, and eliminate to find the nonzero rows of R.  
$$
A=\left[\begin{array}{rrrrr}
1&1&-2&0&-1\\
1&2&0&-4&1\\
0&1&3&-3&2\\
2&3&0&-2&0\\
\end{array} \right]
\xrightarrow[  ]{ }
\left[\begin{array}{rrrrr}
\mathbf{1} &1&-2&0&-1\\
0&\mathbf{1}&2&-4&2\\
0&0&\mathbf{1}&1&0\\
0&0&0&0&0\\
\end{array} \right]
=R
$$



*Second answer* Put the five vectors into the columns of A. Eliminate to fnd the pivot columns (of A not R). Those pivot columns are a basis for the column space.  

$$
A=\left[\begin{array}{rrrrr}
1&1&0&2\\
1&2&1&3\\
-2&0&3&0\\
0&-4&-3&-2\\
-1&1&2&0\\
\end{array} \right]
\xrightarrow[  ]{ }
\left[\begin{array}{rrrrr}
\mathbf{1}&1&0&2\\
0&\mathbf{1}&1&1\\
0&0&\mathbf{1}&2\\
0&0&0&0\\
0&0&0&0\\
\end{array} \right]
=R
$$

## Dimension of a Vector Space ##
All bases for a vector space contain the same number ovectors,the number is the "**dimension**" of the space  
Let's recall the example. The basis for the row space of is  $(1,1,-2,0,-1)$ , $(0,1,2,-4,2)$ and  $(0,0,1,1,0)$ ,so the row space has dimension 3. The $(1,1,0,2)$ , $(1,2,1,3)$ and  $(-2,0,3,0)$ are the basis for the column space of A  , so the column space has dimension 3



