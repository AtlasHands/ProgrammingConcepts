# Functions
You can think of functions as containers for code. Many people refer to functions as "blocks" of code. Having containers for code is extremely useful if you want to make your code concise and readable. It removes repetition and allows you to generalize code easier.  
  
For example, we want part of our code to first add five to a number, multiply it by 10, then subtract 23 to five seperate numbers. Without functions that would look something like this:
```C
#include <stdio.h>

int main()
{
    int firstNumber = 10;
    int secondNumber = 55;
    int thirdNumber = 77;
    int fourthNumber = 99;
    int fifthNumber = 12;
    int operation1 = ((firstNumber + 5)*10)-23;
    int operation2 = ((secondNumber + 5)*10)-23;
    int operation3 = ((thirdNumber + 5)*10)-23;
    int operation4 = ((fourthNumber + 5)*10)-23;
    int operation5 = ((fifthNumber + 5)*10)-23;
    printf("First:%i\nSecond:%i\nThird:%i\nFourth:%i\nFifth:%i\n",operation1,operation2,operation3,operation4,operation5);
}
```  
  
This start to become cumbersome to keep typing the parethesis and all the operations. Now what would this look like in a function?

```C
#include <stdio.h>

//Function doOperation
int doOperation(int number){
	int operation = ((number + 5)*10)-23;
	return operation; 	
}

int main()
{
    int firstNumber = 10;
    int secondNumber = 55;
    int thirdNumber = 77;
    int fourthNumber = 99;
    int fifthNumber = 12;
    int operation1 = doOperation(firstNumber); //first Example
    int operation2 = doOperation(secondNumber);//second Example
    int operation3 = doOperation(thirdNumber);
    int operation4 = doOperation(fourthNumber);
    int operation5 = doOperation(fifthNumber);
    printf("First:%i\nSecond:%i\nThird:%i\nFourth:%i\nFifth:%i\n",operation1,operation2,operation3,operation4,operation5);
}
```  
  
Lets walk through the anatomy of a function. If you look up above you can see: int doOperation(int number){} the format that this follows is: <returnValue> <functionName>\(<type> <parameterName>\){<CodeToRun>}.  
Reading this in plain english from left to right would explain as follows, We have a function that:
* Returns an integer 
* is called doOperation
* Takes an argument
* Argument is an integer 
* Argument will locally be called number
  
# Some terminology

* **Parameter:** Something you pass to a function, by calling the function with the the variable you want to pass. If you look up above at //first Example you can see that firstNumber is within the parethesis, this is the parameter  
* **Parameter Name:** Whatever you pass to the function will be called by the name you choose within where you declare function. So technically if we pass firstNumber into doOperation, within doOperation it is no loger called firstNumber, it is named number, however the variable number will have the same value as firstNumber.  
* **Return**: What gets passed back to the location where the function is called, must be specified at the front of the function. You'll see that at //secondExample we have operation2 being set equal to the function of doOperation(secondNumber), what we get back from the function is what gets returned from doOperation, which when you look at the function doOperation, we return operation, which is technically going to be (secondNumber + 5)*10)-23;  

# Incorrect function definitions

```C
	int doOperation(int number){return 1} //Ex1:correct
	int doOperation(int number){} //Ex2: incorrect
	int doOperation(number){return 1};//Ex3: incorrect
	int doOperation(int){return 1};//Ex4: incorrect
	doOperation(int number){return 1};//Ex5: incorrect
	int (int number){return 1};//Ex6: incorrect
```
