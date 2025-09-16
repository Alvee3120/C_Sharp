# Abstract Class
An abstract class is a class that cannot be instantiated directly. It can contain both abstract methods (which do not have a body) and concrete methods (which have an implementation). Abstract classes allow you to provide a common base for other classes.

```cs
using System;

public abstract class Animal //Abstract Class
{

    public abstract void MakeSound(); //Abstract Method

    public void eat() //Normal method
    {

        Console.WriteLine("Eating");
    }
}

class Kutta: Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Ghew Ghew");
    }
}

class Goru : Animal
{
    public override void MakeSound() {


        Console.WriteLine("Hambaaaaaaa");
    }
}

class myProgram{
        public static void Main(string[] args)
        {
    
            Animal k1 = new Kutta();
            k1.MakeSound();
            k1.eat();

            Animal g1 = new Goru();
            g1.MakeSound();


        }
}
```


Here MakeSound is a abstract method which must be call in every derive class. 
and Eat is a normal class.

Output
```bash
Ghew Ghew
Eating
Hambaaaaaaa
```


# Interface

In C#, an interface is a contract or blueprint that defines a set of methods, properties, events, or indexers that classes or structs must implement. Interfaces themselves do not provide any implementation for the methods; they only declare the signatures. Any class or struct that implements an interface is required to provide its own implementation of the interface's methods.


```cs
using System;


interface IDriveable
{

    void Start();
    void Stop();
}

class Car : IDriveable
{
    public void Start()
    {
        Console.WriteLine("Car Started");
    }
    public void Stop()
    {
        Console.WriteLine("Car Stoped");
    }
}

class Bike : IDriveable
{
    public void Start()
    {
        Console.WriteLine("Bike Started");
    }
    public void Stop()
    {
        Console.WriteLine("Bike Stoped");
    }
}

class myProgram
{
    public static void Main(string[] args)
    {
        IDriveable c = new Car();
        c.Start();
        c.Stop();

        IDriveable b = new Bike();
        b.Start();
        b.Stop();
    }
}
```

Output
```bash
Car Started
Car Stoped
Bike Started
Bike Stoped
```


# Main Difference Between Abstract and Interface

# Difference Between Abstract Class and Interface in C#

| Feature                     | Abstract Class                                          | Interface                                               |
|-----------------------------|---------------------------------------------------------|---------------------------------------------------------|
| **Purpose**                  | An abstract class is used to provide a common base for classes with some implementation. | An interface defines a contract that implementing classes must adhere to, without providing any implementation. |
| **Implementation**           | An abstract class can have both abstract methods (without implementation) and methods with implementations. | An interface can only have method signatures (no implementation). |
| **Inheritance**              | A class can inherit from only one abstract class (single inheritance). | A class can implement multiple interfaces (multiple inheritance). |
| **Constructors**             | Abstract classes can have constructors.                | Interfaces cannot have constructors.                     |
| **Access Modifiers**         | Abstract class members can have access modifiers (`public`, `protected`, etc.). | Interface members are `public` by default, and cannot have other access modifiers. |
| **Fields**                   | Abstract classes can have fields (variables).          | Interfaces cannot have fields.                          |
| **Properties**               | Abstract classes can have properties with or without implementation. | Interfaces can only define properties without implementation. |
| **Methods**                  | Abstract class methods can have both implementation and abstraction. | Interface methods can only declare the signature, without any implementation. |
| **Static Members**           | Abstract classes can have static members (fields, methods, etc.). | Interfaces cannot have static members.                   |
| **Default Implementation**   | Abstract classes can provide a default implementation for methods. | Interfaces (in C# 8.0 and later) can provide default method implementations, but traditionally, interfaces do not. |
| **Multiple Inheritance**     | A class can inherit from one abstract class but can implement multiple interfaces. | A class can implement multiple interfaces, which allows a form of multiple inheritance. |
| **Events**                   | Abstract classes can have events.                       | Interfaces can declare events.                           |
| **Use Case**                 | Used when classes share common functionality or need to inherit shared behavior. | Used when you want to enforce certain behavior without dictating how it should be implemented. |
| **Memory Usage**             | Abstract classes can hold state (e.g., fields), which means more memory usage. | Interfaces do not hold state; they only define behavior. |

