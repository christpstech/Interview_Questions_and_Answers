### **C# .Net Interview Questions and Answers**

#

1.  **What is garbage collection?**

    > - Garbage collection is a **_memory management technique_**.

    > - Garbage collection is responsible of **_managing the memory and automatically freeing up memory_** that is no longer been used by the application.

2.  **Difference between IEnumerable and IQueryable?**

    > | **`IEnumerable`**                                                                                                         | **`IQueryable`**                                                                     |
    > | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
    > | IEnumerable namespace is **System.Collection**                                                                            | IQueryable namespace is **System.Linq**                                              |
    > | IEnumerable executes the selected query in server side, **loads data in-memory in client side and then filter the data**. | IQueryable executes the selected query in server **side with help of it's filters**. |

3.  **What is abstraction?**

    > _Hiding the implemetation and showing essential features_.

4.  **What is encapsulation?**

    > _Wrapping up related data and methods into a single unit_

5.  **What is polymorphism?**

    > A ability of an message to display in more then one form.

    #### **Type of polymorphism**

    > - Compile time => Overloading
    > - Runtime => Overriding

6.  **What is generic and Collections?**

    #### **Generic:**

    > **_Reuable code with type safe_** for working with different type.

    #### **Collections:**

    > Data structure for **_storing and manipulating groups of object_** not type safe.

7.  **What is Web API?**

    > - Web API => **Application Programming Interface**
    > - **_Provides interface between software application_**

8.  **OverLoading and Overriding in c#?**

    #### **OverLoading:**

    > Multiple methods with **_same name but different parameters_**

    #### **Example**

    ```
    public class Area {
      public double area(double x) {
          double area = x * x;
          return area;
      }
      public double area(double a, double b) {
          double area = a * b;
          return area;
      }
    }
    ```

    #### **Overriding:**

    > Overriding a virtal method that is inhereted from the base class.

9.  **What is JIT in c#**

    > - Just in Time compiler
    > - Convert intermediate language to native code

10. **Value type and Reference type?**

    ##### **Value type:**

    > - Value type holds the value of the variable directly on it's memory space.
    > - Stack memory is used

    ##### **Reference type:**

    > - Contains a pointer that points to another memory location that holds data.

11. **Delegate in c#?**

    > Defines a method signature, and hold references of one or more methods with the same signature.

    #### **Example:**

        using System;
        using System.Collections.Generic;
        class Program
        {
          static int calculateSum(int x, int y)
          {
            return x + y;
          }

          public delegate int myDelegate(int num1, int num2);

          static void Main()
          {
              myDelegate d = new myDelegate(calculateSum);

              int result = d(5, 6);

              Console.WriteLine(result);
          }
        }

12. **What is a Abstract class?**

    > It is a restricted class and connot be used to create object.

13. **What is Interface?**

    > An interface is a complitly abstract class which contains only abstract method & properies.

14. **What is the difference between an Array and ArrayList in C#?**

    #### **Aarry:**

    > - Fixed size
    > - Type-safe
    > - Better performance for direct element access
    > - Single type
    > - Length property
    > - Efficient memory allocation

    #### **Systax:**

    ```
    int[] arr = new int[4];
    arr[0] = 1;
    arr[0] = 4;
    arr[0] = 3;
    ```

    #### **AarryList:**

    > - Dynamic size
    > - Type flexibility
    > - Boxing and unboxing
    > - Slightly lower performance
    > - Count property
    > - Dynamic memory allocation

    #### **Systax:**

    ```
    ArrayList list = new ArrayList();
    list.Add(false);
    list.Add(10);
    list.Add(10.10);
    list.Add("c#");
    ```

15. **What is the difference between an Managed code and Unmanaged code in C#?**

    #### **Managed code:**

    > - Code that **_runs within a managed runtime environment_** (e.g., .NET, Java).
    > - Memory management is handled by the **_runtime through automatic garbage collection_**.
    > - Platform-independent and portable.

    #### **Unmanaged code:**

    > - Code that **_runs directly on the operating system_**.
    > - Manual memory allocation and deallocation.
    > - Platform-specific and less portable.

