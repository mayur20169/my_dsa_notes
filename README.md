### Character sequences

The `string` class has been briefly introduced in an earlier chapter. It is a very powerful class to handle and manipulate strings of characters. However, because strings are, in fact, sequences of characters, we can represent them also as plain arrays of elements of a character type.

For example, the following array:

  char foo [20];

is an array that can store up to 20 elements of type `char`. It can be represented as:

![image](https://user-images.githubusercontent.com/77676919/156035928-fb8ab661-58f3-41bd-be8e-bb18b6459d67.png)

Therefore, this array has a capacity to store sequences of up to 20 characters. But this capacity does not need to be fully exhausted: the array can also accommodate shorter sequences. For example, at some point in a program, either the sequence `"Hello"` or the sequence `"Merry Christmas"` can be stored in `foo`, since both would fit in a sequence with a capacity for 20 characters.

By convention, the end of strings represented in character sequences is signaled by a special character: the *null character*, whose literal value can be written as `'\0'` (backslash, zero).

In this case, the array of 20 elements of type `char` called `foo` can be represented storing the character sequences `"Hello"` and `"Merry Christmas"` as:

![image](https://user-images.githubusercontent.com/77676919/156036413-25d32d51-8fd6-4398-829d-422688b468ea.png)

Notice how after the content of the string itself, a null character (`'\0'`) has been added in order to indicate the end of the sequence. The panels in gray color represent char elements with undetermined values.

### Initialization of null-terminated character sequences


