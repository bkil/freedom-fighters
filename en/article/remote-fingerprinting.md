# Remote device fingerprinting from the distance

## Introduction

The fingerprinting actor does not need to be near our devices.
They may observe our transmission through a MITM position or by operating or compromising a server or client that we connect to.

* https://github.com/xsleaks/wiki/tree/master/content/docs/attacks
* https://github.com/fingerprintjs/fingerprintjs

See local options in case of physical proximity:

* [local-fingerprinting.md](local-fingerprinting.md)

## Purpose

### Threat

As a form of a surreptitious evercookie, correlating a user profile to sell or better target for future attacks:

* https://en.wikipedia.org/wiki/Evercookie

### Benign

Serve a benign purpose in agreement with the terms of service to mitigate abuse:

* [../../hu/server/passive-abuse-prevention.md](../../hu/server/passive-abuse-prevention.md)

## Network level

Assuming that the user agent application can be anything that uses TCP/TLS or a generic HTTP transport.

### TCP Fast Open cookie

https://arxiv.org/pdf/1905.03518.pdf

> Enhanced Performance and Privacy for TLS over TCP Fast Open

### Location, ISP subscription

* GeoIP, reverse DNS
* traceroute, intermediate firewall determination
* measure round trip time and hop count
  * depending on WAN uplink technology, fine grain measurement of latency and jitter to nearest data centers to triangulate
  * based on TLS handshake and TCP ACK timing
* IPv6 address, behavior, preference

### Network speed test

* based on dummy fillers
* if this varies within a session or between sessions for a non-mobile ISP, consider the maximum and correlate dips with local access technology (spotty wifi)

### Network reliability

* gather statistics and build a detailed model on buffering events, reloads or speed dips
* both in general and according to time of day

### Network level software and settings

* https://en.wikipedia.org/wiki/TCP/IP_stack_fingerprinting
  * local NAT port range of outgoing connections
  * TCP congestion control algorithm, window size, options, handling of simulated packet loss, TLS properties
  * sequence number and timestamp jitter and rate
  * header sizes, padding
  * MTU
  * how often does it flush its buffers and how fast does it close the connection
* DNS resolver: redirects, TTL, latency, resolver side cache, internationalized domain names

### Network CPU speed estimate

* based on TLS handshake operations
* based on overhead of chunked HTTP encoding with very short chunks or a short TLS record size

### Clock pinpointing

* the wall clock at the user: binary search using caching HTTP headers or wildcard certificate expiry

### Network based user behavior

* IP, ASN or domain name filters set by the user or ISP
* time and intensity of activity per day and per week

### Correlate overlapping connections of the same user

* if some other application or web connection also happened to overlap with a compatible fingerprint, merge profiles
* for example, if streaming music or a video while also checking e-mail or chatting in a browser

### Correlate overlapping connections of different users

* if a guest who has trackers installed connects to the home wireless network of another user
* if similar networking conditions apply to mobile users in proximity, share their location data and attempt to connect them socially as well
* https://patents.justia.com/patent/10111059

> Systems and methods for utilizing wireless communications to suggest connections for a user - Facebook

## Application level options

### Headers

* HTTP: Accept, Accept-Encoding, Accept-Language, User-Agent
* SIP options
* XEP-0030 Service Discovery
* other client options related to rich protocols

### Application based user behavior

* generate a few HTTP redirects
* see which redirect was cached
* see which domains were cached by the client resolver: repeated poll to determine expiry (and hence time of the previous resolution)

### HTTP redirect handling

* limits
* loops
* GET vs. POST transformation
* caching of answer

### Application level Fuzzing

* Perturbate markup and binary streams in ways that result in undefined behavior according to the standards
* Vary between visits the content and HTTP/RTMP headers for main entry point (HTML or stream)
* Detect application interpretation automatically: reconnection, seeking or buffering changes for stream recovery

## Browser level options

Assuming that the user agent is a web browser. Includes device fingerprinting, user behavior profiling or user biometrics via either JavaScript or only with CSS.

### Browser level fuzzing

* Vary within the same visit for subresources: HTTP headers, media, CSS, JavaScript, iframes or frames
* Detect application interpretation automatically: CSS/JavaScript or HTTP GET for browsers
* Determine application interpretation by user behavior (i.e., visibility)

### HTTP cache

* HTTP client side cache status of various locally generated assets or global CDN referenced ones
* client side handling of various HTTP caching headers
* https://blog.mozilla.org/security/2021/01/26/supercookie-protections/

### Browser CPU speed estimate

* how fast are further resources pulled in after sending a deliberately huge or complicated payload
* almost zip-bomb like extremely well compressible stream of either text or nested HTML markup
* calibrate network transfer overhead of a similar amount of normal data
* predict implemented decompression algorithm
* predict parser kind for HTTP/HTML/CSS/Javascript/images/fonts, inline vs. file content
* estimate CPU speed and cache amount

### HTML-only

