# Remote device fingerprinting from the distant

## Introduction

The fingerprinting actor does not need to be near our devices.
They may observe our transmission through a MITM position or by operating or compromising a server or client that we connect to.

See local options in case of physical proximity:

* [local-fingerprinting.md](local-fingerprinting.md)

## Purpose

### Threat

As a form of a surreptitious evercookie, correlating a user profile to sell or better target for future attacks:

* https://en.wikipedia.org/wiki/Evercookie

### Benign

Serve a benign purpose in agreement with the terms of service to mitigate abuse:

* [../../hu/server/passive-abuse-prevention.md](../../hu/server/passive-abuse-prevention.md)

## Network level options

* HTTP headers
  * Accept, Accept-Encoding, Accept-Language, User-Agent
* the wall clock at the user: binary search using caching headers or wildcard certification expiry
* GeoIP, reverse DNS
* traceroute, intermediate firewall determination
* measure round trip time and hop count
  * depending on WAN uplink technology, fine grain measurement of latency and jitter to nearest data centers to triangulate
  * based on TLS handshake and TCP ACK timing
* network speed test based on dummy fillers
* https://en.wikipedia.org/wiki/TCP/IP_stack_fingerprinting
  * local NAT port range of outgoing connections
  * TCP congestion control algorithm, window size, options, handling of simulated packet loss, TLS properties
  * sequence number and timestamp jitter and rate
  * header sizes, padding
  * MTU
  * how often does it flush its buffers and how fast does it close the connection
* DNS resolver: redirects, TTL, latency, resolver side cache
* DNS resolving: client side cache
* IPv6 address, behavior, preference

### CPU speed estimate

* based on TLS operations
* based on overhead of chunked HTTP encoding with very short chunks
* how fast are further resources pulled in after sending a deliberately huge or complicated payload
  * almost zip-bomb like extremely well compressible stream of either text or nested HTML markup
  * calibrate network transfer overhead of a similar amount of normal data
  * predict implemented decompression algorithm
  * predict parser kind for HTTP/HTML/CSS/Javascript/images/fonts, inline vs. file content
  * estimate CPU speed and cache amount

## Application level options

Includes device fingerprinting, user behavior profiling or user biometrics via either JavaScript or only with CSS

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

### Browsing history

Could be achieved automatically via fine grained timing and CPU cache side channels.

Manually by tricking the user into clicking onto links that look differently based on whether the user has visited a certain unrelated site or not:

* https://varun.ch/history

> Retrieving your browsing history through a CAPTCHA

### Services where you are logged in

Certain services may have images, scripts, styles, pages or other assets that produce different side effects based on whether the user is logged in or not.
There are various technicalities for embedding.

https://www.grepular.com/Abusing_HTTP_Status_Codes_to_Expose_Private_Information

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
