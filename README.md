# Experiment 12
## Aim -
To study and implement Constructors and Destructors <br>

## Theory - 
Constructors are unique member functions of a class that are automatically called when an object of the class is created. The object’s data members are initialized. Resources may also be allocated when required. <br>
There are some key points about costructors which are: <br>
- The name of the constructor is same as its class name. <br>
- Constructors do not have a return type. <br>
- Constructors are mostly declared in the public section of the class. <br>
- Multiple constructors can be defined with different parameters, this is known as overloading. <br>
<br>
There are mainly 3 types of constructors.
They are: <br>

### Default Constructor:
A constructor which takes no arguments. It is also called a zero-argument constructor as it has no parameters. <br>

### Parameterized Constructor:
A constructor that takes parameters, allowing the object to be initialized with specific values. <br>

### Copy Constructor:
A constructor that initializes an object using another object of the same class. It is used for deep copying and when passing objects by value. <br>
<br>

### Deconstructors - 
A destructor is also a special member function like a constructor.
- Destructor destroys the class objects created by the constructor.
- Destructor has the same name as their class name preceded by a tilde (~) symbol.
- It is not possible to define more than one destructor.
- The destructor is only one way to destroy the object created by the constructor. 
- Destructor neither requires any argument nor returns any value.
-  It is automatically called when an object goes out of scope.
-  Destructor release memory space occupied by the objects created by the constructor.


## CODE - 
### A - 
```
// Vivaan Gupta
// 23070123151
// defining constructor inside the class

#include <iostream>
using namespace std;
class student
{
    int rollno;
    char name[50];
    double fee;
    public:
    student()
    {
        cout<<"Enter the roll number : ";
        cin>>rollno;
        cout<<"Enter the name: ";
        cin>>name;
        cout<<"Enter the fee: ";
        cin>>fee;
    }
    void display()
    {
        cout<<endl<<rollno<<"\t"<<name<<"\t"<<fee<<endl;
    }
};

int main(){
    student s;
    s.display();
    return 0;
}
```

### B - 
```
#include <iostream>
using namespace std;

//defining the constructor outside the class
class student
{
    int rn;
    char name[50];
    float fee;
    public:
    student();
    void display();
};
student::student()
{
    cout<<"Enter the name: ";
    cin>>name;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the fee: ";
    cin>>fee;
}
void student::display()
{
    cout<<endl;
    cout<<"Name: "<<name<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Fee: "<<fee<<endl;
}
int main()
{
    student s1;
    s1.display();
}
```

### C - 
```
// Vivaan Gupta
// Default Constructors

#include<iostream>
#include<string>
using namespace std;

class Data {
    string name;
    int roll_no;
    char dept[50];
    int batch;

public:
    Data() {
        cout << "Name: ";
        cin >> name;
        cout << "Roll Number: ";
        cin >> roll_no;
        cout << "Department: ";
        cin >> dept;
        cout << "Batch: ";
        cin >> batch;
    }

    void display() {
        cout << endl << "DETAILS:" << endl << name << " " << roll_no << " " << dept << " " << batch << endl;
    }
};

int main() {
    Data d1;
    d1.display();
}
```

### D - 
```
// Vivaan Gupta
//parameterized constructor

#include<iostream>
using namespace std;

// Defining parameterized constructor
class Num {
    // int a=7, b=9;
public:
    Num(int c, int d) {
        if (c > d) {
            cout << c << " is greater"<<endl;
        } else {
            cout << d << " is greater"<<endl;
        }
    }
};

int main() {
    Num n1(4, 3);
}
```

### E - 
```
//Vivaan Gupta

#include<iostream>
#include<string.h>
using namespace std;

class student {
    int rno;
    char name[50];
    double fee;

public:
    student(int, char[], double);
    student(student &t) // copy constructor
    {
        rno = t.rno;
        strcpy(name, t.name);
        fee = t.fee;
    }
    void display();
};

student::student(int no, char n[], double f) {
    rno = no;
    strcpy(name, n);
    fee = f;
}

void student::display() {
    cout << endl << rno << "\t" << name << "\t" << fee<<endl;
}

int main() {
    student s(151, "Vijay", 999999);
    s.display();

    student vijay(s); // copy constructor called
    vijay.display();

    return 0;
}
```

### F - 
```
#include<iostream>
using namespace std;

int count = 0;

class destruct {
public:
    destruct() {
        ::count++;
        cout << "No. of objects created: " << ::count << endl;
    }

    ~destruct() {
        ::count--;
        cout << "No. of objects destroyed: " << ::count << endl;
    }
};

int main() {
    destruct aa, bb, cc;
    {
        destruct dd;
    }
    return 0;
}
```

## Outputs - 

### A - 

<img width="689" alt="Screenshot 2024-09-01 at 4 24 00 PM" src="https://github.com/user-attachments/assets/2c132748-3d02-49a0-adfa-440fdd6c47a5">

### B -

<img width="700" alt="Screenshot 2024-09-01 at 4 30 39 PM" src="https://github.com/user-attachments/assets/658cfad7-6730-4103-a677-8db3a3d46e3c">

### C -

<img width="465" alt="Screenshot 2024-09-01 at 4 31 32 PM" src="https://github.com/user-attachments/assets/c58f9e5e-a922-4c24-8743-75b883e17771">

### D -

<img width="386" alt="Screenshot 2024-09-01 at 4 31 53 PM" src="https://github.com/user-attachments/assets/c2069a42-9973-400e-b0c6-fe3dbd715468">

### E - 

<img width="440" alt="Screenshot 2024-09-01 at 4 32 07 PM" src="https://github.com/user-attachments/assets/c5bc707e-d03d-4a97-911c-2b2bd5c7a4e5">

### F -

<img width="411" alt="Screenshot 2024-09-01 at 4 32 23 PM" src="https://github.com/user-attachments/assets/971d27e5-93ff-4707-9f85-20dcab8a75fc">

## Conclusion - 
-  We learnt about constructors and deconstructors in C++. <br>
-  We learnt the use case of each of them in C++.  <br>

