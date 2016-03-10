UECM3033 Assignment #2 Report
========================================================

- Prepared by: Chua Khang Hui
- Tutorial Group: T2

--------------------------------------------------------

## Task 1 --  $LU$ Factorization or SOR method

The reports, codes and supporting documents are to be uploaded to Github at: 

[https://github.com/ChuaKhangHui/UECM3033_assign2](https://github.com/ChuaKhangHui/UECM3033_assign2)

Explain your selection criteria here.

1. Check strictly diagonally dominant Matrix

-	if (Matrix A is strictly diagonally dominant)

--		then Solve it by LU

-	else

--		continue to 2

2. Check possitive Definite 

-	if (Matrix A is possitive definite and all diagonal element are possitive)

--		then Solve it by SOR

-	else

--		Solve it by LU
		
Explain how you implement your `task1.py` here.

Matrix A is classified as strictly diagonally dominant matrix when (2* diagonal element > sum of row) for all rows.

In python: 

'	temp = 2 * np.diag(A) > np.sum(np.abs(A),1)'
'    result = temp.all()                       '

If the result is true, then A is a strictly diagonally dominant Matrix

Matrix A is classified as strictly possitive definite matrix when  np.linalg.cholesky(A) return no error.

If error received, slove it by LU.
else no error received, then check for possitive diagonal element.
If all element is possitive, then we solve it by SOR, else, slove it by LU.


---------------------------------------------------------

## Task 2 -- SVD method and image compression

Put here your picture file (KB.jpg)

![KB.jpg](KB.jpg)

How many non zero element in $\Sigma$?

For a $M \times N$ sized image, the number of zeros in $\Sigma$ will be $(N \times M - N)$ 

Put here your lower and better resolution pictures. Explain how you generate these pictures from `task2.py`.

The image with lower resolution
![KB_lower.jpg](KB_lower.jpg)

The image with better resolution
![KB_better.jpg](KB_better.jpg)

First, recaculate a new $\Sigma_n$ with $n$ number of eigenvector used, 30 for lower resolution and 200 for better resolution.
Both picture is then obtain by compute the matrix by U $\Sigma_n$ V for each color layer, then merge togehter to become an image in RGB format.

What is a sparse matrix?

Sparse matrix is the matrix with high percentage of zero entries.
In this assignment, $\Sigma_n$ is the example of sparse matrix which contain only $n$ non-zero element out of $N \times M$ element.

-----------------------------------

<sup>last modified: 3/11/2016</sup>
