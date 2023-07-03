# Collections & Enums

## Collections:

Collections provide a more flexible way to work with groups of objects.
Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change. For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.

(A collection is a class, so you must declare an instance of the class before you can add elements to that collection.)

#### simple collection example:

```
// Create a list of strings.
var salmons = new List<string>();
salmons.Add("chinook");
salmons.Add("coho");
salmons.Add("pink");
salmons.Add("sockeye");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

#### collections examples:

Many common collections are provided by .NET. Each type of collection is designed for a specific purpose.

- Some of the common collection classes:

1. System.Collections.Generic classes
2. System.Collections.Concurrent classes
3. System.Collections classes


## Enumeration

An enumeration type (or enum type) is a value type defined by a set of named constants of the underlying integral numeric type. To define an enumeration type, we use the enum keyword and we can specify the names of enum members:
```
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```
- By default, the associated constant values of enum members are of type int.

#### The System.Enum type and enum constraint:

The System.Enum type is the abstract base class of all enumeration types. It provides a number of methods to get information about an enumeration type and its values.

#### Conversions:

For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type. 