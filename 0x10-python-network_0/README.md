## What a URL is:
A URL (Uniform Resource Locator) is a string of characters used to address and locate resources on the internet. It specifies the protocol to be used (e.g., HTTP, HTTPS), the domain or IP address of the server, the path to the resource, and optional components such as query parameters.

## What HTTP is:
HTTP (Hypertext Transfer Protocol) is an application-level protocol used for communication between web browsers and web servers. It defines how requests from clients (such as web browsers) are formatted and sent to servers, and how servers respond with the requested resources.

## How to read a URL:
To read a URL, you can break it down into its components:
- Scheme: The protocol used, such as HTTP or HTTPS.
- Domain: The main address of the website.
- Subdomain: An optional prefix to the domain, indicating a specific section or subcategory of the website.
- Port: An optional number that specifies the network port to be used for the connection.
- Path: The specific location of the resource within the website's directory structure.
- Query String: Optional parameters passed to the server for additional information or customization.

## The scheme for an HTTP URL:
The scheme for an HTTP URL is typically "http://" for unsecured connections or "https://" for secured connections using SSL/TLS encryption.

## What a domain name is:
A domain name is a human-readable label that represents an IP address or a collection of resources on the internet. It is used to identify websites and other online services. For example, in "example.com," "example" is the domain name.

## What a sub-domain is:
A subdomain is a prefix to the main domain name, indicating a specific section or subcategory of a website. For example, in "subdomain.example.com," "subdomain" is the subdomain.

## How to define a port number in a URL:
To define a port number in a URL, append a colon (:) followed by the desired port number after the domain name or IP address. For example, "http://example.com:8080" specifies port 8080 for the HTTP connection.

## What a query string is:
A query string is a part of a URL that follows a question mark (?) and contains parameters in the form of key-value pairs. It is used to pass data to the server for processing or customization. For example, in "http://example.com/search?q=keyword," the query string is "?q=keyword," where "q" is the parameter key and "keyword" is the parameter value.

## What an HTTP request is:
An HTTP request is a message sent by a client (such as a web browser) to a server, requesting a specific resource. It includes the HTTP method (GET, POST, etc.), the URL of the resource, headers containing additional information, and optionally, a message body containing data to be sent to the server.

## What an HTTP response is:
An HTTP response is the message sent by a server in response to an HTTP request. It contains the requested resource, along with response headers providing additional information about the response. It also includes an HTTP status code indicating the outcome of the request (e.g., 200 OK, 404 Not Found).

## What HTTP headers are:
HTTP headers are additional information sent in both requests and responses. They provide metadata about the message, such as the content type, caching instructions, authentication credentials, and more. Headers help the client and server communicate and handle the request and response correctly.

## What the HTTP message body is:
The HTTP message body is the optional part of an HTTP request or response that follows the headers. It contains data sent by the client (in a request) or data returned by the server (in a response). The format and content of the message body depend on the specific application or resource being accessed.

## What an HTTP request method is:
An HTTP request method specifies the action to be performed on a resource. Common HTTP request methods include GET (retrieve a resource), POST (submit data to be processed), PUT (update a resource), DELETE (remove a resource), and more. The method is specified in the request's HTTP line.

## What an HTTP response status code is:
An HTTP response status code is a three-digit number included in an HTTP response. It indicates the outcome of the request and provides information about whether it was successful or encountered an error. Examples include 200 (OK), 404 (Not Found), and 500 (Internal Server Error).

## What an HTTP Cookie is:
An HTTP Cookie is a small piece of data stored on the client's computer by a web server. Cookies are used to maintain state and track user interactions with a website. They can store information such as user preferences, session identifiers, and shopping cart contents.

## How to make a request with cURL:
cURL is a command-line tool and library for making HTTP requests. Here's an example of how to make a GET request using cURL in the command line:

```
curl http://example.com
```

This command sends a GET request to "http://example.com" and displays the response in the command line.

You can also include additional options with cURL to customize the request, such as adding headers, sending data with POST requests, or handling cookies.

## What happens when you type google.com in your browser (Application level):
When you type "google.com" in your browser and press Enter, several steps occur at the application level:

1. The browser checks its cache for a previously accessed IP address for "google.com" to avoid unnecessary DNS lookup.

2. If the IP address is not found in the cache, the browser sends a DNS (Domain Name System) request to a DNS server to resolve the domain name "google.com" into an IP address.

3. The DNS server responds with the IP address associated with "google.com" (e.g., 216.58.204.46).

4. The browser establishes a TCP (Transmission Control Protocol) connection with the web server at the retrieved IP address, typically on port 80 for HTTP or port 443 for HTTPS.

5. The browser sends an HTTP GET request to the web server, specifying the path ("/") and other headers.

6. The web server receives the request, processes it, and generates an HTTP response.

7. The web server sends the HTTP response back to the browser, which includes the requested webpage content along with response headers.

8. The browser receives the response, interprets the HTML content, and renders the webpage for display.

9. The browser may send additional requests for external resources (e.g., images, stylesheets) referenced in the HTML.

10. The browser renders the complete webpage, and you can interact with it, perform searches, or navigate to other pages within the website.

Please note that the above steps are simplified and may vary depending on factors such as browser optimizations, caching mechanisms, and the specific website's configuration.