16. **What are the differences between ref and out keywords?**

    #### **ref:**

    > - **_Parameters should be initialized_** before being passed to "ref"
    > - **_Not necessary to initialize the value of a parameter before returning_** it to the calling method.
    > - The passing of value through "ref" parameter is **useful when the called method needs to change the value of that parameter**.
    > - When "ref" is used the data passage is **_bidirectional_**.
    > - _If we want to change an existing value of a variable inside a method, we are going to use the ref keyword._

    #### **out:**

    > - **_Parameters don't need to be initialized_** before being passed to "out".
    > - It is **_necessary to initialize the value of a parameter before returning_** it to the calling method.
    > - Useful when a method **_returns multiple values_**.
    > - When "out" keyword is used the **_data flows in one direction_**.
    > - _if we want to assign a completely new value to the variable inside a method, then we use the out keyword._

    #### **Example:**

        class Program
        {
          public static void ChangeRef(ref int numberRef)
          {
            numberRef = 25;
            Console.WriteLine($"Inside the ChangeRef method the numberRef is {numberRef}");
          }

          public static void ChangeOut( out int numberOut)
          {
              numberOut = 60;
              Console.WriteLine($"Inside the ChangeOut method the numberOut is {numberOut}");
          }

          static void Main(string[] args)
          {
              int numberRef = 15;

              Console.WriteLine($"Before calling the ChangeRef method the numberRef is {numberRef}");
              ChangeRef(ref numberRef);
              Console.WriteLine($"After calling the ChangeRef method the numberRef is {numberRef}");

              Console.WriteLine();

              int numberOut;
              Console.WriteLine("Before calling the ChangeOut method the numberOut is unassigned");
              ChangeOut(out numberOut);
              Console.WriteLine($"After calling the ChangeOut method the numberOut is {numberOut}");

              Console.ReadKey();
          }
        }

17. **What are the types of classes in C#?**

    #### **Static class:**

    > - Static class, defined by the keyword **_‘static’ does not allow inheritance_**. Therefore, **_you cannot create an object_** for a static class.

    #### **Systax:**

    ```
    static class classname
    {
      //static data members
      //static methods
    }
    ```

    #### **Partial class:**

    > - Partial class, defined by the keyword **_‘partial’ allows its members to partially divide or share source (.cs) files_**
    > - Partial classes implement the functionality of a **_single class into multiple files_**. These **_multiple files are combined into one_** during compile time.

    #### **Systax:**

    ```
    public partial Clas_name
    {
          // code
    }
    ```

    #### **Abstract class:**

    > - Abstract classes are classes that **cannot be instantiated where you cannot create objects**. Abstract classes work on the **OOPS concept of abstraction**. Abstraction helps to _Hiding the implemetation and showing essential features_

    #### **Sealed class:**

    > - Sealed classes are classes that ca**_nnot be inherited_**. Use the keyword sealed to **_restrict access to users to inherit that class_**.

    #### **Systax:**

    ```
    sealed class classname
    {
      //data members
      //methods
    }
    ```

18. **What is Boxing and Unboxing in C#?**

    > _The two functions are used for ***typecasting the data types***:_

    #### **Boxing:**

    > Boxing converts **_value type (int, char, etc.) to reference type (object)_** which is an i**mplicit conversion process** using object value.

    #### **Example**

    ```
    int num = 23; // 23 will assigned to num
    Object Obj = num; // Boxing
    ```

    #### **Unboxing:**

    > Unboxing **_converts reference type (object) to value type (int, char, etc.)_** using an **_explicit conversion process_**.

    #### **Example**

    ```
    int num = 23;         // value type is int and assigned value 23
    Object Obj = num;    // Boxing
    int i = (int)Obj;    // Unboxing
    ```

19. **Difference between the Equality Operator (==) and Equals() Method in C#?**

    #### **Equality operator (==):**

    > - Equality operator is a **_reference type_** which means that if equality operator is used, it will return true only if _both the references point to the same object_.
    > - Equality operator: **_Compares by reference_**

    #### **Equals() method:**

    > - Equals method is used to compare the **_values carried by the objects_**.
    > - Equals(): **_Compares by value_**

20. **What are Design Patterns?**

    > Design pattern is a **_flexible way to solve common design problems_**

    _These 23 patterns are grouped into three main categories_

    1. **Creational Patterns**

       > The Creational Design Pattern deals with **Object Creation and Initialization**.

       _There are 5 types of creational patterns_

       1. **Abstract Factory**
          > Design pattern provides an **_interface for creating families of related or dependent objects_**
       2. **Builder** >
          > - **Factory Method** => Creates an instance of several derived classes
          > - **Prototype** => A _fully initialized instance to be copied or cloned_
          > - **Singleton** => A class of which only a single instance can exist

    2. **Structural Design Pattern**

       > The Structural Design Pattern is basically used to **_Manage the Structure of Classes and Interfaces_** as well as **_Manage the Relationship Between the Classes and Interfaces_**.

       _There are 7 types of Structural patterns_

       1. **Adapter**
          > Match interfaces of different classes
       2. **Bridge**
          > Separates an object’s interface from its implementation
       3. **Composite**
          > A tree structure of simple and composite objects
       4. **Decorator**
          > Add responsibilities to objects dynamically
       5. **Facade**
          > A single class that represents an entire subsystem
       6. **Flyweight**
          > A fine-grained instance used for efficient sharing
       7. **Proxy**
          > An object representing another object

    3. **Behavioral Patterns**

       > Behavioral Design Patterns deal with the **_Communication Between Classes and Objects_**.
       > _There are 11 types of Behavioral patterns_

       1. **Chain of Responsibility**
          > A way of passing a request between a chain of objects
       2. **Command**
          > Encapsulate a command request as an object
       3. **Interpreter**
          > A way to include language elements in a program
       4. **Iterator**
          > Sequentially access the elements of a collection
       5. **Mediator**
          > Defines simplified communication between classes
       6. **Memento**
          > Capture and restore an object's internal state
       7. **Observer**
          > A way of notifying change to a number of classes
       8. **State**
          > Alter an object's behavior when its state changes
       9. **Strategy**
          > Encapsulates an algorithm inside a class
       10. **Template Method**
           > Defer the exact steps of an algorithm to a subclass
       11. **Visitor**
           > Defines a new operation to a class without change

