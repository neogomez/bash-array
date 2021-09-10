<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

#                  Bash Array

## How to declare an array in Bash Scripting.
Bash scripts give you a convenient way to automate command line tasks.
With Bash, you can do many of the same things you would do in other scripting or programming languages. You can create and use variables, execute loops, use conditional logic, 
and store data in arrays.

While the functionality may be very familiar, the syntax of Bash can be tricky. In this article, you will learn how to declare arrays 
and then how to use them in your code.

### How to Declare an Array in Bash
Declaring an array in Bash is easy, but pay attention to the syntax. If you are used to programming in other languages, the code might look familiar, but there are subtle differences that are easy to miss.

To declare your array, follow these steps:

1. Give your array a name
2. Follow that variable name with an equal sign. The equal sign should not have any spaces around it
3. Enclose the array in parentheses (not brackets like in JavaScript)
4. Type your strings using quotes, but with no commas between them

```
myArray=("cat" "dog" "mouse" "frog")
```
That's it! It's that simple.

### How to access an Array in Bash
There are a couple different ways to loop through your array. You can either loop through the elements themselves, 
or loop through the indices.

### How to Loop Through Array Elements
To loop through the array elements, 
your code will need to look something like this:
```
for str in ${myArray[@]}; do
  echo $str
done
```
To break that down: this is somewhat like using forEach in JavaScript. For each string (str) in the array (myArray), print that string.

The output of this loop looks like this:
```
cat
dog
mouse
frog
```
Note: The @ symbol in the square brackets indicates that you are looping through all of the elements in the array. If you were to leave that out and just write for str in ${myArray}, only the first string in the array would be printed.

### How to Loop Through Array Indices
Alternatively, you can loop through the indices of the array. This is like a for loop in JavaScript, and is useful for when you want to be able to access the index of each element.

To use this method, your code will need to look something like the following:
```
for i in ${!myArray[@]}; do
  echo "element $i is ${myArray[$i]}"
done
```
The output will look like this:
```
element 0 is cat
element 1 is dog
element 2 is mouse
element 3 is frog
```
Note: The exclamation mark at the beginning of the myArray variable indicates that you are accessing the indices of the array and not the elements themselves. This can be confusing if you are used to the exclamation mark indicating negation, so pay careful attention to that.

Another note: Bash does not typically require curly braces for variables, but it does for arrays. So you will notice that when you reference an array, you do so with the syntax ${myArray}, but when you reference a string or number, you simply use a dollar sign: $i.

# Conclusion
Bash scripts are useful for creating automated command line behavior, and arrays are a great tool that you can use to store multiple pieces of data.

Declaring and using them is not hard, but it is different from other languages, so pay close attention to avoid making mistakes.
