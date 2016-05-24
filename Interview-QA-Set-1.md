# Interview QA Set-1


#### What is Class and Object?

Class is a template or blueprint used to define an object in Java.
Class contains elements like methods, variables, blocks and subclasses.

Class members can be classified into two types: Static and Non-static.

Non-static variables represent the state of an object.
And non-static methods represent the behavior of an object.

Object is a physical entity with properties and behaviour.
Object is the physical existance of a class whereas class is the logical entity that defines an object.


#### What is a Constructor and why is it required?

Constructor is that member of a class which is used to initialize data members of the class it is declared in.
Every class should provide a constructor to initialize data members of the class.

Constructors alone cannot create the object of a class, they are used only for initializing the data members of a class. For createtion of an object firstly, the memory allocation for the data members is done by the new keyword, following which the initilization of the data members is done by constructor.

Constructors can be defined either by user or by compiler.

Constructor defined by compiler is known as default constructor.
Default constructor is always a no-argument constructor.

Whereas a constructor defined by user is known as user defined constructor.
When data members of a class have to be compulsorily initialized then we must define a user-defined constructor.

A user defined constructor can be of two types:

1. No-argument constructor
2. Paramaterized constructor

Defining a constructor with parameter types is known as parameterized constructor.
We can define any number of parameters.

If a class is having user defined constructor, then the compiler will not define the default constructor.

In a class, either the default constructor or a user defined constructor should exist.

The name of constructor is always same as the name of class in which it is declared so as to allow JVM to easily identify which class members are to be initialized when a constructor is executed.

We must not specify a return value for a constructor because when a constructor is executed, it implicitly returns something to the new keyword. Developer must not explicitly specify a return type and value for a constructor, not even void.

#### What is constructor overloading?

In a class, defining multiple constructors with different parameter types is known as constructor overloaidng.

The parameters should differ either in type of parameter or the length of parameters.

When calling the constructor, JVM calls the corresponding constructor based on parameters at compile time.

With constructor overloading, we can create objects of class with different initilization.


#### Can we override constructors?

No, we cannot override constructors because every class has its own constructor and constructor of a superclass is not inherited by subclass during inheritance. Hence, we can only overload constructor within a class but can never override them.


#### What is the difference betweeb this and super keyword?

This keyword in Java stores the address of the current object under operation.
Using this keywork, we refer to the members of current object.
Whenever we invoke a method on an object reference variable, such as d1.display();, the value of this keyword will be updated to the value stored by d1 reference variable.
In-fact, the compiler automatically adds this keyword to all non-local variable references as long as there is no conflict of scope in non-local variables and local variables. If there is a conflict of scope between non-local variables and local variables, it is upto the programmer to use this keyword to refer to the non-local variable wherever required.

Whereas, with super keyword we can access the members of superclass from its subclass.


#### What is constructor chaining?

Constructor chaining is a phenomenon which happens during inheritence, where a subclass constructor makes a call to its superclass constructor, which further makes a call to its respective superclass constructor until finally when the Object class constructor is called.

Constructor chaining can be done either implictily by the compiler or expilictly by the programmer.
Whenever user-defined parameterized constructors are present in the chain, explicit constructor chaining must be done because while implicit constructor chaining the compiler will only call non-parameterized constructor. It will never call parameterized constructors.


#### What is the usage of this() and super() statements?

this() statement in Java is used to call the no-argument or parameterized constructors of the class in operation.
Whereas super() statement is used to call the no-argument or parameterized constructors of superclass from its subclass.

super() or this() can be used only in constructor body and whenever used, it should be the first statement of the constructor body.
One costructor body can only have either super() statement or this() statement.
Also, there can be only one super() statement in one constructor body. Using multiple super() statements is not allowed in Java.

The subclass constructor can either make a implicit call or an explicit call to the superclass constructor.
Implicit call is made by compiler whereas explicit call is made by programmer.

Implicit calls happens only when the superclass has a no-argument constructor.


#### What is inheritance and what are its types?

