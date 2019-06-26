# Introduction: MyMatrix 
## Overview
This code provides the template construction and mathematical calculation for the matrix: `Matrix<T>`
+ `T` is the numerical type, such as：`Matrix<int>`, `Matrix<double>`
+ The subscript of row and column starts at 1
+ The matrix elemnts is stored by rows

## Construction/Set
There are three ways to assign values to a matrix:
**1.** **constructor:**  `Matrix<T>(row, column, data)`
**2.** **normal function:**  `set(row, column, data)`
**3.** **operator overload:**  `(row-i, column-j)=data-ij`

For `data`, the following parameter types can be accepted:
+ **single value**
```C++
int row = 2, int col = 3;
int value = 5;
Matrix<int> mymat(row, col, value);
/*
5 5 5
5 5 5
*/
```
+ **one-dimensional array**
```C++
int row = 2, int col = 3;
int array[6] = {1,2,3,4,5,6};
Matrix<int> mymat(row, col, array);
/*
1 2 3
4 5 6
*/
```
+ **two-dimensional array**
```C++
int row = 2, int col = 3;
int array[2][3] = {{1,2,3},{4,5,6}};
Matrix<int> mymat(row, col, value);
/*
1 2 3
4 5 6
*/
```
+ **vector**
```C++
int row = 2, int col = 3;
vector<int> vec = {1,2,3,4,5,6};
Matrix<int> mymat(row, col, vec);
/*
1 2 3
4 5 6
*/
```
+ **iterator**
```C++
int row = 2, int col = 3;
vector<int> vec = {1,2,3,4,5,6};
Matrix<int> mymat(row, col, vec.begin(), vec.end());
/*
1 2 3
4 5 6
*/
```
+ **input stream**
```C++
int row = 2, int col = 3;
istream is;
is<<1<<2<<3<<4<<5<<6;
Matrix<int> mymat(row, col, is);
/*
1 2 3
4 5 6
*/
```
+ **another matrix**
```C++
int row = 2, int col = 3;
Matrix<int> mymat(row, col, 5);
Matrix<int> mymat2(row, col, mymat);
/*
5 5 5
5 5 5
*/
```

## Get
### basic information
+ **`getRow()`**: the number of rows
+ **`getCol()`**: the number of cols
+ **`getElem()`**: the number of elements
+ **`getElem(int i, int j)`**: the value of element(row-i, col-j)
### advanced information
+ **`getRank()`**: the rank of matrix
+ **`getDet()`**: the determinant of matrix
+ **`getTr()`**: the trace of matrix
+ **`getNormOne()`**: the norm-1 of matrix
+ **`getNormTwo()`**: the norm-2 of matrix
+ **`getNormInf()`**: the infinite norm of matrix
+ **`getCond()`**: the condition number of matrix
+ **`getNonZeroRow()`**: the number of non-zero rows
+ **`getMin()`**: the value of minimum in matrix
+ **`getMax()`**: the value of maximum in matrix
+ **`getMinRow()`**: the row subscript of minimum in matrix
+ **`getMaxRow()`**: the row subscript of maximum in matrix
+ **`getMinCol()`**: the col subscript of minimum in matrix
+ **`getMaxCol()`**: the col subscript of maximum in matrix
+ **`getSum()`**: the sum(+) of all elements
+ **`getProduct()`**: the product(*) of all elements
+ **`getSSQ()`**: the sum(+) of all elements^2
+ **`getRSSQ()`**: the sqrt of `getSSQ()`
### partial matrix
+ **`getRows(int i)`**: row-i of the matrix
+ **`getCols(int i)`**: col-i of the matrix
+ **`getRows(int i, int j)`**: row-i to row-j of the matrix
+ **`getCols(int i, int j)`**: col-i to col-j of the matrix
+ **`getBlocks(int i, int j)`**: area from upper-left(0,0) to lower-right(i,j) of the matrix
+ **`getBlocks(int p, int q, int i, int j)`**: area from upper-left(p,q) to lower-right(i,j) of the matrix
+ **`getBlocks(int p, int q, int i, int j)`**: area from upper-left(p,q) to lower-right(i,j) of the matrix
+ **`getDigs(int i, int j)`**: diagonal of the matrix
+ **`getSimplestRows()`**: simplest form of the matrix based on rows
+ **`getEchelonRows()`**: echelon form of the matrix based on rows
+ **`getSumRows()`**: sum(+) for each row in matrix
+ **`getSumCols()`**: sum(+) for each column in matrix

## Judgment
## Calculation

