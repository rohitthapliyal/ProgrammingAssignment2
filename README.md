
+	# creating the matrix during the call of makeCacheMatrix()
+	a <- makeCacheMatrix( matrix(c(1,2,12,13), nrow = 2, ncol = 2) );
+
+	summary(a);
+	#>              Length Class  Mode    
+	#> setMatrix    1      -none- function
+	#> getMatrix    1      -none- function
+	#> cacheInverse 1      -none- function
+	#> getInverse   1      -none- function
+
+	a$getMatrix();
+	#>      [,1] [,2]
+	#> [1,]    1   12
+	#> [2,]    2   13
+
+	cacheSolve(a)
+	#> [,1]        [,2]
+	#> [1,] -1.1818182  1.09090909
+	#> [2,]  0.1818182 -0.09090909
+
+	# the 2nd time we run the function to get the cached value
+	cacheSolve(a)
+	#> getting cached data
+	#> [,1]        [,2]
+	#> [1,] -1.1818182  1.09090909
+	#> [2,]  0.1818182 -0.09090909
+
+Alternatively, the matrix can be created after calling a `makeCacheMatrix`
+without arguments.
+	source("path/to/file/assessment3.R")
+	
+	# call makeCacheMatrix without arguments
+	a <- makeCacheMatrix();
+	summary(a);
+	#>              Length Class  Mode    
+	#> setMatrix    1      -none- function
+	#> getMatrix    1      -none- function
+	#> cacheInverse 1      -none- function
+	#> getInverse   1      -none- function
+
+	# creating a square matrix (reason `solve` only handles square matrices )
+	a$setMatrix( matrix(c(1,2,12,13), nrow = 2, ncol = 2) );
+	a$getMatrix();
+	#>      [,1] [,2]
+	#> [1,]    1   12
+	#> [2,]    2   13
+
+	cacheSolve(a)
+	#> [,1]        [,2]
+	#> [1,] -1.1818182  1.09090909
+	#> [2,]  0.1818182 -0.09090909
+
+	# the 2nd time we run the function, we get the cached value
+	cacheSolve(a)
+	#> getting cached data
+	#> [,1]        [,2]
+	#> [1,] -1.1818182  1.09090909
+	#> [2,]  0.1818182 -0.09090909
+