A class inheriting members of another class is known as inheritace.
One class can inherit members of another class using extends keyword.
The class from which members are inherited is called superclass.
The class to which members are inherited is called subclass.

Only non-static members are inherited from superclass to subclass.
If superclass has static or private members, then such members will not be inherited to the subclass.
Also, the constructor of superclass will not be inherited by the subclass.

With inheritance, we can achieve:

1. Code usability
2. Code extensability
3. Code enhancement

There are 4 types of inheritance:

1. Single inheritance
2. Multi-level inheritance
3. Multiple inheritance
4. Hierarchial inheritance

###### Single inheritance

In this type of inheritance, the subclass inherits from only one superclass.

###### Multi-level inheritance

In this type of inheritance, a subclass inherites from its superclass, which further inherits from its own superclass and so on.
In this type of inheritance, a class acts as both a subclass as well as a superclass.

###### Multiple inheritance

In this type of inheritance, one subclass inherits from more than one superclass.
This type of inheritance is not supported in Java.

###### Hierarchial inheritance

In this type of inheritance, a superclass has more than one subclass.
This type of inheritance is used to achieve generalization.
All subclasses have the common properties of superclass.


#### Why Java doesn't support multiple inheritance?

Java doesn't support multiple inheritence because, there can be only one super() statement in one constructor body. Hence, it is not possible to initialize two superclasses from one subclass.
Also, it leads to the Diamond problem, which says, if a subclass extends two or more superclasses and two or more superclasses have a method with same name but different implementation, there is an ambiguity as to which implementation will be inherited by the superclass. That is why JVM allows programmer to write only one super() statement in one constructor body.


#### What is HAS-A and IS-A relationship?

Two classes are said to have HAS-A relation (or, Object Composition relation) when instance of one class belongs to (or, is the member of) the other class.

If one class is composed of or is made of the instance of the other class, then this type of HAS-A relation is called Composition. For example, Car class HAS-A Object Composition relation with Wheel class.
Object Composition relation between two classes is represented on a UML diagram with black colored diamond pointed from contained class to the containing class.

Whereas, if one class can have or possess the instance or multiple instances of the other class, then this type of HAS-A relation is called Aggregation relation. For example, a Pond class may or may not contain Duck class instances.
Aggregation relation between two classes is represented on a UML diagram with hollow diamond pointed from possessed class to the possessing class.

Two classes are said to have IS-A relation (or, Inheritance relation) when one class extends the other class (or, one class IS-A extension of the other class. Or, one class inherits non-static properties from the other class).
Two interfaces are said to have IS-A relation when one interface extends the other interface.
A class is said to have IS-A relation with an interface when that class implements that interface.
We can identify IS-A relation or Inheritence relation easily by looking for extends keyword or implemets keyword.
For example, Car is a Vehicle, so we can say Car class has IS-A relation with the Vehicle class.
IS-A relation between two classes is represented on a UML diagram with a black colored arrow pointed from the extending class to extended class, or with a hollow arrow from implemeting class to the implemented interface.

Both, IS-A relation (Inheritence relation) and HAS-A relation (Object Composition relation) are used to achieve code reusability.
IS-A relaition differs from HAS-A relation in following ways:

1. It is easier to change the class implementing Composition than the class implementing Inheritance, because the change of a superclass impacts the inheritance hierarchy to subclasses.
2. It is not possible to subclass a method with same signature as declared in the superclass but with a different return type. Whereas, the same is possible in a Composition relation. Composition allows programmer to change the interface of a front-end class without affecting the back-end classes.
3. Composition is dynamic binding (run time binding) while Inheritance is static binding (compile time binding).
4. It is easier to add new subclasses than it is to add new front-end classes, because Inheritance comes with polymorphism. if you have a code that relies on a superclass interface, that code can work with a new subclass without change. Whereas this is not true for Composition, unless composition is used with interfaces.

Inheritance should not be used just to get code reuse. If all that is really required is code reuse, Composition should be used.
Inheritance should not be used just to get polymorphism. If there is no nautral IS-A relationship, use Composition with interfaces.


