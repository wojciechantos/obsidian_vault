
2024-07-30 | 16:51

##### Tags: [[Networking]] [[Network Protocols]] [[URL]] [[URI]]

---

## URL (Uniform Resource Locator)

URL is a **string of characters that specifies the location of a resource on the internet**. They are used to access web pages and other resources on the World Wide Web, such as images or videos. URLs are a specific type of URI and are used to locate resources on the internet.

URL has a specific syntax, which usually includes the following parts:
- protocol
- domain
- path

A full URL example with its parts described:

![[mdn-url-all.png]]


1. **Scheme** - indicates the protocol like HTTP or HTTPS
2. **Authority**: 
	- *Username & Password* - which are access credentials They optionally prefix the domain or subdomain (if present), they are separated with colon, and end with the "@" sign.
	- *Domain name*: separated with the "://" character pattern, contains subdomain (eventually), domain and TLD (Top Level Domain)
	- *Port*: numeric value that indicates the "technical gate" used to access the resources, omitted when standard ports are used (80 for HTTP, 443 for HTTPS), otherwise mandatory.
3. **Path to resource** - it used to be a physical file location, but now it is an abstraction handled by the web servers. They generally navigate to different sections of the website and can be nested.
4. **Parameters** - they start with "?" and they are extra-provided to the server. Always in a key=value pairs separated with the "&" symbol. The web server can use them to do some extra stuff before returning the resource, but it is specific to a certain server and can be known by asking the owner if and how they are handled.
5. **Anchor** - it represents a sort of "bookmark" inside the resource, giving the browser the directions to show the content located at that "bookmarked" spot. On an HTML document, for example, the browser will scroll to the point where the anchor is defined; on a video or audio document, the browser will try to go to the time the anchor represents. It is worth noting that the part after the **#**, also known as the fragment identifier, is never sent to the server with the request.

### Usage

Besides that the URLs can be typed in the browser's address bar to get to the resource it is also widely used in the HTML elements, like:
- `<a>` - to create link to other documents 
- `<link>` or `<script>` - to link a document with its related resources
- `<img>`, `<video>` or `<audio>` - to display a media files
- `<iframe>` - to display other HTML documents within the current one
