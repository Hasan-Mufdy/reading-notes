# Data Transfer Objects

Right now, our web API exposes the database entities to the client. The client receives data that maps directly to your database tables. However, that's not always a good idea. Sometimes you want to change the shape of the data that you send to client. For example, you might want to:

- Remove circular references (see previous section).
- Hide particular properties that clients are not supposed to view.
- Omit some properties in order to reduce payload size.
- Flatten object graphs that contain nested objects, to make them more convenient for clients.
- Avoid "over-posting" vulnerabilities. (See Model Validation for a discussion of over-posting.)
- Decouple your service layer from your database layer.

To accomplish this, you can define a data transfer object (DTO). A DTO is an object that defines how the data will be sent over the network. Let's see how that works with the Book entity. In the Models folder, add two DTO classes:

```
namespace BookService.Models
{
    public class BookDto
    {
        public int Id { get; set; }
        public string Title { get; set; }
        public string AuthorName { get; set; }
    }
}

namespace BookService.Models
{
    public class BookDetailDto
    {
        public int Id { get; set; }
        public string Title { get; set; }
        public int Year { get; set; }
        public decimal Price { get; set; }
        public string AuthorName { get; set; }
        public string Genre { get; set; }
    }
}
```

- A Data Transfer Object (commonly known as a DTO) is usually an instance of a POCO (plain old CLR object) class used as a container to encapsulate data and pass it from one layer of the application to another. You would typically find DTOs being used in the service layer to return data back to the presentation layer. The biggest advantage of using DTOs is decoupling clients from your internal data structures.

#### Why use Data Transfer Objects (DTOs)?

When designing and developing an application, if you’re using models to pass data between the layers and sending data back to the presentation layer, then you’re exposing the internal data structures of your application. That’s a major design flaw in your application.

By decoupling your layers DTOs make life easier when you’re implementing APIs, MVC applications, and also messaging patterns such as Message Broker. A DTO is a great choice when you would like to pass a lightweight object across the wire — especially when you’re passing your object via a medium that is bandwidth-constrained.

