# Circumvent HTTPS mixed content warnings

See also:

* [circumvent-cors.md](circumvent-cors.md)

## Motivation

### Static websites

* You may want to operate a web service as a hobby where HTTPS is already given on the frontend (or via CDN).
* Almost all free static web hosting solutions provide HTTPS
* From a root of trust perspective, it is crucial to load the main HTML with integrity (HTTPS)
* Other resources can be loaded with SRI or encrypted and validated dynamically from JavaScript if needed
* [../hu/free-static-web-hosting.md](../hu/free-static-web-hosting.md)

### Dynamic websites

* Installing and maintaining a HTTPS site is just a little bit more difficult than a HTTP one.
* Less free PaaS providers provide HTTPS access than just HTTP:
* [../hu/free-paas-dynamic-web-hosting.md](../hu/free-paas-dynamic-web-hosting.md)

### Problem

The browser will refuse XHR requests (among others) from your HTTPS frontend to your small HTTP backend:

* https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content

A `<form>` post to an HTTP target still succeeds on most browsers, but gives a warning during text input or before submission:

* https://www.bleepingcomputer.com/news/security/google-chrome-will-warn-users-when-submitting-insecure-forms/

## Workarounds

### Mixed passive content

* If your use case allows for mixed passive content (won't work on Chrome 81+)
* Generate an `<img>` element in JavaScript
* Pass any form data to submit as URI parameters
* The URI should be at most 2KB and must be at most 8KB
* Encode the response as an uncompressed `.png` on the backend
* Decode the returned resource in JavaScript

### CSP report

* Define a content security policy that will report to our HTTP backend
* You might want to target only a subset of entity types (`style-src`?)
* Unfortunately, this must be an HTTP header, because `report-uri` is not supported in `<meta>`

```
Content-Security-Policy-Report-Only: default-src 'none'; report-uri http://example.com/csp
```

* Create a resource reference in JavaScript (e.g., `<img>`)
* Target a non-existing path under the same origin
* Encode the request, form data and a nonce in the URI parameters
* On the backend, decode `blocked-uri`, generate a response and upload it to the static HTTPS host via FTP
* Poll for the response on the HTTPS host in JavaScript
* Start with a slight delay, then use exponential back-off and an overall timeout
* https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP

### JavaScript callback parameters

* Encode HTTPS frontend state into a callback URI (or `Referer`)
* Navigate to the HTTP backend URI by passing the callback in the anchor
* Depending on demands for routing or extra round trips, the response could be inlined into the HTTP result HTML, pregenerated statically or assembled via JavaScript
* The HTTP result HTML ends with a snippet that would navigate back to the HTTPS callback URI with the results appended

### Server assisted callback parameters

* For `<noscript>` usage
* Hyperlinks to the HTTP backend could be pregenerated on the page with the HTTPS callback URI substituted everywhere
* The user would click a link to navigate to the backend and/or optionally by a periodic `meta refresh`
* The backend page would contain the response data generated inline
* Returning by invocation of the callback could happen with:

```
<meta http-equiv="refresh" content="0; url=https://example.com/?i=callbackInput&o=responseData">
```

## Past workarounds

### HTTP redirect

* The resource or form action targets an HTTPS URI
* Immediately redirect via 302/307/308 to the HTTP backend URI
* Won't make a difference on recent browsers any more
