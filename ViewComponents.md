# View Components

## View components are similar to partial views, but they're much more powerful. View components don't use model binding, they depend on the data passed when calling the view component. This article was written using controllers and views, but view components work with Razor Pages.

- A view component:

Renders a chunk rather than a whole response.
Includes the same separation-of-concerns and testability benefits found between a controller and view.
Can have parameters and business logic.
Is typically invoked from a layout page.
View components are intended anywhere reusable rendering logic that's too complex for a partial view, such as:

Dynamic navigation menus
Tag cloud, where it queries the database
Sign in panel
Shopping cart
Recently published articles
Sidebar content on a blog
A sign in panel that would be rendered on every page and show either the links to sign out or sign in, depending on the sign in state of the user
A view component consists of two parts:

The class, typically derived from ViewComponent
The result it returns, typically a view.

## to create a view component

A view component class can be created by any of the following:

Deriving from ViewComponent
Decorating a class with the [ViewComponent] attribute, or deriving from a class with the [ViewComponent] attribute
Creating a class where the name ends with the suffix ViewComponent
Like controllers, view components must be public, non-nested, and non-abstract classes. The view component name is the class name with the ViewComponent suffix removed. It can also be explicitly specified using the Name property.

A view component class:

Supports constructor dependency injection
Doesn't take part in the controller lifecycle, therefore filters can't be used in a view component

## View component methods

A view component defines its logic in an:

- InvokeAsync method that returns Task<IViewComponentResult>.
- Invoke synchronous method that returns an IViewComponentResult.

## View component methods

A view component defines its logic in an:

InvokeAsync method that returns Task<IViewComponentResult>.
Invoke synchronous method that returns an IViewComponentResult.

## View search path

The runtime searches for the view in the following paths:

- /Views/{Controller Name}/Components/{View Component Name}/{View Name}
- /Views/Shared/Components/{View Component Name}/{View Name}
- /Pages/Shared/Components/{View Component Name}/{View Name}
- /Areas/{Area Name}/Views/Shared/Components/{View Component Name}/{View Name}
