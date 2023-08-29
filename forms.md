# Forms In ASP.NET MVC

### Setup:

1. Create a New ASP.NET MVC Project MvcForms.

2. Create a model class NewModel.cs.(Right-click on Model Add Class.)

3. Open StudentModel.cs and add the following code in it:

```
{
    public class NewModel
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public bool Addon { get; set; }
    }
}
```

#### weakly typed form:

it is the easiest and quickest way to create forms in MVC, by adding the required inputs in Index.cshtml, and adding an action method for the form in HomeController.cs

##### Advantage for the weakly typed form:

1. It is easy to create a form using Weakly Typed mechanism
2. Mostly used when you need to create a form with one or two input items.

##### Disadvantage for the weakly typed form:

1. Because, it is not strongly typed so IntelliSense doesn't help you.
2. Have higher chance of getting exception and runtime error messages.
3. Very difficult to manage when forms have multiple input items and controls.
4. It is very clumsy when you need to add or remove some input items.
