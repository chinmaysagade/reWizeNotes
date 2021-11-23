### Sets of Interest in Linear Algebra.   
Z (Zahlen, german for numbers): Set of integers : -1,0,1,2,3,4    
Q : Quotient: Set of rational numbers:  1/2 , 3/4. -5/2.   
R : Set of real numbers :  e, pi, 1, ,2 , 4.5, \sqrt(2).     
C:  Set of complex numbers    

### What is a Vector:   
Physicist: Something which has mangnitude and direction.  
Computer Science:  Ordered list of numbers (a record) (houses as 2-d vector of price and sq.footage).    
Mathematician:   Anything which can be added and scaled according to vector laws.   

In linear algebra: Vectors are always rooted at the origin. Origin is root of all vectors.      
The coordinates are written vertically [ 2/3 ]  to avoid confusing with a point like (2,3) . 

### Linear and Affine Vectors and Transformations:
When we are discussing linear algebra, we are strictly in the domain where vectors are rooted at origing and the transformations are not translating the vectors from origin. Those vectors and transformations are affine, a superset of linear transformations.     
For instance, y = mx+b is not a linear transformaiton since   
Transforming first and then adding:  y(x1+x2) =  m(x1)++b+m(x2)+b = m(x1+x2)+2b .   
Adding first and then transforming:  y(x1+x2) =  m(x1+x2)+b.   


### Gradient as Vectors:    
The gradient of a vector valued function f:R^n to R is the vector of the partial derivatives of f:  

### Support of a Vector:    
support of a vector is the number of non-zero elements in that vector.    

### Vector valued functions:   
Functions of one or more numbers or vectors to an ouput vector.    
think of scalar as one-dimensional vector, so the function can take in a scalar as well.    
example:   
f(a,b) =  (a+b, a-b), so that.  f(-2,1) = (-2+1, -2-1) = (-1,-3).  

### Dot or Scalar Product:  v.w  
The dot product is a vector-valued function that takes two vectors and yields a scalar.    
In real vector spaces, multiply the corresponding entries in each vector and then add the product to get the scalar value.    
x^Ty = dot(x,y) = xoyo+x1y1+.....+xnyn.    

If the dot product is zero, the vectors are orthogonal.     
In real space, dot product is commutative.   

### Dot product equations.  
u.v = u1v1 + u2v2 + .... + u3v3    
Law of cosines:   
|u-v|^2 = |u|^2 + |v|^2 - 2|u||v|cos0      
|u-v|^2 = |u|^2 + |v|^2 - 2 u.v    
hence, u.v = |u| |v| cos0 

### Span of vectors:   
Set of all possible points you can reach by any pair of vectors is called it's span.   
OR.  
Span is all possible linear combination of basis vectors.   

### linearly dependent vectors:    
Vectors which can be described as linear combinations of other vectors.   


### Eigen Vector 
Vector which when multiplied by the transformation matrix get's scaled by a constant factor.   
That constant factor is called as **Eigen value**.

### How PCA uses eigen vector and values. 
To reduce dimension, instead of original dimensions as axes, eigen vector along the maximum variance is calculated and individual components are projected down to the eigen vector.     
Say, we have a dataset with ‘n’ predictor variables. We center the predictors to their respective means and then get an n x n covariance matrix. This covariance matrix is then decomposed into eigenvalues and eigenvectors.  
Covariance matrix (also called as dispersion matrix or variance-covariance matrix) is a matrix whose element in the i,j position is the covariance between the i-th and j-th element (feature) of a random vector (A random vector is a random variable with multiple dimensions).  
So, PCA is a method that:  
Measures how each variable is associated with one another using a Covariance matrix. 
Understands the directions of the spread of our data using Eigenvectors. 
Brings out the relative importance of these directions using Eigenvalues. 
![alt text](https://raw.githubusercontent.com/chinmaysagade/reWizeNotes/main/images/pca.png)

### What is a Tensor:    
Tensors are multi-indexed arrays of numbers, or functions, that transform according to certain rules under a change of coordinates.    
Tensor Orders:   
0-tensor:  scalar.  
1-tensor:  vector.   
2-tensor:  matrix.  
3-tensor:  a 3d cube of numbers.

#### Vector Operations:    
1) Addition:   can only be done on vectors with equal dimensions. Is associative as well as commutatitve.      
2) Multiplication by scalar:   They scale the vector.   

#### Linear Combination:    
A linear combination of u and v is a vector au+bv where a and b are scalers.   
All vectors can be represented as linear combination of unit vectors.   

