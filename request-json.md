# Task

Every task scheduled on [crond.io](https://www.crond.io) is a standard HTTP request. The request to be made is represented in the form of a JSON with the following configurable fields:

* **url \(string, required\): **The HTTP URL of the request.
* **method \(string, optional\): ** The HTTP method to be used. Defaults to GET.
* **params \(map, optional\): **Additional parameters for the request to be sent as query string.
* **body \(string, optional\): **A string that will be sent as the body of the request.
* **json \(any, optional\): **JSON value that needs to be sent as the body of the request.
* **cookies \(map, optional\): **Cookies to be sent along with the request.
* **auth \(map, optional\): **HTTP Basic Auth parameters to be used as a map containing a 'user' key and 'pass' key.
* **timeout \(number, optional\): **How many seconds to wait for the server to send data before giving up.
* **allow\_redirects \(boolean, optional\): **Enable/disable automatic redirection. Defaults to true.



