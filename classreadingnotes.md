# Classes Reading Notes

## Debugging - try/catch - exception handling.

### Debugging:
The code we write as software developers doesn't always run as we expected, it is very normal to have some errors, compilation, or runtime. This can be frustrating, especially for new developers. Because of that, debugging can be very useful to test an application step by step and find bugs.
So debugging will make the process of finding bugs way faster and easier, especially when using the right tools.

### Try/Catch:
Using try/catch is sometimes crucial while writing code, it basically tells the compiler that we expect to have an error in this block, so if we had an error the application prints it and continue executing other things. Without using it, if we had an error the application would just have a compilation error, and it will not execute anything.
A real-life example of try/catch:
Imagine if you have an equation to calculate your budget for the month, if any of the inputs was missing or wrong, we can just skip it, after addressing it.
try/catch can sometimes affect the performance of the application, it can also make debugging a little harder and more complicated.
In my opinion try/catch advantages absolutely outweighs its disadvantages.

### Exception handling:
A real-life example of exception handling:
Imagine if you are fixing your car by yourself, and you are watching an online tutorial, you will most likely to encounter some problems, like for example if something broke. In my previous example about budget calculating equation, if we for example had to divide a number by zero, this will be an exception, we can do the alternative and continue.
