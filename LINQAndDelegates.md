# LINQ & Delegates

## Language Integrated Query (LINQ)

Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language. Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support. Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on. With LINQ, a query is a first-class language construct, just like classes, methods, events. You write queries against strongly typed collections of objects by using language keywords and familiar operators. The LINQ family of technologies provides a consistent query experience for objects (LINQ to Objects), relational databases (LINQ to SQL), and XML (LINQ to XML).

The following example shows the complete query operation. The complete operation includes creating a data source, defining the query expression, and executing the query in a foreach statement.

```
// Specify the data source.
int[] scores = { 97, 92, 81, 60 };

// Define the query expression.
IEnumerable<int> scoreQuery =
    from score in scores
    where score > 80
    select score;

// Execute the query.
foreach (int i in scoreQuery)
{
    Console.Write(i + " ");
}

// Output: 97 92 81
```

### LINQ Queries

A query is an expression that retrieves data from a data source. Queries are usually expressed in a specialized query language. Different languages have been developed over time for the various types of data sources, for example SQL for relational databases and XQuery for XML. Therefore, developers have had to learn a new query language for each type of data source or data format that they must support. LINQ simplifies this situation by offering a consistent model for working with data across various kinds of data sources and formats.

- Parts of a Query Operation:

1. Obtain the data source.
2. Create the query.
3. Execute the query.

### LINQ Query Operations

- to obtain a Data Source:
  In a LINQ query, the first step is to specify the data source. In C# as in most programming languages a variable must be declared before it can be used. In a LINQ query, the from clause comes first in order to introduce the data source (customers) and the range variable (cust).

- some query operation examples:

1. Filtering
2. Ordering
3. Grouping
4. Joining
5. Selecting

filtering operation is probably the most common query operation, The filter causes the query to return only the elements where the expression is true.

- example:

```
var queryLondonCustomers = from cust in customers
                           where cust.City == "London"
                           select cust;
```
