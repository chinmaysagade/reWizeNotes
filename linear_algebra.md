### What is a vector:   
Physicist: Something which has mangnitude and direction.  
Computer Science:  Ordered list of numbers (a record) (houses as 2-d vector of price and sq.footage).    
Mathematician:   Anything which can be added and scaled according to vector laws.   



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
![alt text](images/pca.png)
