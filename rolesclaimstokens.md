# Roles, Claims and JWT Tokens

## Claims-based authorization in ASP.NET Core

When an identity is created it may be assigned one or more claims issued by a trusted party. A claim is a name value pair that represents what the subject is, not what the subject can do. For example, you may have a driver's license, issued by a local driving license authority. Your driver's license has your date of birth on it. In this case the claim name would be DateOfBirth, the claim value would be your date of birth, for example 8th June 1970 and the issuer would be the driving license authority. Claims based authorization, at its simplest, checks the value of a claim and allows access to a resource based upon that value. For example if you want access to a night club the authorization process might be:

The door security officer would evaluate the value of your date of birth claim and whether they trust the issuer (the driving license authority) before granting you access.

An identity can contain multiple claims with multiple values and can contain multiple claims of the same type.

#### Claim based authorization checks:

- Are declarative.
- Are applied to Razor Pages, controllers, or actions within a controller.
- Can not be applied at the Razor Page handler level, they must be applied to the Page.

#### The difference between Authentication and Authorisation

First of all, we should clarify the difference between these two dependent facets of security. The simple answer is that Authentication is the process of determining who you are, while Authorisation revolves around what you are allowed to do, i.e. permissions. Obviously before you can determine what a user is allowed to do, you need to know who they are, so when authorisation is required, you must also first authenticate the user in some way.

#### Authentication in ASP.NET Core

The fundamental properties associated with identity have not really changed in ASP.NET Core - although they are different, they should be familiar to ASP.NET developers in general. For example, in ASP.NET 4.x, there is a property called User on HttpContext, which is of type IPrincipal, which represents the current user for a request. In ASP.NET Core there is a similar property named User, the difference being that this property is of type ClaimsPrincipal, which implements IPrincipal.

#### What is JWT?

JSON Web Token (JWT) is a means of representing claims to be transferred between two parties. The claims in a JWT are encoded as a JSON object that is digitally signed using JSON Web Signature (JWS) and/or encrypted using JSON Web Encryption (JWE).

#### SIGNATURE:

It is calculated by base64url encoding of header and payload and concatenating them with a period as a separator. Then encrypt it with HMAC-SHA256 along with the secret key and the result of the first step.

#### Producer and Consumer concept of API’s:

- There are two parties involved, one party who gives a service, and the other party who uses the service.

1. Producer is the one who gives a service. It will be the provider(Server) of the API(s) which are JWT protected.

2. Consumer is the one who uses it. It will be the customer(Server/Mobile App/ Web App/ Client) who will be providing the valid JWT token to consume the API(s) being provided by the Producer.
