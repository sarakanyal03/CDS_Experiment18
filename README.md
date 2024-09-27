# EXPERIMENT 18
### AIM
To study and implement Stack implementation using array. <BR>
Menu options -  <BR>
1. Push <BR>
2. Pop <BR>
3. Display <BR>
4. Exit <BR>

### THEORY <BR>
A stack is a linear data structure that follows the Last In, First Out (LIFO) principle.This means that the final piece added to the stack will be the first one removed. In C++, a stack can be implemented by storing elements in an array and performing the following operations using functions: <BR>
1. Push: Adds an element to the top of the stack. <BR>
2. Pop: Removes and returns the element from the top of the stack. <BR>
3. Display: Displays all elements in the stack. <BR>
4. Exit: Terminates the program. <BR>

*Stack Implementation Using an Array in C++*
1. Array as the Stack: An array is used to store stack elements, and a variable `top` keeps track of the index of the `top` element. Initially, top is set to `-1`, indicating an empty stack.

2. Push Operation: The `push` operation inserts an element at the `top` of the stack. Before pushing, it checks if the stack is full (i.e., if `top` has reached the maximum size). If the stack is not full, it increments the `top` and adds the element at the `top` position.

3. Pop Operation: The `pop` operation removes and returns the top element of the stack. Before popping, it checks if the stack is empty (i.e., if `top == -1`). If the stack is not empty, it returns the element at the `top` and decrements the `top`.

4. Display Operation: The `display` operation prints all the elements in the stack from the top to the bottom.

### CODE & OUTPUT 
1. CODE A: <BR>
```
//SARA KANYAL 
//23070123115
//EXPERIMENT 18-A 
#include <iostream>
using namespace std;
int stack[100], n=100, top=-1;
void push(int val) {
   if(top>=n-1)
   cout<<"Stack Overflow"<<endl;
   else {
      top++;
      stack[top]=val;
   }
}
void pop() {
   if(top<=-1)
   cout<<"Stack Underflow"<<endl;
   else {
      cout<<"The popped element is "<< stack[top] <<endl;
      top--;
   }
}
void display() {
   if(top>=0) {
      cout<<"Stack elements are:";
      for(int i=top; i>=0; i--)
      cout<<stack[i]<<" ";
      cout<<endl;
   } else
   cout<<"Stack is empty";
}
int main() {
   int ch, val;
   cout<<"1) Push in stack"<<endl;
   cout<<"2) Pop from stack"<<endl;
   cout<<"3) Display stack"<<endl;
   cout<<"4) Exit"<<endl;
   do {
      cout<<"Enter choice: "<<endl;
      cin>>ch;
      switch(ch) {
         case 1: {
            cout<<"Enter value to be pushed:"<<endl;
            cin>>val;
            push(val);
            break;
         }
         case 2: {
            pop();
            break;
         }
         case 3: {
            display();
            break;
         }
         case 4: {
            cout<<"Exit"<<endl;
            break;
         }
         default: {
            cout<<"Invalid Choice"<<endl;
         }
      }
   }while(ch!=4);
   return 0;
}
```
* OUTPUT A: <BR>
![EXP18A](https://github.com/sarakanyal03/CDS_Experiment18/blob/main/18A.png)
2. CODE B: <BR>
```
//SARA KANYAL
//23070123115
//EXPERIMENT 18-B
#include <iostream>
using namespace std;
#define size 5
#define error -9999

class stack 
{
    int top, ar[size];

public:
    stack() 
    {
        top = -1;
        ar[0]=0;
    }
    void push(int);
    int pop();
    int peak();
    void disp();
};

void stack::push(int num) 
{
    if (top == size - 1) 
    {
        cout << "Stack overflow: stack is full" << endl;
        return;
    } else 
    {
        ar[++top] = num;
    }
}

int stack::pop() {
    int val;
    if (top == -1) 
    {  // Corrected this line
        cout << "Stack underflow: stack is empty" << endl;
        return error;
    } else 
    {
        val = ar[top--];
        return val;
    }
}

int stack::peak() 
{
    if (top == -1) 
    {
        cout << "Stack underflow: stack is empty" << endl;
        return error;
    } else 
    {
        return ar[top];
    }
}

void stack::disp() 
{
    if (top == -1) 
    {
        cout << "Stack underflow: stack is empty" << endl;
        return;
    } else 
    {
        for (int i = 0; i <= top; i++) 
        {
            cout << ar[i] << " ";
        }
        cout << endl;  // Added for better output readability
    }
}

int main() 
{
    stack s1;
    s1.push(10);
    s1.push(7);
    s1.push(4);
    int val = s1.pop();
    cout << "Popped value: " << val << endl;
    int top = s1.peak();
    cout << "Top value: " << top << endl;
    cout << "Stack contents: ";
    s1.disp();
    return 0;
}
```
* OUTPUT B: <BR>
![EXP18B](https://github.com/sarakanyal03/CDS_Experiment18/blob/main/18B.png)
### CONCLUSION 
Implementing a stack with an array in C++ is an efficient and straightforward technique to manage data that adheres to the LIFO principle. The menu-driven application allows users to interact with the stack by performing operations such as push, pop, and show, while also ensuring that stack overflow and underflow are handled gracefully. <BR>