#### What is method overloading? Can main() method be overloaded?

In a class, defining multiple methods with same name but different parmeters is called method overloading.
The parameters should differ either in terms of parameter type or in terms of parameter length or both.

In a class, we can overload both static and non-static methods.
Overloaded methods are invoked based on the parameters.

Superclass methods can be overloaded in the subclass.

Method overloading is used to achieve compile time polymorphism.

While developing applications, if we come accross an operation that should be performed with different parameters and parameter types, then we must use method overloading.
For example, logging in to Facebook using phone number, or email or username.

Yes, main() method can be overloaded but the only version of main() method that JVM will look for starting execution of a class is:
public static void main(String[] args){...}


#### What is method overriding? Explain?

Inheriting a method from the superclass and changing its implementation in the subclass according to the subclass specification is called Method overriding.
Method overriding can be done only in a subclass.
When overriding a method, the subclass should retain the signature of method from the superclass and must provide a different implementation body.

Whenever we create a subclass object that is having a overridden method, then the object is said to use method overriding.

Subclass cannot override the follwing methods:

1. Static methods, because static methods cannot be inherited.
2. Private methods, because scope of private methods is limited to the class in which they are decalred. Private method are not accessible outside the class, not even to the subclasses. So private methods are not inherited and hence cannot be overloaded.
3. Final methods, because any method marked final cannot be re-implemented. Final keyword restricts changing the method implementation. However final methods can be inherited to subclasses.

Method overriding is used to achieve runtime polymorphism.

While developing an application whenever we come accross a functionality where the implementation needs to be changed, then we use method overriding.

A subclass can override as well as overload the superclass methods.


#### What do you mean by final class?

A class declared using final keyword is called final class. The final keyword restricts a class from being inherited.

If a developer tries to inherit a final class, the compiler will successfully compile the code but "java.lang.VerifyError" exception will be thrown at runtime.


#### What is an abstract class?

A class declared using abstract keyword is called abstract class. The abstract keyword allows a class to have abstract methods. However, it is not enforced upon the developer. An abstract class can also have none to all methods as concrete methods. But even if one method in the class is abstract, it is mandatory to declare the class using abstract keyword because a non-abstract class cannot have abstract methods.

An abstract class also has a constructor. But still, an abstract class cannot be instantiated using the new keyword because there may be some abstract methods which do not have implementation in the abstract class. Hence, compiler does not allow making instance of any class declared using abstract keyword.

Abstract class is not a pure abstract body as it can have concrete methods too. Hence, if a complete abstract body is required, developer should use interfaces.

The abstract keyword cannot be combined with the static or private or final keywords as they all restrict providing concrete implementation to the abstract methods in a class.


#### What is an interface and how is it different from an abstract class?

Interface is a Java non-primitive type which is used to define abstract methods.
By default interface itself is abstract.
In an interface we can declare only static final data members.
In an interface body we can only declare abstract methods. Compiler does not allow declaring concrete methods in interface.
Interface does not have a constructor. Because purpose of a constructor is to initialize the data members, and since all data members in an interface are static final, we have to initialize them at the time of declaration. Due to this reason, there are no data members for the constructor to initialize, hence there is no need for a constructor in interface.
Default access in an interface is public.
Methods of an interface must be implemented by an implementing class.
The class which provides implementation to the interface methods is knows an implementation class.
If the implementation class does not provide implementation for all the methods of an interface, then the class should be declared as abstract class.
A class can implement an interface by using implements keyword.
A class can implement any number of interfaces.
An interface can inherit form another interface using extends keyword, but it cannot inherit from a class using inherits keyword.
We can declare a reference variable of interface type but  we cannot create an object of interface type.
For a reference variable of interface type, we can either assign a null or an instance of an implementation class or instance of subclasses of implementation class.

