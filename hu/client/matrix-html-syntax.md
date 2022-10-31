# Mátrix kliensek formázási lehetőségei

## Áttekintés

A kérdés, hogy melyik kliens mennyire támogatja a `markdown` vagy `/html` formázott üzenetek megjelenítését illetve beküldését.

## Element Web lenyíló bélyegkép

`/html <details><summary><img src="mxc://grin.hu/iXjxZOXmgszkaLgchvrNSVCO/cat-on-tv-technology-doesnt-change-everything-for-the-better.jpeg" width=140 alt="cat sleeping on top of flat TV" title="cat on TV" /><span data-mx-bg-color="#888888" data-mx-color="#ffffff">Kattints a nagyításhoz</span><br> <i>Cat on top of TV: Technology doesn't change everything for the better</i></summary> <a href="https://framasphere.org/posts/5557d800db2001370ad8543d7eeced27"><img src="mxc://grin.hu/iXjxZOXmgszkaLgchvrNSVCO/cat-on-tv-technology-doesnt-change-everything-for-the-better.jpeg" height=700 alt="cat sleeping on top of flat TV" title="cat on TV" /></a> </details>`

## Element Web tesztüzenet 1

`/html <h1>h1</h1> <h2>h2</h2> <h3>h3</h3> <h4>h4</h4> <h5>h5</h5> <h6>h6</h6> <del>del</del> <strike>strike</strike> <sub>sub</sub> <span data-mx-color="#00ff00">span data-mx-color green</span> <span data-mx-bg-color="#ff0000">span data-mx-bg-color red</span> <sup>sup</sup> <br> ... br <font data-mx-color="#00ff00">font data-mx-color green</font> <font data-mx-bg-color="#ff0000">font data-mx-bg-color red</font> <font color="#00ff00">font color green</font> <hr> ... hr <b>b</b> <i>i</i> <strong>strong</strong> <em>em</em> <p>p</p> <u>u</u> <ol start=42><li>item 42</li><li>item 43</li></ol> <ul><li>some bullet</li><li>another bullet</li></ul> <table><caption>table caption</caption><thead><tr><th>table head column 1</th><th>col 2</th><th>col 3</th></tr></thead><tbody><tr><th>body row 2 head</th><td>r2c2</td><td>r2c3</td></tr><tr><th>r3h</th><td>r3c2</td><td>r3c3</td></tr></tbody></table> <details><summary>summary (click to see details)</summary> details</details> <span data-mx-spoiler="click to reveal">span data-mx-spoiler</span> <span data-mx-maths="span \over{ data-mx-maths}"><code>span \over{ data-mx-maths}</code></span> <div data-mx-maths="div \over{ data-mx-maths}"><code>div \over{ data-mx-maths}</code></div> <blockquote>blockquote</blockquote> <code>var code = ""; // highlight</code> <pre><code class="language-haxe">var preCode = "language-haxe"; // highlight</code></pre> <code class="language-haxe">var code = "language-haxe"; // highlight</code> <pre>var pre = ""; // highlight</pre> <pre><code>var preCode = ""; // highlight</code></pre> <a href="https://framasphere.org/posts/5557d800db2001370ad8543d7eeced27"><img src="mxc://grin.hu/iXjxZOXmgszkaLgchvrNSVCO/cat-on-tv-technology-doesnt-change-everything-for-the-better.jpeg" width=130 alt="cat sleeping on top of flat TV" title="&lt;img&gt; Cat on top of TV: Technology doesn't change everything for the better" /></a> ... mxc:// img <a href="https://diasp.eu/posts/aa9dc730ab7b013a1d0b101b0efced44">a href https://</a> <a href="mailto:a@example.com,b@example.com?cc=c@example.com&amp;bcc=d@example.com&amp;subject=hello&amp;body=from%20matrix">a href mailto:</a> <a href="magnet:?xt=urn:btih:ef6b1a1a21767fd63332674b77f900e33017a778&amp;dn=Ubuntu%20%C3%89retts%C3%A9gi%20Remix%2019.04">a href magnet:</a> <a href="ftp://example.com/">a href ftp://</a>`

