

2024-07-31 | 07:50

##### Tags: [[Networking]]

---

Cookie is a small, key-value format, piece of data a server sends to user's web browser. The browser may store, create new or modify existing ones and send them back to the same server with the later requests.

Cookies are mainly used for three purposes: 
1. **Session management** - user sign-in status, shopping cart contents, game scores, or any other user session-related details that the server needs to remember
2. **Personalization** - user preferences such as UI theme, display language
3. **Tracking** - Recording and analyzing user behavior


### Cookies management
After sending request, a server can send one or more cookies with `Set-Cookie` header with the response. 

Example response that instructs the browser to store received cookies:

``` http
```
HTTP/2.0 200 OK
Content-Type: text/html
Set-Cookie: yummy_cookie=choco
Set-Cookie: tasty_cookie=strawberry

[page content]
```
```


Usually, with each new request the browser sends the cookies back to the server:

```http
```
GET /sample_page.html HTTP/2.0
Host: www.example.org
Cookie: yummy_cookie=choco; tasty_cookie=strawberry
```
```

### Cookie removal: defining the lifetime of a cookie
We can specify an expiration date or time period after which the cookie should be deleted. The cookies can be either:

##### 1. Permanent:
Deleted after specified date in the `Expires` attribute:

`Set-Cookie: id=a3fWa; Expires=Thu, 31 Oct 2021 07:28:00 GMT;`

or after the period specified in the `Max-Age` attribute: 

`Set-Cookie: id=a3fWa; Max-Age=2592000`

##### 2. Session
Cookies without `Expires` or `Max-Age`. Deleted when the current session ends. Session end is defined by the browser, some browsers use session restoring when restarting, which can cause cookies to last indefinitely.

