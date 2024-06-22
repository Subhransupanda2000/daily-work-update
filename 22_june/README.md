1) Array Introductions
2) Array declaration
3) Array construction
4) Array initialization
5) Array declaration, construction, initialization in a single line.
6) length Vs length() method
7) Anonymous arrays
8) Array element assignments
9) Array variable assignments.
# Ans:
* 1)An array is an indexed collection of fixed number of homogeneous data elements.
* The main advantage of arrays is we can represent multiple values with the same name
so that readability of the code will be improved.
* But the main disadvantage of arrays is:
Fixed in size that is once we created an array there is no chance of increasing or
decreasing the size based on our requirement that is to use arrays concept compulsory
we should know the size in advance which may not possible always.
We can resolve this problem by using collections.
# Array declarations:
# Single dimensional array declaration: 
```
* int[] a;
int []a;
int a[];
```
* At the time of declaration we can't specify the size otherwise we will get compile time
error.
# Two dimensional array declaration:
```
Example:
int[][] a;
int [][]a;
int a[][]; 
int[] []a;
int[] a[];
```
# Three dimensional array declaration:
```
int[][][] a;
int [][][]a;
int a[][][];
int[] [][]a;
int[] a[][]; 
int[] []a[];
int[][] []a;
int[][] a[];
int []a[][];
int [][]a[];
```
# Array construction:
Every array in java is an object hence we can create by using new operator.
Example:
int[] a=new int[3];
* Rule 1:
At the time of array creation compulsory we should specify the size otherwise we will
get compile time error.
* Rule:2
* It is legal to have an array with size zero in java.
* Rule 3:
If we are taking array size with -ve int value then we will get runtime exception saying
NegativeArraySizeException.
* The allowed data types to specify array size are byte, short, char, int.
By mistake if we are using any other type we will get compile time error.
* The maximum allowed array size in java is maximum value of int size [2147483647]. 
# Array Initialization:
* Whenever we are creating an array every element is initialized with default value
automatically. 
* int[] a=new int[3];
* System.out.println(a);
# length:
* 1. It is the final variable applicable only for arrays.
* 2. It represents the size of the array.
* 3. System.out.println(x.length);
# length() method:
* 1. It is a final method applicable for String objects.
* 2. It returns the no of characters present in the String.
* 3. System.out.println(s.length());
# Anonymous Arrays:
* Sometimes we can create an array without name such type of nameless arrays
are called anonymous arrays.
* The main objective of anonymous arrays is "just for instant use".
* We can create anonymous array as follows.
* new int[]{10,20,30,40};(valid)
* new int[][]{{10,20},{30,40}};(valid)
