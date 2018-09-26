# Arrays In C
Arrays are variables that have the ability to hold multiple values.  An example of this would be if you want to store something like your favorite numbers. Lets say that you have more than one favorite number. You could say: 
```C
int favoriteNumber1 = 12;
int favoriteNumber2 = 77;
int favoriteNumber3 = 80;
```
However if you want to get all of your favorite numbers you are then restricted because you need to know the name of your variable that you used for each favorite number, and if you have 10,000 favorite numbers you then need to call independently all of your favorite numbers by name if you want to look at your favorite numbers.  
  
A better way to do this is to store your favorite numbers in an array, making it easier to access all of your favorite numbers. An example of making an array with the same numbers as the last example is:
```C
int favoriteNumbers[] = {12,77,80};
```
Awesome! Now we can store all of our favorite numbers into one variable. I stated previously how this makes it easier to access your favorite numbers but how do we access our favorite numbers now?  
  
Notice how when favoriteNumbers was defined, it was followed by \[\] \(favoriteNumbers\[\]\). To access the values in favoriteNumbers we use a similar format. To get the first value in favoriteNumbers we call favoriteNumbers[0] - which would give us the value of 12.  Note: indexes for arrays start at 0 for most programming languages. So 0 will give you the first element, 1 will give you the second element and so on.
  
To see this in action put this into the online C compiler:

```C
#include <stdio.h>

int main()
{
    int favoriteNumbers[] = {12,77,88};
    printf("%i",favoriteNumbers[0]);
}
```
Try changing [0] to [1] and then [2] and then [3].  
  
You'll notice that when you try 3 the compiler will give you an error "Segmentation fault". This just means that you tried to access an element that does not exist within the array. Since we did not have a 4th element in the array we cannot access a [3] index. Be careful when programming because a segmentation fault will cause you program to crash, ruining whatever you are trying to do with your program.  
  
So why is this beneficial? Well now that we don't need to know the actual name of the variable we can use a programming concept called a loop to go through all the values in favoriteNumbers, even if you have 10,000 favorite numbers.  
  
An example of a loop that goes through a complete array is below, we will talk about loops later in the book.  
```C
#include <stdio.h>

int main()
{
    int favoriteNumbers[] = {12,77,88};
    int lengthOfFavorityNumbers = sizeof(favoriteNumbers)/sizeof(int);
	for(int x =0;x<lengthOfFavorityNumbers;x++){
		printf("%i ",favoriteNumbers[x]);
	}
}
```
If you plug that into the compiler you will get each value in the favoriteNumbers array. The loop above basically tells variable x to keep adding to itself until you reach the length of the elements in the favorite numbers.