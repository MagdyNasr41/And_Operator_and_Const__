#The uses of the const in C++
Const is a promise that something won’t change, which can be broken as any real-life promise.
Const has so many usages in C++ programming language so let’s dig deep into these usages.

The first usage of const is before the data type variable which means that variable’s value won’t change during the runtime code.

Ex:

###const int maxAge = 90; >> we can’t do that: maxAge = 30; because once the variable’s value is initialized, it can’t be modified.

The second usage is declaring a constant pointer, but the constant in this case the pointer value is the constant not the pointer.

Ex:

###const int* a = new int; >> we can’t do that: *a = 3; because once the pointer’s “a” value is initialized, it can’t be modified.
####Notice that we can modify what does the pointer refer to freely without any error.
Ex: 
###a = &maxAge;

####Notice that we can code this case as follows: const int* a = new int; OR int const * a = new int;
The third usage is declaring a constant pointer, but in this case the constant is the pointer itself not its value. For instance, we can modify the value of this pointer but can’t modify what it refers to.

Ex:

###int* const a = new int;  we can’t do that: a = nullptr; but on the other side we can re-assign the variable value as follows: *a = 2;
If we add const after any method in a class it means that this method doesn’t support editing in the class variables

Ex:

###void getName() const { cout<<”name”; }

####Notice in the previous function’s body we can’t write down any code that modify a variable like x = 90;

####Notice in this case mostly we use const with setters and getters as they don’t need any variable modifications in their body.
The fourth usage is in constant overloading. C++ allows constant overloading which means to write the same  method with constant return value and without constant return value and the compiler chooses the suitable method to use while run time.

Ex:

###int& myClass::getData() { return data; }

###const int& myClass::getData() const { return data; }

##Side notes:
-Declaring two const pointers in this way const int* x , y; is wrong because in this way x is a pointer but y is a still a variable , the correction is const int* x , *y;

-Constant methods can only call constant methods also.

-We can modify variables in a constant methods by adding “mutable” during declaring the variables.

Ex:

###mutable x = 0;

###void get() const { x = 1; cout<<x; }

-Interesting code:

###const int* const  get() const { return ptr; }

first const refers to returning a ptr that can’t be modified “The value can’t be modified”.

Second const refer to the content of the pointer can’t be modified “The pointer shouldn’t point to other address”.

Finally the last const refers to the body of get method which can’t contain any modification code.

----------------------------------------------------------------------------------
#The uses of the operator ‘&’ in C++

-If we declare a pointer:
###int x; int* p; p= &x;
here we store the address of x in the variable p.

-Use & as logical operator
###if (a >30 & b<60)
Here we are checking both the conditions using logical ANDing where if both are true then it will execute if block.

-Use & as bitwise ANDing
###If we use 6 & 3 ….it actually does a bitwise ANDing like 110 AND 011 = 010

----------------------------------------------------------------------------------




