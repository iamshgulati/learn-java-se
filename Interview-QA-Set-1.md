# Interview QA Set-1


#### What is Class and Object?

Class is a template or blueprint used to define an object in Java.
Class contains elements like methods, variables, blocks and sub-classes.

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

No, we cannot override constructors because every class has its own constructor and constructor of a super class is not inherited by sub-class during inheritance. Hence, we can only overload constructor within a class but can never override them.


#### What is the difference betweeb this and super keyword?

This keyword in Java stores the address of the current object under operation.
Using this keywork, we refer to the members of current object.
Whenever we invoke a method on an object reference variable, such as d1.display();, the value of this keyword will be updated to the value stored by d1 reference variable.
In-fact, the compiler automatically adds this keyword to all non-local variable references as long as there is no conflict of scope in non-local variables and local variables. If there is a conflict of scope between non-local variables and local variables, it is upto the programmer to use this keyword to refer to the non-local variable wherever required.

Whereas, with super keyword we can access the members of super class from its subclass.


#### What is constructor chaining?

Constructor chaining is a phenomenon which happens during inheritence, where a sub-class constructor makes a call to its super class constructor, which further makes a call to its respective super class constructor until finally when the Object class constructor is called.

Constructor chaining can be done either implictily by the compiler or expilictly by the programmer.
Whenever user-defined parameterized constructors are present in the chain, explicit constructor chaining must be done because while implicit constructor chaining the compiler will only call non-parameterized constructor. It will never call parameterized constructors.


#### What is the usage of this() and super() statements?

this() statement in Java is used to call the no-argument or parameterized constructors of the class in operation.
Whereas super() statement is used to call the no-argument or parameterized constructors of super class from its sub-class.

super() or this() can be used only in constructor body and whenever used, it should be the first statement of the constructor body.
One costructor body can only have either super() statement or this() statement.
Also, there can be only one super() statement in one constructor body. Using multiple super() statements is not allowed in Java.

The sub-class constructor can either make a implicit call or an explicit call to the super class constructor.
Implicit call is made by compiler whereas explicit call is made by programmer.

Implicit calls happens only when the super class has a no-argument constructor.


#### What is inheritance and what are its types?

A class inheriting members of another class is known as inheritace.
One class can inherit members of another class using extends keyword.
The class from which members are inherited is called super class.
The class to which members are inherited is called sub-class.

Only non-static members are inherited from super class to sub-class.
If super class has static or private members, then such members will not be inherited to the sub-class.
Also, the constructor of super class will not be inherited by the sub-class.

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

In this type of inheritance, the sub-class inherits from only one super class.

###### Multi-level inheritance

In this type of inheritance, a sub-class inherites from its super class, which further inherits from its own super class and so on.
In this type of inheritance, a class acts as both a sub-class as well as a super class.

###### Multiple inheritance

In this type of inheritance, one sub-class inherits from more than one super class.
This type of inheritance is not supported in Java.

###### Hierarchial inheritance

In this type of inheritance, a super class has more than one sub-class.
This type of inheritance is used to achieve generalization.
All sub-classes have the common properties of super class.


#### Why Java doesn't support multiple inheritance?

Java doesn't support multiple inheritence because, there can be only one super() statement in one constructor body. Hence, it is not possible to initialize two super classes from one sub-class.
Also, it leads to the Diamond problem, which says, if a sub-class extends two or more super classes and two or more super classes have a method with same name but different implementation, there is an ambiguity as to which implementation will be inherited by the super class. That is why JVM allows programmer to write only one super() statement in one constructor body.


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

1. It is easier to change the class implementing Composition than the class implementing Inheritance, because the change of a super class impacts the inheritance hierarchy to sub-classes.
2. It is not possible to sub-class a method with same signature as declared in the super class but with a different return type. Whereas, the same is possible in a Composition relation. Composition allows programmer to change the interface of a front-end class without affecting the back-end classes.
3. Composition is dynamic binding (run time binding) while Inheritance is static binding (compile time binding).
4. It is easier to add new sub-classes than it is to add new front-end classes, because Inheritance comes with polymorphism. if you have a code that relies on a superclass interface, that code can work with a new subclass without change. Whereas this is not true for Composition, unless composition is used with interfaces.

Inheritance should not be used just to get code reuse. If all that is really required is code reuse, Composition should be used.
Inheritance should not be used just to get polymorphism. If there is no nautral IS-A relationship, use Composition with interfaces.


#### What is method overloading? Can main() method be overloaded?

In a class, defining multiple methods with same name but different parmeters is called method overloading.
The parameters should differ either in terms of parameter type or in terms of parameter length or both.

In a class, we can overload both static and non-static methods.
Overloaded methods are invoked based on the parameters.

Super-class methods can be overloaded in the sub-class.

Method overloading is used to achieve compile time polymorphism.

While developing applications, if we come accross an operation that should be performed with different parameters and parameter types, then we must use method overloading.
For example, logging in to Facebook using phone number, or email or username.

Yes, main() method can be overloaded but the only version of main() method that JVM will look for starting execution of a class is:
public static void main(String[] args){...}


#### What is method overriding? Explain?

Inheriting a method from the super class and changing its implementation in the sub-class according to the sub-class specification is called Method overriding.
Method overriding can be done only in a sub-class.
When overriding a method, the subclass should retain the signature of method from the super class and must provide a different implementation body.

Whenever we create a sub-class object that is having a overridden method, then the object is said to use method overriding.

Sub-class cannot override the follwing methods:

1. Static methods, because static methods cannot be inherited.
2. Private methods, because scope of private methods is limited to the class in which they are decalred. Private method are not accessible outside the class, not even to the sub-classes. So private methods are not inherited and hence cannot be overloaded.
3. Final methods, because any method marked final cannot be re-implemented. Final keyword restricts changing the method implementation. However final methods can be inherited to sub-classes.

Method overriding is used to achieve runtime polymorphism.

While developing an application whenever we come accross a functionality where the implementation needs to be changed, then we use method overriding.

A sub-class can override as well as overload the super class methods.


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
For a reference variable of interface type, we can either assign a null or an instance of an implementation class or instance of sub-classes of implementation class.

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



































































