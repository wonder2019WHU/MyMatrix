# Introduction: MyMatrix 
## Overview
This code provides the template construction and mathematical calculation for the matrix: `Matrix<T>`
+ `T` is the numerical type, such as：`Matrix<int>`, `Matrix<double>`
+ The subscript of row and column starts at 1
+ The matrix elemnts is stored by rows

## Construction/Set
There are three ways to assign values to a matrix:
**1.** **constructor:**  `Matrix<T>(row, col, data)`
**2.** **normal function:**  `set(row, col, data)`
**3.** **operator overload:**  `(row-i, col-j)=data-ij`

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
+ **`getDigs(int i, int j)`**: diagonal of the matrix
+ **`getSimplestRows()`**: simplest form of the matrix based on rows
+ **`getEchelonRows()`**: echelon form of the matrix based on rows
+ **`getSumRows()`**: sum(+) for each row in matrix
+ **`getSumCols()`**: sum(+) for each column in matrix

## Judgment
+  **`isEmpty()`**: determine if it's a empty matrix
+  **`isSquare()`**: determine if it's a square matrix
+  **`isInv()`**: determine if it's a invertible matrix
+  **`isMatchMultiply()`**: determine if it can multiply with matrix-p
+  **`isEqual(Matrix<T>&p)`**: determine if it's equal to Matrix-p
+  **`isAppr(Matrix<T>&p)`**: determine if it's approximately equal to Matrix-p
+  **`isEqualSize(Matrix<T>&p)`**: determine if the size is equal to Matrix-p
+  **`isGreaterSize(Matrix<T>&p)`**: determine if the size is greater than Matrix-p
+  **`isLessSize(Matrix<T>&p)`**: determine if the size is less than Matrix-p
+  **`isZero()`**: determine if it's a matrix which all elements are zero
+  **`isSingle()`**: determine if it's a matrix with only one element
+  **`isVector()`**: determine if it's a vector
+  **`isUnitVector()`**: determine if it's a unit vector
+  **`isUnitOneVector()`**: determine if it's a unit vector like {1,0,0,0,……}
+  **`isInternal(int i, int j)`**: determine if (i, j) is in the matrix

## Calculation
### basic calculation
+ **`operator +(Matrix<T>&p)`**: Matrix-this + Matrix-p, create new matrix
+ **`operator -(Matrix<T>&p)`**: Matrix-this - Matrix-p, create new matrix
+ **`operator *(Matrix<T>&p)`**: Matrix-this * Matrix-p, create new matrix
+ **`operator +=(Matrix<T>&p)`**: Matrix-this + Matrix-p, modify Matrix-this
+ **`operator -=(Matrix<T>&p)`**: Matrix-this - Matrix-p, modify Matrix-this
+ **`operator +(Matrix<T>&p, T num)`**: Matrix-p + num, create new matrix
+ **`operator -(Matrix<T>&p, T num)`**: Matrix-p - num, create new matrix
+ **`operator *(Matrix<T>&p, T num)`**: Matrix-p * num, create new matrix
+ **`operator +(T num, Matrix<T>&p)`**: num + Matrix-p, create new matrix
+ **`operator -(T num, Matrix<T>&p)`**: num - Matrix-p, create new matrix
+ **`operator *(T num, Matrix<T>&p)`**: num * Matrix-p, create new matrix
### advanced calculation
+ **`tp()`**: matrix transpose
+ **`invGJC()`**: matrix inverse, by Gauss-Jordar, pivot in Column
+ **`facLU()`**: matrix decomposition, by LU
+ **`facQR()`**: matrix decomposition, by QR
+ **`orthSMT()`**: matrix orthgonization, by SchMidT
+ **`eigQR()`**: matrix eigenvalue
+ **`solveHomo()`**: basic solutions of homogeneous linear equations
+ **`norm()`**: matrix normalization
+ **`normRows()`**: matrix normalization for each row
+ **`normCols()`**: matrix normalization for each col
### special matrix construction
+ **`creOnes(int row, int _col)`**: row*col matrix, all elements are 1
+ **`creZeros(int row, int _col)`**: row*col matrix, all elements are 0
+ **`creEyes(int index)`**: index*index matrix, all diagonal elements are 0
+ **`creDiags(vector<int>&diags)`**: all diagonal elements are from `diags`
+ **`creVander(vector<T>&vander)`**: vandermonde matrix
+ **`creRotX(T alpha)`**: rotation matrix, by X-axis, with `alpha`, in anticlockwise
+ **`creRotY(T alpha)`**: rotation matrix, by Y-axis, with `alpha`, in anticlockwise
+ **`creRotZ(T alpha)`**: rotation matrix, by Z-axis, with `alpha`, in anticlockwise
+ **`creRot(T alpha, T x, T y, T z)`**: rotation matrix, by unit-norm-vector `{x,y,z}`, with `alpha`, in anticlockwise

## Operation
+ **`exRows(int i, int j)`**: exchange row-i and row-j
+ **`exCols(int i, int j)`**: exchange col-i and col-j
+ **`mpRows(int i, T num)`**: row-i + num
+ **`mpCols(int i, T num)`**: col-j + num
+ **`plRows(int i, int j, T num)`**: row-i + num*row-j
+ **`plCols(int i, int j, T num)`**: col-i + num*col-j
+ **`rpRows(Matrix<T>&rows, int i)`**: replace row-i with `rows`
+ **`rpCols(Matrix<T>&cols, int i)`**: replace col-i with `cols`
+ **`rpBlocks(Matrix<T>&blocks)`**: replace area with blocks from upper-left(0,0)
+ **`rpBlocks(Matrix<T>&blocks, int i, int j)`**: replace area with blocks from upper-left(i,j)
+ **`rpDiags(Matrix<T>&diags)`**: replace diagonal with `diags`
+ **`addRows(Matrix<T>&rows)`**: add `rows` after the last row
+ **`addCols(Matrix<T>&cols)`**: add `cols` after the last col
+ **`insertRows(Matrix<T>&rows, int i)`**: add `rows` after the row-i
+ **`insertCols(Matrix<T>&cols, int i)`**: add `cols` after the col-i
+ **`substractRows(int num)`**: delete the last `num` rows
+ **`substractRows(int num)`**: delete the last `num` cols
+ **`deleteRows(int i)`**: delete row-i
+ **`deleteCols(int i)`**: delete row-i
+ **`deleteRows(int i, int j)`**: delete from row-i to row-j
+ **`deleteCols(int i, int j)`**: delete from row-i to row-j
+ **`mergeRows(Matrix<T>&p1, Matrix<T>&p2)`**: merge Matrix-p1 and Matrix-p2 by rows
+ **`mergeCols(Matrix<T>&p1, Matrix<T>&p2)`**: merge Matrix-p1 and Matrix-p2 by cols
+ **`mergeDiags(Matrix<T>&p1, Matrix<T>&p2)`**: merge Matrix-p1 and Matrix-p2 by diags
+ **`flipRows()`**: filp by rows
+ **`flipCols()`**: filp by cols
+ **`flipDiags()`**: filp by diags

















