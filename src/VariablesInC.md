# Variables in C
A variable is a designated "thing" that holds data.  You can think of it as a container for data where the data can be whatever that variable has been predefined to hold.  

In C defining a basic variable follows the format \[type\] \[nameYouChoose\] = \[value\];  
Note that at the end of the definition there is a semi-colon, the semi-colon is important in C and without it the program will fail to run since the semi-colon specifies the end of the definition.
  
For a quick example in C you can specify:
```C
	int a = 22;
	float b = 2.2;
	double c = 2.2;
	char d = 'A';
	//Non-Standard assignments
	char e = 99;
	int f = 2.6;
```
Where int means integer, float is a 64 bit decimal, double is a 32 bit decimal, char is an ASCII character \(A letter\).  
  
If you look below the Non-Standard assignments section you can see I assign a char to a number and doing that is valid. By default C will treat a number like the corresponding ASCII character \(ASCII is a map of numbers to characters that people defined\). If you go to: [http://www.asciitable.com/](http://www.asciitable.com/) you can see that char e = 99; will actually give us a lower case 'c'.  
  
Try running this in the C Compiler at: [https://www.tutorialspoint.com/compile_c_online.php](https://www.tutorialspoint.com/compile_c_online.php)
```C
#include <stdio.h>

int main()
{
    char a = 99;
	printf("%c",a);
}
```
In the right hand side panel you can see that a 'c' gets printed out, you can look up the characters in the table now and try different things in the compiler like: 
```C
	char a = 43;
	printf("%c",a);
```
or
```C
	char a  = 48;
	printf("%c",a);
```
To see what you will get!  
  
The second example I gave was int f = 2.2 which is a little less interesting.  All that happens here is that the decimal points get removed, technically rounding down no matter what decimal you give it.  So 2.999999999999 will be turned into 2.  To test this out you can run this in the compiler:
```C
#include <stdio.h>

int main()
{
    int a = 2.9999999;
	printf("%i",a);
}
```
And you can change 'int a' to whatever you want to see how it behaves.  
  
Later on in the chapter I will explain what "int main(){}" means, what the top #include <stdio.h>, and what printf() means in C.

Thanks for waiting on me, I should be able to keep writing after work slows down.