Difference between interface and abstract class:
1. Interface is used for pure abstraction. Whereas abstract classes are used for partial abstraction.
2. Interface can only have abstract methods and static final data members. Whereas abstract class can have abstract as well as concrete methods and non-static data members.
3. Interface does not have a constructor. Whereas abstract classes have constructor. Both interface and abstrace class cannot be instantiated.
4. Interface is implemented by implementation class. Whereas abstract class is extended by non-abstract class.
5. A class can implement multiple interfaces. Whereas a class can only extend one abstract class.
6. Interfaces facilitate multiple inheritance. Whereas abstract classes do not facilitate multiple inheritance.


#### What is abstraction and how to achieve it?

Abstraction is the process of hiding the implementation of a class and providing an public interface to use essential functionality.
Using abstraction, an objects functionality is hidden from usage of the object.
An interface is provided to use the essential functionality of the object without showing its implementation.

There are three essenstial steps to achieve abstraction in Java:

1. Define the interface: Define the essential functionality of an object in an public interface.
2. Define the implementation class: Provide implementation for all functionality of an object, as per requirement or specification, in an implementation class.
3. Upcasting: Refer to the essential functionality of the object using reference variable of interface type.

Advantages of using interface:

1. Hiding the implementation.
2. Any changes made in thte implementation will not impact the usage of application.
3. The functioning of application is not dependent on a concrete class. Instead it depends on an interface type and any concrete class implementing the interace is acceptable to make the application functional. This is also known as Loose coupling.

For example, we use a smartphone. Essential functionality of the smartphone is shown to the user in an interface displayed on the screen. But complete implementation is hidden inside the casing. The user does not need to know the implementation in order to use the smartphone functionality and complete the task he is trying to accomplish.

Example of tight and loose coupling:

A user object wants to commute from his home to office. Now, in the first case, the implementation class of this user object is using a concrete method move() implemented in a concrete class Car to help himself commute from one place to another. Due to some reason, this car object is in a bad state and is not working, or is not available. Now, since the car object's functionality is not available, the user object cannot commute. This kind of coupling between objects is called tight coupling.

In a second case, the implementation class of user object is using an abstract method move() declared in an abstract interface Vehicle and implemented in many implementation classes such as Car, Bike, Bus etc to help him commute from one place to another. Here, the user object will accept any type of concrete Vehicle type, be it a Car, or a bike, or a bus, or any other vehicle type. Even if the car object is not available, the user object will still accept other concrete vehicle type objects to help him commute. The functionality of user object is not dependent entirely on a particular concrete Car object. This kind of coupling is called Loose coupling.


#### What is encapsulation?

Wrapping the data members and member methods together as a single unit in a class is knows as encapsulaition.
In encapsulation, the data members of one class will be hidden from other classes and can be accessed only through the member methods of their current class. This is also knows as data hiding.

To achieve encapsulation:

1. Declare the data members with private access specifier.
2. Provide public getter and setters to modift and view the data members.

Advantages of encapsulation:

1. The feilds of a class can be made read-only or write-only.
2. The class can have total control over what is stored in its feilds.
3. The users of a class do not know how the class is storing its data. A class can change the data type of a feild and users of the class will not have to change any of their code to adapt to the changes in class implementation.


#### What is Java Bean class?

Java Bean is a class that follows the following conventions:

1. The class has a public default constructor with no arguments.
2. The class properties are accessibe using getters (or accessor methods) and setters (or mutator methods), which are declared according to the standard naming convention.
3. The class is serializable, that is, it implements serializable interface. This allows applications to reliably save, store and restore 


#### What is Singleton class?

A class for which the instantantion has been restricted to just one object is called Singleton class. Singleon class pattern is useful when exactly one object of a particular class is needed to coordinate actions accross the system.
For example, for one program, only one database connction is required. Hence, we need only one object to provide the database connection through out the application.

Singleton class implementation is done using:

1. A private constructor for the class
2. A feild to hold the result of the constructor
3. A public static accessor method with a name like getInstance()
4. Necessary logic which restricts the creation of more than one object


#### What are different access specifiers in Java? Explain.

