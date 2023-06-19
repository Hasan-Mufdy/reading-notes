## C# classes

Class is a reference type. At run time, when a variable of a reference type is declared, the variable contains the value null until you explicitly create an instance of the class by using the new operator.
Objects can be created by using the new keyword.

## constructors
A constructor is a special method that is used to initialize objects. And its name is the same as the name of its type.

## Constructor syntax:
```
public class Person
{
   private string last;
   private string first;

   public Person(string lastName, string firstName)
   {
      last = lastName;
      first = firstName;
   }

   // Remaining implementation of Person class.
}

```


## Properties in C#:

A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field. They can be used as if they're public data members. They are very useful, as every object in real life has properties.

## Stacks and Heaps

There are two places the .NET framework stores items in memory as a code executes.
Stack and heap reside in the operating memory on our machine and contain the pieces of information we need to make it all happen.
The Stack is responsible for keeping track of what's executing in our code.  The Heap is responsible for keeping track of our objects.

## garbage collection

In the common language runtime (CLR), the garbage collector (GC) serves as an automatic memory manager. The garbage collector manages the allocation and release of memory for an application. Therefore, developers working with managed code don't have to write code to perform memory management tasks. Automatic memory management can eliminate common problems such as forgetting to free an object and causing a memory leak or attempting to access freed memory for an object that's already been freed.

Garbage collector helps developers to be more efficient, as they don’t need to manually release the memory.