# MVC (Model view controller)

MVC is a design pattern used to decouple user-interface (view), data (model), and application logic (controller). This pattern helps to achieve separation of concerns.

Some things this MVC tutorial has that the Razor Pages tutorial doesn't:
Implement inheritance in the data model
Perform raw SQL queries
Use dynamic LINQ to simplify code

Some things the Razor Pages tutorial has that this one doesn't:

Use Select method to load related data
Best practices for EF.

#### Database engines

The Visual Studio instructions use SQL Server LocalDB, a version of SQL Server Express that runs only on Windows.

#### To create a web app:

- Start Visual Studio and select Create a new project.
- In the Create a new project dialog, select ASP.NET Core Web Application > Next.
- In the Configure your new project dialog, enter ContosoUniversity for Project name. It's important to use this exact name including capitalization, so each namespace matches when code is copied.
- Select Create.
- In the Create a new ASP.NET Core web application dialog, select:
  .NET Core and ASP.NET Core 5.0 in the dropdowns.
  ASP.NET Core Web App (Model-View-Controller).

#### EF Core NuGet packages

EF Core supports different database systems through the use of "database providers". Each system has its own database provider, which is shipped as NuGet package. Applications should install one or more of these provider packages

#### database context

The main class that coordinates EF functionality for a given data model is the DbContext database context class. This class is created by deriving from the Microsoft.EntityFrameworkCore.DbContext class. The DbContext derived class specifies which entities are included in the data model. Some EF behaviors can be customized. In this project, the class is named SchoolContext.

#### SQL Server Express LocalDB

The connection string specifies SQL Server LocalDB. LocalDB is a lightweight version of the SQL Server Express Database Engine and is intended for app development, not production use. LocalDB starts on demand and runs in user mode, so there's no complex configuration. By default, LocalDB creates .mdf DB files in the C:/Users/<user> directory.

#### To create controller and views

Use the scaffolding engine in Visual Studio to add an MVC controller and views that will use EF to query and save data.
The automatic creation of CRUD action methods and views is known as scaffolding.

- In Solution Explorer, right-click the Controllers folder and select Add > New Scaffolded Item.
- In the Add Scaffold dialog box:
  Select MVC controller with views, using Entity Framework.
  Click Add. The Add MVC Controller with views, using Entity
  In Model class, select Student.
  Click Add.

#### to view the database:

When the app is started, the DbInitializer.Initialize method calls EnsureCreated. EF saw that there was no database:

- So it created a database.
- The Initialize method code populated the database with data.

#### Asynchronous code

Asynchronous programming is the default mode for ASP.NET Core and EF Core.

A web server has a limited number of threads available, and in high load situations all of the available threads might be in use. When that happens, the server can't process new requests until the threads are freed up. With synchronous code, many threads may be tied up while they aren't actually doing any work because they're waiting for I/O to complete. With asynchronous code, when a process is waiting for I/O to complete, its thread is freed up for the server to use for processing other requests. As a result, asynchronous code enables server resources to be used more efficiently, and the server is enabled to handle more traffic without delays.

Asynchronous code does introduce a small amount of overhead at run time, but for low traffic situations the performance hit is negligible, while for high traffic situations, the potential performance improvement is substantial.