* Determine which resources get downloaded: application manifest, size and image format for favicon and an image set
* How meta viewport is handled
* Which proprietary meta and markup is interpreted
* Determine which subsets of resources are hidden by a web browser extension (e.g., reading mode) or a browser setting
* Effect of color-scheme determined manually

### CSS-only

HTTP Accept, Accept-Language, Accept-Encoding request header, @supports (-webkit-app-region, -moz-appearance, -apple-pay-button-style, -webkit-touch-callout, -moz-osx-font-smoothing, accent-color), @media (hover, any-hover, pointer, any-pointer, color, color-gamut, forced-colors, inverted-colors, monochrome, prefers-color-scheme, prefers-contrast, prefers-reduced-motion, dynamic-range, device-width, device-height and -webkit-device-pixel-ratio), @font-face (Roboto, Ubuntu, Calibri, MS UI Gothic, Gill Sans, Helvetica Neue, Arimo)

* https://github.com/fingerprintjs/blog-nojs-fingerprint-demo
* https://noscriptfingerprint.com/
* https://fingerprintjs.com/blog/disabling-javascript-wont-stop-fingerprinting/

HTTP 308, HTTP 410 responses, an exhaustive list of @media queries and fonts:

* https://github.com/OliverBrotchie/CSS-Fingerprint
* https://csstracking.dev/

Keyboard biometrics:

* https://github.com/kkuchta/css-only-chat

Pointer biometrics:

* https://www.bleepingcomputer.com/news/security/researcher-finds-css-only-method-to-track-mouse-movements/

Mostly just examples, @supports (-webkit-appearance, -ms-ime-align, -moz-appearance), @font-face (Calibri), hover duration via @keyframes, checkbox :checked, textbox pattern :valid, @media (orientation, min-device-width, min-device-height)

* https://github.com/jbtronics/CrookedStyleSheets

Further possibility:

* https://developer.mozilla.org/en-US/docs/Web/CSS/@import

### Biometrics

* Reading speed
* Screen object scanning speed
* Typing speed
* Word typing patterns
* Typos
* Vocabulary, n-grams
* Mouse movement patterns
* Pointer dexterity: among distant or near elements, hitting small or large targets, speed
* Visual acuity
* Color blindness

### Visited links

Infer browsing history by styling difference of anchor links.
Could be achieved automatically via fine grained timing and CPU cache side channels.

Manually by tricking the user into clicking onto links that look differently based on whether the user has visited a certain unrelated site or not:

* https://varun.ch/history

> Retrieving your browsing history through a CAPTCHA

### History API

The `history.length` property can still be read:

* https://developer.mozilla.org/en-US/docs/Web/API/History

* If our portal requires page switching navigation, we could occasionally navigate the tab way back into her history before they opened our page.
* Either just when clicking their back/forward button, or when opening links.
* If they then reopen our page, we could establish more referrers.

### Scroll Restoration

The app layout could allow showing the same content even for small perturbations of the scroll position.
We could introduce a small perturbation into the scroll position for new visitors and possibly use that for limited tracking.

* https://developer.mozilla.org/en-US/docs/Web/API/History/scrollRestoration

### Lazy loading

Real time reading position and scroll restoration may be unveiled remotely using images. Some browsers hence disable lazy loading when JavaScript is disabled. Notably, this side channel may still be present if JavaScript is globally enabled within the browser but interactively blocked by a user extension.

* https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#lazy

### Services where you are logged in

Certain services may have images, scripts, styles, pages or other assets that produce different side effects based on whether the user is logged in or not.
There are various technicalities for embedding.

* https://www.grepular.com/Abusing_HTTP_Status_Codes_to_Expose_Private_Information
* https://github.com/RobinLinus/socialmedia-leak
* https://meta.stackoverflow.com/questions/336337/stack-overflow-logged-in-information-leak-part-2

### Favicon cache

https://arstechnica.com/information-technology/2021/02/new-browser-tracking-hack-works-even-when-you-flush-caches-or-go-incognito/

Can work without JavaScript my meta refresh redirects.

### Content Security Policy reports

* The exact format of the JSON sent by the browser varies.
* They may also differ in nuance ways in parsing the policy itself.
* https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP

## Display refresh rate

* Ideally via WebGL in JavaScript, but might be approximated via CSS animation
* Determine which coarse display refresh rate bin did the system _attempt_ to use
* Also determine precise oscillator skew between _achieved_ display refresh vs. system
* Determine whether the display is refreshed horizontally or vertically based on flickering
* Needs manual cooperation from the user (e.g., CAPTCHA): make certain links (or thin lines) more or less visible based on clock ratio and phase
* https://en.wikipedia.org/wiki/Wagon-wheel_effect
* https://en.wikipedia.org/wiki/Beat_(acoustics)
* https://en.wikipedia.org/wiki/Aliasing
* https://bkil.gitlab.io/static-wonders.css/fingerprint/display-refresh-rate.html
