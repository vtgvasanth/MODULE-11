
# Ex.No:5  
# Ex.Name: Object Delegation in C++ (using float data)  

## Date:  

## Aim:  
To write a C++ program to demonstrate **object delegation** (one object delegating tasks to another) using **float data**.  

## Algorithm:  
1. Start the program.  
2. Define a class `Delegate` with:  
   - A private float data member.  
   - A constructor to initialize the data.  
   - A function `show()` to display the value.  
3. Define another class `MainClass` that contains an object of class `Delegate`.  
4. In `MainClass` constructor, delegate initialization to the `Delegate` class.  
5. In `main()`:  
   - Read a float value from the user.  
   - Create a `MainClass` object.  
   - Call the function to display the value.  
6. Stop the program.  

## Program:
```cpp
#include <iostream>
using namespace std;

// Simple class
class A {
public:
	float a;

};

// Complex class
class B :public A{
    public:
    void disp(float a){
        cout<<a<<endl;
    }
	
	
};

// Driver code
int main()
{
	double a;
	cin>>a;
	B x;
	x.disp(a);
	return 0;
}

```

## Output:
<img width="884" height="414" alt="image" src="https://github.com/user-attachments/assets/09f0e688-5b34-47fb-b937-7000403c43e5" />

## Result:
```
Input:
10.01

Output:
10.01
10.01
10.01



Input:
20.20

Output:
20.2
20.2
20.2
```
