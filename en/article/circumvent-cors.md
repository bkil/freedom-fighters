# Circumvent CORS

## Motivation

* If you have limited control over your servers
* The CORS headers may be filtered or against the terms of service
* You can't handle such request specially via .htaccess or using a dynamic backend
* Perhaps the hoster is not experienced enough to set it up
* The service might be optimized for novices, like a blog engine or a purpose-built website builder
* You may be developing an application that shall require the absolute minimum amount of setup instructions and maximize deployment compatibility

See also:

* [circumvent-https-mixed-content.md](circumvent-https-mixed-content.md)
* [../../hu/service/game-backend.md](../../hu/service/game-backend.md)

## Cookie protection

* Shared PaaS web hosting providers sometimes protect against hotlinking assets by setting of a cookie from JavaScript on initial page load. Some injectors drop the URI query and anchor.
* Encode HTTPS frontend state into the URI in browsing history
* Navigate to the HTTP backend URI
* The injector sets the cookie
* The backend page should just navigate back in history (or execute the callback passed via the `Referer` header or the URI anchor if that is preserved)
* Hotlinking should work for some time if passing in the received cookie

## Referrer protection

Navigate to a jump page on the host, passing in the callback & state within the anchor or referrer similarly to how it is described for circumventing HTTPS mixed content.

## Preflight

* If a CORS request does not fit the constraints called `simple`, a preflight `OPTION` request will be made to the destination
* It has multiple user controlled fields (`Access-Control-Request-Method`, `Access-Control-Request-Headers`)
* Can be routed to a dynamic backend side script (or SSI)

## Resources references

These are not restricted by CORS and can be used for two-way communication:

* CSS stylesheets
* `<script>`: sometimes blocked for privacy, performance or bandwidth
* https://en.wikipedia.org/wiki/JSONP

Not restricted by CORS, but awkward due to navigating away and back via a callback:

* `<form>` POST: may also add an `Origin` header that could facilitate verification

One way only, egress via query parameters, but their content can't be read, except for 1 bit of information for each resource regarding success or failure:

* `<img>`, `<video>`, `<audio>`, `background-image`: sometimes blocked for bandwidth or accessibility
* `<iframe>`: sometimes blocked for privacy
