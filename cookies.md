# HTTP cookies

An HTTP cookie (web cookie, browser cookie) is a small piece of data that a server sends to a user's web browser. The browser may store the cookie and send it back to the same server with later requests. Typically, an HTTP cookie is used to tell if two requests come from the same browser—keeping a user logged in, for example. It remembers stateful information for the stateless HTTP protocol.

Cookies are mainly used for three purposes:

- Session management
  Logins, shopping carts, game scores, or anything else the server should remember

- Personalization
  User preferences, themes, and other settings

- Tracking
  Recording and analyzing user behavior

Cookies were once used for general client-side storage. While this made sense when they were the only way to store data on the client, modern storage APIs are now recommended. Cookies are sent with every request, so they can worsen performance (especially for mobile data connections). Modern APIs for client storage are the Web Storage API (localStorage and sessionStorage) and IndexedDB.

#### Creating cookies

After receiving an HTTP request, a server can send one or more Set-Cookie headers with the response. The browser usually stores the cookie and sends it with requests made to the same server inside a Cookie HTTP header. You can specify an expiration date or time period after which the cookie shouldn't be sent. You can also set additional restrictions to a specific domain and path to limit where the cookie is sent.

#### The lifetime of a cookie can be defined in two ways:

- Session cookies are deleted when the current session ends. The browser defines when the "current session" ends, and some browsers use session restoring when restarting. This can cause session cookies to last indefinitely.
- Permanent cookies are deleted at a date specified by the Expires attribute, or after a period of time specified by the Max-Age attribute.

#### HTTP-Only cookies

Microsoft introduced a new option for cookies in Internet explorer 6 SP1: HTTP-only cookies. The idea behind HTTP-only cookies is to instruct a browser that a cookie should never be accessible via JavaScript through the document.cookie property. This feature was designed as a security measure to help prevent cross-site scripting (XSS) attacks perpetrated by stealing cookies via JavaScript. Today, Firefox 2.0.0.5+, Opera 9.5+, and Chrome also support HTTP-only cookies. Safari as of 3.2 still does not.

To create an HTTP-only cookie, just add an HttpOnly flag to your cookie:

```
Set-Cookie: name=Nicholas; HttpOnly
```

#### main usage of cookies

Thanks to cookies, you can save information about the visitor and retrieve it again on subsequent requests. This is a very important technique, used in a wide range of situations, like keeping the user logged in, tracking their use of your website and much more.