Access specifiers in Java: private, package level (default), protected, public

1. Private: private access specifier restricts access to class level
2. Package level: package level (or default) access specifier restricts access to package level
3. Protected: protected access specifier restricts access to package level but members of the class can be accessed outside by using inheritance
4. Public: public access specifier allows members to be accessed from anywhere

Members of class can be declared with any of the four access specifiers. But the same is not true for all the classes.
If programmer is writing an inner class then it can be declared with any of the four access level.
The outer class should always be declared with public or package level access i.e default access.

Constructor of a class can have any of the four access levels.
If the class is having default constructor, then such constructor will have same access level as that of its class.

While overriding, the subclass should retain the same access level as that of the superclass.
Method and subclasses can be declared with stronger access level than that of the superclass but not weaker access level than that of the superclass.


#### What is the need to override toString() method?

In Object class, the toString() method is implemented to return a string which represents the fully qualified class name and address of the object created.
It's return type is String. It is decalred using public access specifier and it does not take any arguments
Purpose of toSring() method is to show the state of an object. Programmer can override the toString() method to return or print relevant properties or data members useful for the end user.


#### What is the use of hashCode() and equals() methods?

hashCode() method is declared in java.lang.Object class.
It's return type is int. It is declared using public access specifier and it does not take any argument.
The default implementation of hashCode() method processes the memory address of an object to an integer value.

equals() method is also declared in java.lang.Object class.
It's return type is boolean. It is declared using public access specifier and it takes one Object type argument.
The default implementation of equals() method is used to make equal comparision between two objects. Internally equals() method calls the hashCode() method.
If the hash value of two objects are same then equals() method returns true otherwise it returns false.


#### Why do we need finalize() and clone() methods?

finalize() method is declared in java.lang.Object class.
It's return type is void. It is declared using protected access specifier and it does not take any argument.
Purpose of finalize() method is to cleanup heap memory during garbage collection. finalize() method can be used when ever programmer wants to destroy an object.

clone() method is declared in java.lang.Object class.
It's return type is Object. It is declared using protected access specifier and it does not take any argument.
Purpose of clone() method is to create a clone of the object on which it is invoked. It can be used when a clone of an object is required.


#### What is the difference between String class, String buffer class and String builder class?

Following are the differences between String class, String buffer class and String builder class:

1. Immutable
String class is immutable. Where as String buffer and String builder classes are not immutable.

2. Final
All three classes are final.

3. Methods overridden
In string class toString(), hashCode() and equals() methods are overridden. Whereas in String buffer and String builder classes only toString() method is overridden.

4. Comparable interface
String class implements comparable interface, hence its objects can be sorted. Whereas String buffer and String builder classes do not implement Comparable interface. Hence their objects cannot be sorted.

5. Methods Synchronized
String buffer class has synchronized methods. Where as String class and String builder class do not have synchronized methods.

6. Thread safe
String buffer class is thread safe. Whereas String and String builder class are not thread safe.


#### Why is String class immutable? Explain?

Java uses the concept of String literal. Suppose there are five reference variables of String type, all reffering to one String object "Sachin". If one reference variable changes the object "Sachin", this change will be reflected accross all reference variables. This is not desirable. That is why String class has been kept immutable in Java.


#### What is String pool area?

String objects are stored in a seperate area on the Heap memory, known as String pool area.

This area is divided into two types, Constant pool area and Non-constant pool area.

Constant pool are doesn't allow duplicate string objects to be stored seperately in the memory.
Whereas, Non-constant pool area allows duplicate string objects to be stored in the memory.

String object created using new operator will always be stored in non-constant pool area.
Where as string objects created without using new operator will be stored in constant pool area.

In constant pool area, different reference variables with same string literal value will point to the same String object.
Whereas, in non-constant pool area, different references with same string literal value will not necessarily point to the same string object.

For example, let us make four string objects:

String s1 = new String("JSpiders");
String s2 = "JSpiders";
String s3 = new String("JSpiders");
String s4 = "JSpiders";

