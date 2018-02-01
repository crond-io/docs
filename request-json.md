# Task

Every task scheduled on [crond.io](https://www.crond.io) is a standard HTTP request. The request to be made is represented in the form of a JSON with the following configurable fields:

* **url **_**\(string, required\)**_**: **The HTTP URL of the request.
* **method **_**\(string, optional\)**_**: ** The HTTP method to be used. Defaults to GET.
* **params **_**\(map, optional\)**_**: **Additional parameters for the request to be sent as query string.
* **body **_**\(string, optional\)**_**: **A string that will be sent as the body of the request.
* **json **_**\(any, optional\)**_**: **JSON value that needs to be sent as the body of the request.
* **cookies **_**\(map, optional\)**_**: **Cookies to be sent along with the request.
* **auth **_**\(map, optional\)**_**: **HTTP Basic Auth parameters to be used as a map containing a 'user' key and 'pass' key.
* **timeout **_**\(number, optional\)**_**: **How many seconds to wait for the server to send data before giving up.
* **allow\_redirects **_**\(boolean, optional\)**_**: **Enable/disable automatic redirection. Defaults to true.



