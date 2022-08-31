// Write a program to implement the stack data structure using arrays.
#include<iostream>
#include<iostream>
using namespace std;
#define n 100 //let take array size 100

//create a stack class
class stack{
    int top;
    int* arr;
    public:
    stack(){
        arr=new int[n];  // an array of size n created
        top=-1;          // top is an index which pointing -1 at begining so there is no elements in array
    }
    
    // function for push operation push--> it can insert element on the top of stack
    void push(int e){
        if(top==n-1)    // if index reached at last then array full and we can'r insert element
        {
            cout<<"stack overflow";
        }
        top++;
        arr[top]=e;  // else the element inserted at top of stack
    }

    // fuction for pop oparation used to remove the top element

    void pop(){
        if(top==-1){
            cout<<"stack is empty";
        }
        top=top-1;   // if stack not empty then top element can be removed
    }
    
    // function to display the top most element in stack which not removes just displays
    int Top(){
        if(top==-1){
            cout<<"stack is empty";
        }
        return arr[top];
    }

    // function for printing the all ements in stack from top to bottom; LIFO || FILO
    
    void print(){
        if(top==-1){
            cout<<"stack is empty";
        }
        while(top!=-1){
            cout<<arr[top]<<"\n";  // to get line by line elements '\n'
            top--;
        }
    }
    
    // function to check the stack is empty or not
    bool isempty(){
        if(top==-1)    //if index top=-1 then there is no elements and it return true else it return false;
        return true;  
    }

};

// main function to call and do opartion with the above functions 

int main(){
    stack st;  // ctreating an object to call the above functions 
    // pushing elements into stack

    st.push(1);
    st.push(2);
    st.push(3);
    st.push(4);
    st.push(5);  // elements stored in linearly

    // printing the top element
    cout<<"the top element in stack is :  \n";
    cout<<st.Top()<<"\n";   // 5  the returned top value should be print 
    // removing the top element 5 then 4 becomes the top element
    st.pop();
    cout<<"top element after removing previous top element 5 is: \n";
    cout<<st.Top()<<"\n";
    //checking is stack is empty or not 
    cout<<"is your stack empty ?:  ";
    if(st.isempty()){
        cout<<"stack is empty\n";
    }
    else{
        cout<<"stack is not empty\n";
    }
    //printing the all the stack elements 
    cout<<"elements of your stack in top to bottom: \n";
    st.print();


}