Superposition can be represented by a linear combination of states.   
![alt text](https://raw.githubusercontent.com/chinmaysagade/reWizeNotes/main/images/spinors.jpeg)
### Vector Norm:   
Norms are used to determine the magnitude or length of the vector.   
The most common norm is the L^2 norm, which is the cartesian distance of the vector.    
L^1 : Manhattan distance.    
L^2 : Euclidean (pythagorean).   

A norm is a vector valued function that gives us some sense of the magnitude of a vector. It can also allow us to compare two or more vectors.   

![alt text](https://raw.githubusercontent.com/chinmaysagade/reWizeNotes/main/images/norm.png)   
L2 norm is the dot product with itself !!!   

L1 norm :  [u1 u2]  = |u1| + |u2|.  

L1 norm is always greater than L2 norm.   

Both L1 and L2 can be used to improve results in machine learning. L1 and L2 regularization.    

### L1 and L2 regularization:  
L1 and L2 norm regularization encourages "simple" solutions.  Add burden to convergence process and avoid overfitting.
L2 norm (ridge regression) : penalizes B that are far from the origin in the Euclidean space.=, leading to many small values. No single affects the output very much.    
L1 norm (lasso regression) : prefers B to be either large or exactly 0, leading to sparse solutions (many zeros). Only a few features have any impact.  
Performance of  model on the test data would always peak after a few epochs and would then start degrading, i.e. our model would quickly start to overfit to the training data. Overfitting happens in every single machine learning problem.


### Algebraic aspects of dot product:   
||u|| = u.u.    
(au) . v = a(u.v).   
u.v = v.u.   
(u+v).w = u.w + v.w.   

Geometric View: Law of cosines:     
|| v - u ||^2 = || v ||^2 - 2 ||v||.||u|| cos \theta + || u || ^2.    
v.u= ||v|| ||u|| cos \theta


### Matrix:    
A matrix is a rectangular array of numbers, symbols or expressions, arranged in rows and columns.  
Items in column vector were called components , whereas items in matrix are called elements.   
Denoted by mxn , where m is rows.   
Matrix can be viewed as built up of vectors as columns.   

Matrix Addition:
Need to be of same dimension.   

Special Matrices:    
Zero Matrix.  
Identity Matrix. 
Symmetric :  if transpose and matrix are same :  A = A^T

Transpose of a matrix:    
Just flip the indices ,  a^T (i,j). = a (j,i)         

###  Non Square Matrices: 
linear transformation between vector spaces of different dimensions.


### Matrix multiplication:    
TBD 

### Determinant. 
Are scalar quantity associated with every Square matrix (which keeps the dimension on vector space constant).   
Is a vector function which encodes algebraic and geometric information.    

Algebraic Information:    
det(A) == 0 mean columns of A are linearly dependent, A is not invertible, the null space of A is non-trivial.     
det(AB) = det(a)det(B).  
det(A+B) != det(A)+det(B). 
det(A^T) = det(A). 
det(A^-1) = 1/ det(A).    

Geometric Information:    
They can be thought of as directed volume of a unit parallelepiped after the linear transformation.  
The sign pf the determinant is positive iff the linear transformation preserves orientation.  


### Rank of a Matrix :    
Rank of a matrix is number of linear independent column vectors in the matrix.   

### How To build a Vector Space:    

Cartesian Products of Sets:   Set of ordered pairs of element of S and T.  
   S x T = { (s,t) :s E S and t E T }.   

- Set :  Collection of unique objects (unordered)
- Group : A set with an operation that meets 4 conditions (closure,assoc, identity, inverse).The operation is typically addition
- Abeliean Group: a group with a commutativity of the operation.
- Ring: An abeliean Group with another operation(typically multiplication) that is assoc, had identify and is distributive 
- Field: A commutative ring with a multiplicative inverse of each non-zero element of the ring.
- Vector Space: An abelian group equipped with a field action


### Isomorphism -- Coordinate tuples vs F^n Vectos.   
Once a basis is picked, every vector is represented by a tuple of coordinates.   
- The tuples are elements of F^n, the cartesian product space of the scalar field. Also, F^n is a vector space in itself.   
- The F^n vector space is isomorphic to the original vector space, which often misleads us to think that vectors are just tuples of scalars (numbers).   
- The mapping of the vectors to it's coordinate tuples is called an isomorphism. There are many such mappings, one for each basis of the vector space.   




