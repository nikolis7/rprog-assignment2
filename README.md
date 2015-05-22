# rprog-assignment2
Create a function that caches the inverse of a matrix

makeCacheMatrix<-function(x=matrix()) {
  
    i<-NULL
    # i am setting the value of the matrix
    set <- function(y) {
      
        x<<-y
        i<<-NULL
      
    }
    # getting the value of the matrix
    get <- function() {
            x }
    # setting the value of the inverted matrix with solve    
    setinv<- function(solve) {
            i<-solve }
    # getting the value of the inverted matrix 
    getinv<- function() {
            i }
    # put it all together in a list 
    list(set=set, get=get,
         setinv=setinv,
         getinv=getinv)
  
}

cacheSolve <- function(x,...) {
  
  i<-x$getinv() 
  # if allready inverse matrix exists getting cached data
  if(!is.null(i)) {
      message("getting cached data")
      return(i)
      
  }
  # if there is not any value for inverse matrix in cache calculate 
  # the inverse matrix and set the value in the cache
  
  data<-x$get()
  i<-solve(data)
  x$setinv(i)
  
}