21. **SOLID Principles in C#**

    > SOLID design principles in C# are **basic design principles**.

    #### **SOLID stands for:**

    > - S => Single Responsibility Principle
    > - O => Open/Closed Principle
    > - L => Liskov Substitution Principle
    > - I => Interface Segregation Principle
    > - D => Dependency Inversion Principle

    #### **Single Responsibility Principle**

    > Each software module **_should have one and only one reason to change_**.

    #### **Open/Closed Principle**

    > Software entities (classes, modules, functions, etc.) should be **open for extension**, but **closed for modification**.

    #### **Liskov Substitution Principle**

    > **_Subtypes must be substitutable for their base type_**.

    #### **Interface Segregation Principle**

    > Clients should not be **_forced to depend_** on methods they do not use.

    #### **Dependency Inversion Principle**

    > **_High-level modules should not depend on low-level modules_**. Both **_should depend on abstraction_**.

22. **Abstract class can inherit from multiple class c#?**

    > Since **_multiple inheritance is not supported_** in C#, you **_cannot inherit your class from two abstract classes_**.

    > C# does not support multiple inheritance because it **_might raise the issue of ambiguity_** (ex. When there is the class A and class B, and class C inherits class A and B. if class A and B have same **_non-abstract_** method, then there will be confution in class C which one to inherit.).

23. **When will use abstract and when will use interface in c#?**

    > **Abstract** classes should be **_used primarily for objects that are closely related_**.

    > **interfaces** are best suited for **_providing a common functionality to unrelated classes_**

24. **What is the difference between 401 and 403 status Code?**

    > **401 Unauthorized** is the status code to return when the **_client provides no credentials or invalid credentials_**

    > **403 Forbidden** is the status code to return when a client has valid credentials but **_not enough privileges to perform an action_** on a resource.

25. **How to print 1 to 1000 without any kind of loop in c#?**

        using System;

        public class HelloWorld
        {
            public static void PrintNumber(int i) {
                if (i <= 1000) {
                    Console.Write(i + " ");
                    PrintNumber(i + 1);
                }
            }
            public static void Main(string[] args)
            {
                PrintNumber(1);
            }
        }

26. **How to get duplicate record from the list using Linq in c#?**

    > string[] list= new string[]{"C#","Angular","Typescript","C#","Angular"};

    #### **Duplicate Record**

            var output  = list.GroupBy(x=> x).Where(x => x.Count() > 1).Select(x=> x.Key);

            Console.WriteLine(String.Join(",",output));

    #### **Unique Record**

            var output  = list.GroupBy(x=> x).Where(x => x.Count() >= 1).Select(x=> x.Key);

            Console.WriteLine(String.Join(",",output));

    #### **Non Duplicate Record**

            var output  = list.GroupBy(x=> x).Where(x => x.Count() == 1).Select(x=> x.Key);

            Console.WriteLine(String.Join(",",output));

27. **When we will use const and when will we use readonly in c# with example?**

    |       Key        |                          readonly                           |                         const                          |
    | :--------------: | :---------------------------------------------------------: | :----------------------------------------------------: |
    |     Purpose      | readonly keyword is used to **_create a readonly fields_**. | const keyword is used to **_create constant fields_**. |
    |       Type       |                           runtime                           |                      compile time                      |
    |      Change      |        value **_can be changed_** after declaration.        |    value **_cannot be changed_** after declaration     |
    |      Method      |           **_cannot be defined within a method_**           |         **_can be declared within a method._**         |
    | Value assignment |               **_can be done in contructor_**               |     **_can assigned at the time of declaration_**      |

28.
