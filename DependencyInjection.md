# Dependency Injection & Repository Design Pattern

## Dependency Injection

In software engineering, dependency injection is a programming technique in which an object or function receives other objects or functions that it depends on.
ASP.NET Core supports the dependency injection (DI) software design pattern, which is a technique for achieving Inversion of Control (IoC) between classes and their dependencies.

A dependency is an object that another object depends on. the following is MyDependency class with a WriteMessage method that other classes depend on:

```
public class MyDependency
{
    public void WriteMessage(string message)
    {
        Console.WriteLine($"MyDependency.WriteMessage called. Message: {message}");
    }
}
```

A class can create an instance of the MyDependency class to make use of its WriteMessage method. In the following example, the MyDependency class is a dependency of the IndexModel class:

```
public class IndexModel : PageModel
{
    private readonly MyDependency _dependency = new MyDependency();

    public void OnGet()
    {
        _dependency.WriteMessage("IndexModel.OnGet");
    }
}
```

##### The class creates and directly depends on the MyDependency class. Code dependencies, such as in the previous example, are problematic and should be avoided for the following reasons:

- To replace MyDependency with a different implementation, the IndexModel class must be modified.
- If MyDependency has dependencies, they must also be configured by the IndexModel class. In a large project with multiple classes depending on MyDependency, the configuration code becomes scattered across the app.
- This implementation is difficult to unit test.

##### Dependency injection addresses these problems through:

The use of an interface or base class to abstract the dependency implementation.
Registration of the dependency in a service container. ASP.NET Core provides a built-in service container, IServiceProvider. Services are typically registered in the app's Program.cs file.
Injection of the service into the constructor of the class where it's used. The framework takes on the responsibility of creating an instance of the dependency and disposing of it when it's no longer needed.

##### Entity Framework contexts

By default, Entity Framework contexts are added to the service container using the scoped lifetime because web app database operations are normally scoped to the client request. To use a different lifetime, specify the lifetime by using an AddDbContext overload. Services of a given lifetime shouldn't use a database context with a lifetime that's shorter than the service's lifetime.

## The Repository pattern

The Repository pattern is a Domain-Driven Design pattern intended to keep persistence concerns outside of the system's domain model. One or more persistence abstractions - interfaces - are defined in the domain model, and these abstractions have implementations in the form of persistence-specific adapters defined elsewhere in the application.

Repository implementations are classes that encapsulate the logic required to access data sources. They centralize common data access functionality, providing better maintainability and decoupling the infrastructure or technology used to access databases from the domain model. If you use an Object-Relational Mapper (ORM) like Entity Framework, the code that must be implemented is simplified, thanks to LINQ and strong typing. This lets you focus on the data persistence logic rather than on data access plumbing.

## SOLID code Principles:

The SOLID principles are a set of guidelines for writing good software. They were introduced by Robert "Uncle Bob" Martin to help developers create code that is easy to understand, flexible, and less prone to bugs. Let's break down each principle:

1. Single Responsibility Principle (SRP).
2. Open/Closed Principle (OCP).
3. Liskov Substitution Principle (LSP).
4. Interface Segregation Principle (ISP).
5. Dependency Inversion Principle (DIP).

Following these principles helps make the code easier to test, understand, and maintain.
