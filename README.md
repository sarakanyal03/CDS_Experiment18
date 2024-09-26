# EXPERIMENT 17
# AIM
To study and implement Stack implementation using array. <BR>
Menu options -  <BR>
1. Push <BR>
2. Pop <BR>
3. Display <BR>
4. Exit <BR>

# THEORY <BR>
A stack is a linear data structure that follows the Last In, First Out (LIFO) principle.This means that the final piece added to the stack will be the first one removed. In C++, a stack can be implemented by storing elements in an array and performing the following operations using functions: <BR>
1. Push: Adds an element to the top of the stack. <BR>
2. Pop: Removes and returns the element from the top of the stack. <BR>
3. Display: Displays all elements in the stack. <BR>
4. Exit: Terminates the program. <BR>
<BR>
*Stack Implementation Using an Array in C++*
1. Array as the Stack: An array is used to store stack elements, and a variable `top` keeps track of the index of the `top` element. Initially, top is set to `-1`, indicating an empty stack.

2. Push Operation: The `push` operation inserts an element at the `top` of the stack. Before pushing, it checks if the stack is full (i.e., if `top` has reached the maximum size). If the stack is not full, it increments the `top` and adds the element at the `top` position.

3. Pop Operation: The `pop` operation removes and returns the top element of the stack. Before popping, it checks if the stack is empty (i.e., if `top == -1`). If the stack is not empty, it returns the element at the `top` and decrements the `top`.

4. Display Operation: The `display` operation prints all the elements in the stack from the top to the bottom.

*Basic Structure*
```
#include <iostream>
using namespace std;

#define MAX 100  // Maximum size of the stack

class Stack {
    int top;
    int arr[MAX];  // Array to store stack elements

public:
    Stack() { top = -1; }  // Constructor to initialize top
    
    // Stack operations
    void push(int value);
    int pop();
    void display();
    bool isFull();
    bool isEmpty();
};

// Check if the stack is full
bool Stack::isFull() {
    return top == MAX - 1;
}

// Check if the stack is empty
bool Stack::isEmpty() {
    return top == -1;
}

// Push operation to insert an element into the stack
void Stack::push(int value) {
    if (isFull()) {
        cout << "Stack Overflow! Cannot push " << value << endl;
        return;
    }
    arr[++top] = value;
    cout << value << " pushed into the stack." << endl;
}

// Pop operation to remove the top element of the stack
int Stack::pop() {
    if (isEmpty()) {
        cout << "Stack Underflow! Cannot pop." << endl;
        return -1;
    }
    cout << arr[top] << " popped from the stack." << endl;
    return arr[top--];
}

// Display operation to show all elements in the stack
void Stack::display() {
    if (isEmpty()) {
        cout << "Stack is empty." << endl;
        return;
    }
    cout << "Stack elements: ";
    for (int i = top; i >= 0; i--) {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main() {
    Stack stack;
    int choice, value;

    while (true) {
        // Menu-driven interface
        cout << "\nStack Menu\n";
        cout << "1. Push\n";
        cout << "2. Pop\n";
        cout << "3. Display\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            cout << "Enter the value to push: ";
            cin >> value;
            stack.push(value);
            break;
        case 2:
            stack.pop();
            break;
        case 3:
            stack.display();
            break;
        case 4:
            cout << "Exiting program..." << endl;
            exit(0);
        default:
            cout << "Invalid choice! Please try again." << endl;
        }
    }

    return 0;
}
```
# CODE & OUTPUT 
1. CODE A:
```
//SARA KANYAL
//entc B2
//23070123115
//experiment 17 A
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
* OUTPUT A: ![EXP17A]( )
# CONCLUSION 
Implementing a stack with an array in C++ is an efficient and straightforward technique to manage data that adheres to the LIFO principle. The menu-driven application allows users to interact with the stack by performing operations such as push, pop, and show, while also ensuring that stack overflow and underflow are handled gracefully. <BR>
