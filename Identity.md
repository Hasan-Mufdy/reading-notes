# Identity

### ASP.NET Core Identity:

- Is an API that supports user interface (UI) login functionality.
- Manages users, passwords, profile data, roles, claims, tokens, email confirmation, and more.

Users can create an account with the login information stored in Identity or they can use an external login provider.

Identity is typically configured using a SQL Server database to store user names, passwords, and profile data. Alternatively, another persistent store can be used, for example, Azure Table Storage.

ASP.NET Core Identity isn't related to the Microsoft identity platform. Microsoft identity platform is:

- An evolution of the Azure Active Directory (Azure AD) developer platform.
- An alternative identity solution for authentication and authorization in ASP.NET Core apps.

ASP.NET Core Identity adds user interface (UI) login functionality to ASP.NET Core web apps. To secure web APIs and SPAs, use one of the following:

- Azure Active Directory
- Azure Active Directory B2C (Azure AD B2C)
- Duende Identity Server

#### Duende Identity Server:

Duende Identity Server is an OpenID Connect and OAuth 2.0 framework for ASP.NET Core.

#### features:

- Authentication as a Service (AaaS)
- Single sign-on/off (SSO) over multiple application types
- Access control for APIs
- Federation Gateway

#### Identity Components

The primary package for Identity is Microsoft.AspNetCore.Identity. This package contains the core set of interfaces for ASP.NET Core Identity, and is included by 
```Microsoft.AspNetCore.Identity.EntityFrameworkCore.```
