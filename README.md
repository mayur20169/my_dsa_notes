### Array
	
An array is a series of elements of the same type placed in contiguous memory locations that can be individually accessed by adding an index to a unique identifier. To add to it, an array in C++ can store derived data types such as the structures, pointers etc.

That means that, for example, five values of type `int` can be declared as an array without having to declare 5 different variables (each with its own identifier). Instead, using an array, the five `int` values are stored in contiguous memory locations, and all five can be accessed using the same identifier, with the proper index.

For example, an array containing 5 integer values of type `int` called `foo` could be represented as:

![image](https://user-images.githubusercontent.com/77676919/156010617-45e3ffde-62b5-4b20-823c-4fd6cd626006.png)

where each blank panel represents an element of the array. In this case, these are values of type `int`. These elements are numbered from 0 to 4, being 0 the first and 4 the last; In C++, the first element in an array is always numbered with a zero (not a one), no matter its length.

Like a regular variable, an array must be declared before it is used. A typical declaration for an array in C++ is:

    type name [elements];  
    
where type is a valid type (such as `int, float, double, char...`), `name` is a valid identifier and the `elements` field (which is always enclosed in square brackets [ ]), specifies the length of the array in terms of the number of elements.

Therefore, the `foo` array, with five elements of type `int`, can be declared as:

    int foo [5];

**Note**: The `elements` field within square brackets [ ], representing the number of elements in the array, must be a *constant expression*, since arrays are blocks of static memory whose size must be determined at compile time, before the program runs.

![image](https://user-images.githubusercontent.com/77676919/156177485-ccf6d4f1-266d-48d6-8850-6494faa39c87.png)

**Note**: In above image `int a[3]={[0…1]=3};` this kind of declaration has been obsolete since GCC 2.5

There are various ways in which we can declare an array. It can be done by specifying its type and size, by initializing it or both.

**Array declaration by specifying size **

	// Array declaration by specifying size
	int arr1[10];

	// With recent C/C++ versions, we can also
	// declare an array of user specified size
	int n = 10;
	int arr2[n];
	
**Array declaration by initializing elements**

	// Array declaration by initializing elements
	int arr[] = { 10, 20, 30, 40 }

	// Compiler creates an array of size 4.
	// above is same as  "int arr[4] = {10, 20, 30, 40}"
	
**Array declaration by specifying size and initializing elements**

	// Array declaration by specifying size and initializing
	// elements
	int arr[6] = { 10, 20, 30, 40 }

	// Compiler creates an array of size 6, initializes first
	// 4 elements as specified by user and rest two elements as
	// 0. above is same as  "int arr[] = {10, 20, 30, 40, 0, 0}"

### Initializing arrays

By default, regular arrays of *local scope* (for example, those declared within a function) are left uninitialized. This means that none of its elements are set to any particular value; their contents are undetermined at the point the array is declared.

But the elements in an array can be explicitly initialized to specific values when it is declared, by enclosing those initial values in braces { }. For example:

    int foo [5] = { 16, 2, 77, 40, 12071 }; 

This statement declares an array that can be represented like this:

![image](https://user-images.githubusercontent.com/77676919/156014423-29d67a46-a19e-4e48-80e6-c8b52d60c53a.png)

The number of values between braces { } shall not be greater than the number of elements in the array. For example, in the example above, foo was declared having 5 elements (as specified by the number enclosed in square brackets, [ ] ), and the braces { } contained exactly 5 values, one for each element. If declared with less, the remaining elements are set to their default values (which for fundamental types, means they are filled with zeroes). For example:

    int bar [5] = { 10, 20, 30 };
    
Will create an array like this:

![image](https://user-images.githubusercontent.com/77676919/156015595-21b2a592-ae72-4765-89ae-7de1e6065f96.png)

The initializer can even have no values, just the braces:

    int baz [5] = { }; 

This creates an array of five `int` values, each initialized with a value of zero:

![image](https://user-images.githubusercontent.com/77676919/156015810-416443af-ecc6-48dd-8208-74975b936f22.png)

When an initialization of values is provided for an array, C++ allows the possibility of leaving the square brackets empty [ ]. In this case, the compiler will assume automatically a size for the array that matches the number of values included between the braces { }:

	int foo [] = { 16, 2, 77, 40, 12071 };

After this declaration, array `foo` would be 5 `int` long, since we have provided 5 initialization values.

Finally, the evolution of C++ has led to the adoption of *universal initialization* also for arrays. Therefore, there is no longer need for the equal sign between the declaration and the initializer. Both these statements are equivalent:

    int foo[] = { 10, 20, 30 };
    int foo[] { 10, 20, 30 }; 

Static arrays, and those declared directly in a namespace (outside any function), are always initialized. If no explicit initializer is specified, all the elements are default-initialized (with zeroes, for fundamental types).

**Advantages of an Array in C/C++: **

1.Random access of elements using array index.

2.Use of fewer line of code as it creates a single array of multiple elements.

3.Easy access to all the elements.

4.Traversal through the array becomes easy using a single loop.

5.Sorting becomes easy as it can be accomplished by writing fewer line of code.

**Disadvantages of an Array in C/C++:**

1.Allows a fixed number of elements to be entered which is decided at the time of declaration. Unlike a linked list, an array in C is not dynamic.

2.Insertion and deletion of elements can be costly since the elements are needed to be managed in accordance with the new memory allocation.

### Accessing the values of an array

![image](https://user-images.githubusercontent.com/77676919/156184622-ef20f18f-96bc-412f-aec5-7fc183b1350f.png)

The values of any of the elements in an array can be accessed just like the value of a regular variable of the same type. The syntax is:

    name[index]

Following the previous examples in which `foo` had 5 elements and each of those elements was of type `int`, the name which can be used to refer to each element is the following:

![image](https://user-images.githubusercontent.com/77676919/156019906-b706c683-1a23-4a6f-b8d1-abe0da6f67ea.png)

For example, the following statement stores the value 75 in the third element of `foo`:

    foo [2] = 75;
    
and, for example, the following copies the value of the third element of `foo` to a variable called `x`:

    x = foo[2];
    
Therefore, the expression `foo[2]` is itself a variable of type `int`.

Notice that the third element of `foo` is specified `foo[2]`, since the first one is `foo[0]`, the second one is `foo[1]`, and therefore, the third one is `foo[2]`. By this same reason, its last element is `foo[4]`. Therefore, if we write `foo[5]`, we would be accessing the sixth element of `foo`, and therefore actually exceeding the size of the array.

In C++, it is syntactically correct to exceed the valid range of indices for an array. This can create problems, since the following program compiles fine but produce unexpected output when run in my VS Code and cause warnings on compilation, and produce unexpected output when run in my Visual Studio.

	// This C++ program compiles fine
	// as index out of bound
	// is not checked in C.

	#include <iostream>
	using namespace std;

	int main()
	{
		int arr[2];

		cout << arr[3] << " ";
		cout << arr[-2] << " ";

		return 0;
	}
	
**Output**

	6422240 59  // in VS Code
	-858993460 -858993460  // in Visual Studio
	
another case: In C++, it is a compiler error to initialize an array with more elements than the specified size.

	#include <iostream>
	using namespace std;

	int main()
	{

		// Array declaration by initializing it
		// with more elements than specified size.
		int arr[2] = {10, 20, 30, 40, 50};

		return 0;
	}
	
**Note**: The program won’t compile in C++. If we save the above program as a .cpp, the program generates compiler error “error: too many initializers for ‘int [2]'”. 

At this point, it is important to be able to clearly distinguish between the two uses that brackets [ ] have related to arrays. They perform two different tasks: one is to specify the size of arrays when they are declared; and the second one is to specify indices for concrete array elements when they are accessed. Do not confuse these two possible uses of brackets [ ] with arrays.

    int foo[5];         // declaration of a new array
    foo[2] = 75;        // access to an element of the array.  

The main difference is that the declaration is preceded by the type of the elements, while the access is not.

Some other valid operations with arrays:

	foo[0] = a;
	foo[a] = 75;
	b = foo [a+2];
	foo[foo[a]] = foo[2] + 5;

For example:

	// arrays example
	#include <iostream>
	using namespace std;

	int foo [] = {16, 2, 77, 40, 12071};
	int n, result=0;

	int main ()
	{
	  for ( n=0 ; n<5 ; n++ )
	  {
		result += foo[n];
	  }
	  cout << result;
	  return 0;
	}
	
**Output**
	
	12206
	
example:
	
	#include <iostream>
	using namespace std;

	int main()
	{
		int arr[5];
		arr[0] = 5;
		arr[2] = -10;

		// this is same as arr[1] = 2
		arr[3 / 2] = 2;
		arr[3] = arr[0];

		cout << arr[0] << " " << arr[1] << " " << arr[2] << " "
			<< arr[3];

		return 0;
	}
	
**Output**

5 2 -10 5

**The elements are stored at contiguous memory locations **

example: 

	// C++ program to demonstrate that array elements
	// are stored contiguous locations

	#include <iostream>
	using namespace std;

	int main()
	{
		// an array of 10 integers.
		// If arr[0] is stored at
		// address x, then arr[1] is
		// stored at x + sizeof(int)
		// arr[2] is stored at x +
		// sizeof(int) + sizeof(int)
		// and so on.
		int arr[5], i;

		cout << "Size of integer in this compiler is "
			<< sizeof(int) << "\n";

		for (i = 0; i < 5; i++)
			// The use of '&' before a variable name, yields
			// address of variable.
			cout << "Address arr[" << i << "] is " << &arr[i]
				<< "\n";

		return 0;
	}
	
**Output**

	Size of integer in this compiler is 4
	Address arr[0] is 0x61fea8
	Address arr[1] is 0x61feac
	Address arr[2] is 0x61feb0
	Address arr[3] is 0x61feb4
	Address arr[4] is 0x61feb8
	
**Another way to traverse the array**
	
	#include<bits/stdc++.h>
	using namespace std;

	int main()
	{
		int arr[6]={11,12,13,14,15,16};
		// Way 1
		for(int i=0;i<6;i++)
			cout<<arr[i]<<" ";

	cout<<endl;
		// Way 2
		cout<<"By Other Method:"<<endl;
		for(int i=0;i<6;i++)
			cout<<i[arr]<<" ";

		cout<<endl;

		return 0;
	}
	
**Output**

	11 12 13 14 15 16 
	By Other Method:
	11 12 13 14 15 16
	
### Multidimensional arrays

Multidimensional arrays can be described as "arrays of arrays". For example, a bidimensional array can be imagined as a two-dimensional table made of elements, all of them of a same uniform data type.

![image](https://user-images.githubusercontent.com/77676919/156025109-05980a7d-27ec-4863-8892-7c5ec296efac.png)

jimmy represents a bidimensional array of 3 per 5 elements of type int. The C++ syntax for this is:

	int jimmy [3][5];
	
and, for example, the way to reference the second element vertically and fourth horizontally in an expression would be:
 
	jimmy[1][3]

![image](https://user-images.githubusercontent.com/77676919/156025328-ce1501b1-6ff8-4def-81f6-b3f631047d73.png)

(remember that array indices always begin with zero).

Multidimensional arrays are not limited to two indices (i.e., two dimensions). They can contain as many indices as needed. Although be careful: the amount of memory needed for an array increases exponentially with each dimension. For example:

	char century [100][365][24][60][60];

declares an array with an element of type char for each second in a century. This amounts to more than 3 billion char! So this declaration would consume more than 3 gigabytes of memory!

At the end, multidimensional arrays are just an abstraction for programmers, since the same results can be achieved with a simple array, by multiplying its indices:

	int jimmy [3][5];   // is equivalent to
	int jimmy [15];     // (3 * 5 = 15)  

With the only difference that with multidimensional arrays, the compiler automatically remembers the depth of each imaginary dimension. The following two pieces of code produce the exact same result, but one uses a bidimensional array while the other uses a simple array:

**multidimensional array**

	#define WIDTH 5
	#define HEIGHT 3

	int jimmy [HEIGHT][WIDTH];
	int n,m;

	int main ()
	{
	  for (n=0; n<HEIGHT; n++)
		for (m=0; m<WIDTH; m++)
			pseudo-multidimensional array
		  jimmy[n][m]=(n+1)*(m+1);
		}
	}
	
**pseudo-multidimensional array**

	#define WIDTH 5
	#define HEIGHT 3

	int jimmy [HEIGHT * WIDTH];
	int n,m;

	int main ()
	{
	  for (n=0; n<HEIGHT; n++)
		for (m=0; m<WIDTH; m++)
		{
		  jimmy[n*WIDTH+m]=(n+1)*(m+1);
		}
	}
	
None of the two code snippets above produce any output on the screen, but both assign values to the memory block called jimmy in the following way:

![image](https://user-images.githubusercontent.com/77676919/156029633-deeed229-89e0-4c2d-831b-f12633c57652.png)

Note that the code uses defined constants for the width and height, instead of using directly their numerical values. This gives the code a better readability, and allows changes in the code to be made easily in one place.Initializing Two-Dimensional Arrays

**Initializing Two-Dimensional Arrays**

Multidimensioned arrays may be initialized by specifying bracketed values for each row. Following is an array with 3 rows and each row have 4 columns.

	int a[3][4] = {  
	   {0, 1, 2, 3} ,   /*  initializers for row indexed by 0 */
	   {4, 5, 6, 7} ,   /*  initializers for row indexed by 1 */
	   {8, 9, 10, 11}   /*  initializers for row indexed by 2 */
	};
	
The nested braces, which indicate the intended row, are optional. The following initialization is equivalent to previous example −

	int a[3][4] = {0,1,2,3,4,5,6,7,8,9,10,11};

**Accessing Two-Dimensional Array Elements**

![image](https://user-images.githubusercontent.com/77676919/156205103-13d42d25-c32a-48f2-8d91-d157505d7ea2.png)

An element in 2-dimensional array is accessed by using the subscripts, i.e., row index and column index of the array. For example −

	int val = a[2][3];
	
The above statement will take 4th element from the 3rd row of the array. You can verify it in the above digram.

	#include <iostream>
	using namespace std;

	int main () {
	   // an array with 5 rows and 2 columns.
	   int a[5][2] = { {0,0}, {1,2}, {2,4}, {3,6},{4,8}};

	   // output each array element's value                      
	   for ( int i = 0; i < 5; i++ )
		  for ( int j = 0; j < 2; j++ ) {

			 cout << "a[" << i << "][" << j << "]: ";
			 cout << a[i][j]<< endl;
		  }

	   return 0;
	}
	
When the above code is compiled and executed, it produces the following result −

	a[0][0]: 0
	a[0][1]: 0
	a[1][0]: 1
	a[1][1]: 2
	a[2][0]: 2
	a[2][1]: 4
	a[3][0]: 3
	a[3][1]: 6
	a[4][0]: 4
	a[4][1]: 8
	
As explained above, you can have arrays with any number of dimensions, although it is likely that most of the arrays you create will be of one or two dimensions.

### Arrays as parameters

At some point, we may need to pass an array to a function as a parameter. In C++, it is not possible to pass the entire block of memory represented by an array to a function directly as an argument. But what can be passed instead is its address. In practice, this has almost the same effect, and it is a much faster and more efficient operation.

To accept an array as parameter for a function, the parameters can be declared as the array type, but with empty brackets, omitting the actual size of the array. For example:

	void procedure (int arg[])

This function accepts a parameter of type "array of `int`" called arg. In order to pass to this function an array declared as:

	int myarray [40];

it would be enough to write a call like this:
 
	procedure (myarray);

Here you have a complete example:
	
	// arrays as parameters
	#include <iostream>
	using namespace std;

	void printarray (int arg[], int length) {
	  for (int i=0; i<length; i++)
		cout << arg[i] << " ";
	  cout << endl;
	}

	int main ()
	{
	  int firstarray[] = {5, 10, 15};
	  int secondarray[] = {2, 4, 6, 8, 10};
	  printarray (firstarray,3);
	  printarray (secondarray,5);
	}
	
**Output**
	
	5 10 15
	2 4 6 8 10

In the code above, the first parameter `(int arg[])` accepts any array whose elements are of type `int`, whatever its length. For that reason, we have included a second parameter that tells the function the length of each array that we pass to it as its first parameter. This allows the for loop that prints out the array to know the range to iterate in the array passed, without going out of range.

In a function declaration, it is also possible to include multidimensional arrays. The format for a tridimensional array parameter is:
 
	base_type[][depth][depth]

For example, a function with a multidimensional array as argument could be:
 
	void procedure (int myarray[][3][4])

Notice that the first brackets [ ] are left empty, while the following ones specify sizes for their respective dimensions. This is necessary in order for the compiler to be able to determine the depth of each additional dimension.

In a way, passing an array as argument always loses a dimension. The reason behind is that, for historical reasons, arrays cannot be directly copied, and thus what is really passed is a pointer. This is a common source of errors for novice programmers. Although a clear understanding of pointers, explained in a coming chapter, helps a lot.

### Library arrays	

The arrays explained above are directly implemented as a language feature, inherited from the C language. They are a great feature, but by restricting its copy and easily decay into pointers, they probably suffer from an excess of optimization.

To overcome some of these issues with language built-in arrays, C++ provides an alternative array type as a standard container. It is a type template (a class template, in fact) defined in header `<array>`.

Containers are a library feature that falls out of the scope of this tutorial, and thus the class will not be explained in detail here. Suffice it to say that they operate in a similar way to built-in arrays, except that they allow being copied (an actually expensive operation that copies the entire block of memory, and thus to use with care) and decay into pointers only when explicitly told to do so (by means of its member data).

Just as an example, these are two versions of the same example using the language built-in array described in this chapter, and the container in the library:

**language built-in array**

	#include <iostream>

	using namespace std;

	int main()
	{
	  int myarray[3] = {10,20,30};

	  for (int i=0; i<3; i++)
	  myarray[i]++;

	  for (int elem : myarray)
	    cout << elem << '\n';
	}
	
**container library array**

	#include <iostream>
	#include <array>
	using namespace std;

	int main()
	{
	  array<int,3> myarray {10,20,30};

	  for (int i=0; i<myarray.size(); i++)
	  myarray[i]++;

	  for (int elem : myarray)
	    cout << elem << '\n';
	}

As you can see, both kinds of arrays use the same syntax to access its elements: `myarray[i]`. Other than that, the main differences lay on the declaration of the array, and the inclusion of an additional header for the *library array*. Notice also how it is easy to access the size of the *library array*.