* bitcoin:175tWpb8K1S7NmH4Zx6rewF9WQrcZv245W?amount=50&label=Luke-Jr&message=Donation%20for%20project%20xyz
* ftp://example.com/path
* geo:37.786971,-122.399677;u=35?z=20
* http://localhost/path
* https://framasphere.org/posts/5557d800db2001370ad8543d7eeced27
* im:user@example.com
* irc://example.com:6667/*matrix?keyword
* ircs://example.com:6667/*matrix?keyword
* magnet:?xt=urn:btih:ef6b1a1a21767fd63332674b77f900e33017a778&amp;dn=Ubuntu%20%C3%89retts%C3%A9gi%20Remix%2019.04
* mailto:a@example.com,b@example.com?cc=c@example.com&amp;bcc=d@example.com&amp;subject=hello&amp;body=from%20matrix
* matrix:#room:example.com
* mms://example.com:1755/path
* news:news:example.group.*
* nntp://news.server.example:119/example.group.this/12345
* openpgp4fpr:653909A2F0E37C106F5FAF546C8857E0D8E8F074
* sip:user@example.com:5060
* sftp://user:password;fingerprint=SHA256:HbW3g8zUjNSksFbqTiUWPWg2Bq1x8xdGUrliXFzSnUw@server.example:22/path
* sms:+15105550101,+15105550102?body=hello%20there
* smsto:+15105550101,+15105550102?body=hello%20there
* ssh://user:password;fingerprint=SHA256:HbW3g8zUjNSksFbqTiUWPWg2Bq1x8xdGUrliXFzSnUw@server.example:22
* tel:1.2-3(4)*5#6f;phone-context=c.example.com;isub=x;ext=9
* urn:ietf:rfc:2648
* webcal://example.com/calendar.ics
* wtai://wp/mc/+18165551212
* xmpp:romeo@montague.net?message;subject=Test%20Message;body=Here%27s%20a%20test%20message

### Element Web asztali

Algoritmus:

* https://github.com/matrix-org/matrix-react-sdk/blob/65d55bd0d972e4546990eaabc0e4365f736469f6/src/HtmlUtils.tsx#L236
* https://github.com/apostrophecms/sanitize-html

Jó:

* (majdnem minden, mivel csak olyan szerepel ebben a tesztben amit támogatnia kell)
* code és pre+code esetén: megadott nyelv esetén szintaxis kiemelés
* code: monospace, szürke háttér, utána soremelés
* pre: monospace, sorszámozás, szürke háttér az egész soron, utána soremelés, előtte-utána helykihagyás

Rossz:

* LaTeX: fel kell kapcsolni a Labs-ban, de elképzelhető, hogy utána nem lehet dollárjelet írni kódba és nem lehet kikapcsolni sem, így nem javasolt
* thead: bár kezelésben elkülönül a fejléc a törzstől, de egyszínűvé válik ettől a felső két sor
* h2: kicsit kisebb mint a h3, de nagyobb mint a h4 és több a térköz
* h1: kicsit kisebb mint a h2, de nagyobb mint a h4 és több a térköz

### Element iOS

Jó:

* h3, h4, h5, h6
* del, strike
* font color green
* b strong i em p u
* ul
* br
* blockquote
* code
* pre
* a href

Nem jó:

* h1, h2
* sub sup
* data-mx-*color
* hr: többszörös sortörés
* ol (soronként jelenik meg, kb. bajusz nélkül ul)
* table
* details summary: mindkét szöveget mutatja egyszerre
* spoiler
* data-mx-maths
* img mxc:// (kimaradt)

### FluffyChat iOS

Algoritmus:

* https://gitlab.com/famedly/fluffychat/-/blob/main/lib/views/widgets/html_message.dart#L2
* https://github.com/Sorunome/flutter_matrix_html

Jó:

* h1, h2, h3, h4, h5, h6: viszont elé mintha nem rakna sortörést
* del strike
* data-mx-*color, color
* b strong i em u
* ol, ul
* table, tr, th, td
* caption: apróság, hogy plusz vonalat húz a jobb oldalára
* spoiler
* br
* span data-mx-maths, div data-mx-maths
* blockquote
* code: inverz betűszín
* pre: monospace
* pre+code automatikus nyelvi színezés
* pre+code adott nyelvű színezés: `<pre><code class="language-haxe">var preCode = "language-haxe"; // highlight</code></pre>`
* img mxc://
* a href

Nem jó:

* sub: kisbetűt csinál
* sup
* hr: sortörés
* p: a lezáró után sortörést rak
* thead: nem különül el
* details, summary: mindkét szöveget mutatja egyszerre
* Amennyiben `a href`-ben ékezetes UTF-8 karakterek szerepelnek nyersen percentile kódolás nélkül

### Geany markdown plugin

Jó:

* h1, h2, h3, h4, h5, h6
* del strike sub sup
* hr br p
* font color
* b strong i em u
* ol ul
* table, caption, tr, th, td: megy, de nincs kerete (kell border=1)
* thead: nem különül el
* summary, details
* blockquote
* pre, code: monospace, más különbség nincs
* img https
* a href https
* a href #

Nem jó:

* data-mx*
* a href mailto, magnet, ftp

### Discord t2bot bridge

Jó:

* del strike
* b strong i em u
* br
* hr: néhány mínuszjellel és sortöréssel helyettesíti
* ol ul
* code
* pre
* spoiler (nincs szöveges tájékoztatás, csak egy fekete téglalappal van eltakarva)
* színezés: pre + code + class="language-haxe"
* a href https:// + előnézet

Nem jó:

* h1, h2 nagybetűs
* h1, h2, h3, h4, h5, h6 félkövér
* sub sup p
* color, bg-color
* table
* summary-details
* mxc:// img képbeszúrás
* a href mailto, magnet:, ftp://