Here, s1 and s3 will refer to two different string objects stored in the non-constant pool area. Whereas s2, s4 will refer to one string object stored in constant pool area.
Moreover, if we compare bit pattern stored in s1, s2, s3, s4:

s1 == s3 ? false. Because s1 and s3 refer to two different string objects stored in non-constant pool area. Hence, s1 and s3 will contain different bit pattern that refers to object location on memory.

s2 == s4 ? true. Since, s2 and s4 refer to the same object stored in constant pool are on memory, s2 and s4 will contain same bit pattern that refers to the same object location on memory.

s1 == s2 ? false. s1 refers to a string object stored on non-constant pool area and s2 refers to a string object stored on constant pool area. Hence, s1 and s2 contain different bit pattern that refers to object location on memory.


#### What is polymorphism? Explain.

An object showing different behaviors at different stages of its life cycle is known as polymorphism.

There are two different types of polymorphism:

1. Compile-time polymorphism
2. Run-time polymorphism

In compile-time polymorphism, depending on the parameters used, the method declaration is binded to its definition at the time of compilation by the compiler. This type of binding is also known as early binding or static binding because once a method declaration is binded to its definition, it cannot be re-binded.

In run-time polymorphism, depending on the class instance created at run-time, the method declaration is binded to its definition by JVM. This type of binding is also known as late binding or dynamic binding because once a method declaration is binded to its definition, it can be re-binded to different definition later during run-time.

To achieve compile-time polymorphism, we can overload methods, or declare methods as static, or declare methods as final.

To achieve run-time polymorphism, following conditions need to be satisfied:
1. Inheritance
2. Method overriding
3. Type casting 


#### What is upcasting and downcasting?

Casting one type of info to another type is called type casting.
There are two types of type casting in Java:

1. Primitive type casting
2. Class type casting

In Primitive type casting, one primitive datatype is casted to another primitive datatype.
Primitive type casting can be of two types:

1. Widening
2. Narrowing

Widening:
Casting lower order datatype to higher order datatype is called Widening.
Widening can be done explicitly or implicitly. If compiler performs widening operation then it is called implicit widening. If programmer performs widening operation then it is called explicit widening.

Narrowing:
Casting higher order datatype to lower order datatype is called Narrowing.
Narrowing cannot be done implicitly by compiler. Hence, narrowing operation must be done explicitly by programmer only. When narrowing operation is performed, data loss wil occur.


In Class type casting, one class type object is casted to another class type object.
Class type casting can be of two types:

1. Upcasting
2. Downcasting

Class type casting can only be done if there is an IS-A relation between two classes. That is, one class extends the other class.

Upcasting:
Casting subclass type object to superclass type object is known as upcasting.
Upcasting can be done either implicitly by compiler ot explicitly by programmer.

Downcasting:
Casting superclass type object to subclass type object is known as downcasting.
Downcasting cannot be done implicitly by compiler. Hence downcasting operation must be done explicitly by programmer only.
Downcasting operation must only be performed on an upcasted object, because the object being downcasted to subclass type should have the relevant class properties of the subclass type. And this is only possible if downcasting operation is being performed on a previously upcasted subclass object.

There is no data loss in class type casting. Class specific properties may become inaccessible but they are still not removed from the object stored in memory.


#### When does JVM throw ClassCastException? Explain why.

ClassCastException is a run-time exception thrown by JVM while performing class casting.

When casting operation is performed on an object, that does not have relevant properties of the class type it is being casted to, then JVM throws ClassCastException.

ClassCastException can be avoided by using the "instanceof" operator. Using instanceof operator, we can first check whether the object that is being casted from one class type to another class type has the relevant properties of the class type it is being casted to. If so, then the instanceof operator returns true, else it returns false.


#### What is generalization? Explain what it means.

Generalization is the process of extracting the shared characteristics from two or more classes, and combining them into a generalized superclass.

Specialization is the exact opposite of generalization. In specialization, new subclasses are created from existing class.


#### What is loose coupling?



 
































































