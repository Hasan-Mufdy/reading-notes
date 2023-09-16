# Razor Pages

With ASP.NET Core 2 we get another way of building web applications. It’s one of those new things that is actually forgotten old thing and it is called Razor Pages. Are we going back to WebMatrix days? This blog post is short introduction to Razor Pages in ASP.NET Core 2.

One of new features of ASP.NET Core 2.0 is support for Razor Pages. Yes, those same pages that came times ago with WebMatrix. Today Razor Pages is subset of MVC on ASP.NET Core. Yes, support for Razor Pages comes with ASP.NET Core MVC meaning that Razor Pages application is technically MVC application. Also Razor Pages have same features as MVC views.

Razor Pages is a newer, simplified web application programming model. It removes much of the ceremony of ASP.NET MVC by adopting a file-based routing approach. Each Razor Pages file found under the Pages directory equates to an endpoint.

## To Create a Razor Page:

Razor Pages is enabled in Program.cs:

```
builder.Services.AddRazorPages();
```

```
app.MapRazorPages();
```

#### and a basic razor page will be something like this:

```
@page

<h1>Hello, world!</h1>
<h2>The time on the server is @DateTime.Now</h2>
```

### basic form example:

- in program.cs file

```
builder.Services.AddDbContext<CustomerDbContext>(options =>
    options.UseInMemoryDatabase("name"));
```

- The data model:

```
using System.ComponentModel.DataAnnotations;

namespace RazorPagesContacts.Models
{
    public class Customer
    {
        public int Id { get; set; }

        [Required, StringLength(10)]
        public string? Name { get; set; }
    }
}
```

- The db context:

```
using Microsoft.EntityFrameworkCore;

namespace RazorPagesContacts.Data
{
    public class CustomerDbContext : DbContext
    {
        public CustomerDbContext (DbContextOptions<CustomerDbContext> options)
            : base(options)
        {
        }

        public DbSet<RazorPagesContacts.Models.Customer> Customer => Set<RazorPagesContacts.Models.Customer>();
    }
}
```

- The Pages/Customers/Create.cshtml view file:

```
@page
@model RazorPagesContacts.Pages.Customers.CreateModel
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<p>Enter a customer name:</p>

<form method="post">
    Name:
    <input asp-for="Customer!.Name" />
    <input type="submit" />
</form>
```

- The Pages/Customers/Create.cshtml.cs page model:

```
public class CreateModel : PageModel
{
    private readonly Data.CustomerDbContext _context;

    public CreateModel(Data.CustomerDbContext context)
    {
        _context = context;
    }

    public IActionResult OnGet()
    {
        return Page();
    }

    [BindProperty]
    public Customer? Customer { get; set; }

    public async Task<IActionResult> OnPostAsync()
    {
        if (!ModelState.IsValid)
        {
            return Page();
        }

        if (Customer != null) _context.Customer.Add(Customer);
        await _context.SaveChangesAsync();

        return RedirectToPage("./Index");
    }
}
```

### Razor Pages benefits:

MVC developers want probably ask why we need one more way to build web sites on ASP.NET Core? Isn’t MVC enough? From information I have found from public space I found the following reasoning:

- It’s easier to get to web development for beginners as Razor pages are more lightweight than MVC. Besides beginners there are people who are coming from other scripting languages be it old ASP or PHP or something else.
- Razor Pages fit well to smaller scenarios where building controllers and models as separate classes is overkill.

### Application structure

Application structure is similar to MVC but there are no folders for controllers and views. The folder called Pages contains all Razor views that in this context are called “pages”. These pages are like regular MVC views but they also contain code that for MVC is held in controller classes.
Program and Startup classes are exactly the same as for MVC applications. Not just by name but also by code.
