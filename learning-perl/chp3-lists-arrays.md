Date: 2014-9-29
Title: Lists And Array
Category: Learning Perl

### What is Lists and Arrays
A list is an ordered collection of scalars.

An array is a variable that contains a list.
To be accurate,the list is data,and the array is variable.You can have a list that isn't an array, but every array hosts a list, through it may be empty.

**Since each element is an independent scalar value, a list or array may hold numbers, strings, undef values, or any mixture of different scalar values.**

### Accessing Elements of an Array
The array name  is from a completely separate namespace than scalar use.**So you could have an array variable and a scalar name whose name are same.**

	$fred[0] = "hello";
	$fred[1] = "world";
	$fred = "hello world";

if the subscript(index) is not an integer, it will be truncated to the lower integer.

	$number = 2.71828;
	print $fred[$number - 1];  	#Same as printing $fred[1]
	
If the subscript indicated an element that would be beyond the end of the array, the corresponding value will be undef just like an unused scalar value.

	$blank = $fred[142_578];  #undef
	$blank = $what;			#undef
	
### Special Array Index
	$rock[0] = "redrock";
	$rock[99] = "schist"; #there are 98 undef variable
	
**How to find the last index of array.**
	
	$#rock
	
**Index can be less than zero**

	#if rock just has three element
	$rock[0] = "redrock";
	$rock[1] = "greenrock";
	$rock[2] = "bluerock";
	
	print $rock[-1]; 	#access the last element;
	print $rock[-2];	#access the middle element;
	print $rock[-3];	#access the first element;
	
	******
	print $rock[-4];	#This should be an fatal error