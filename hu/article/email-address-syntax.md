# Email címek szintaxisa

## Validáló implementációk

### HTML5 input

- https://html.spec.whatwg.org/multipage/input.html#valid-e-mail-address
- https://github.com/foundation/foundation-sites/blob/4e6c218993188d9f5368061d5dc1426978ab01bf/js/foundation.abide.js#L845

Unicode elgépelve szerepel egyes oldalakon:

```/^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/```

Van ahol egyszerűsítve szerepel:

```/^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/```

Van ahol javított változatban szerepel:

```/^[a-zA-Z0-9.!#$%&'*+\/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/```

- _(a szöveges leírásban Unicode karaktereket említenek)_
- _(a több email címes parszernél azt írják le kell venni a vesszők körül a whitespace karaktereket)_

### GitHub flavored Markdown explicit

Szintaxisa megegyezik a HTML input form példával amennyiben a levélcím `<` és `>` jelek között van megadva:

- https://gitlab.com/gitlab-org/gitlab/-/blob/master/lib/banzai/filter/markdown_engines/common_mark.rb
- https://github.com/gjtorikian/commonmarker/blob/b4335a63fe177160788d31b5325e1a0fc624a8c9/ext/commonmarker/scanners.re#L99

```
[<]
[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+
[@]
[a-zA-Z0-9]([a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?
([.][a-zA-Z0-9]([a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*
[>]
```

### GitHub flavored Markdown linkify

Más heurisztikákat használ amennyiben csak szabad szövegben fordul elő a levélcím. A kiegészítések C-ben vannak megírva, becslés alapján rekonstruálva a regexp:

- https://github.github.com/gfm/#extended-email-autolink _"recognised within any text node according to the following rules"_
- https://github.com/gjtorikian/commonmarker/blob/b4335a63fe177160788d31b5325e1a0fc624a8c9/ext/commonmarker/autolink.c#L272
- https://github.com/github/cmark-gfm/blob/master/extensions/autolink.c#L272

```
/\b[0-9a-z._+-]+@([0-9a-z_-]+\.)+[0-9a-z_-]*([0-9a-z]\.?|[_-]\.)\b/i
```

### GitLab.com

- https://gitlab.com/gitlab-org/gitlab/-/blob/ed19a0bdcacc29a21f447feb261f6198af06f06c/config/initializers/8_devise.rb#L136

```
/\A[^@]+@[^@]+\z/
```

- https://gitlab.com/gitlab-org/gitlab/-/blob/ed19a0bdcacc29a21f447feb261f6198af06f06c/ee/lib/gitlab/code_owners/reference_extractor.rb#L11

```
/(?<email>([^@\s]+@[^@\s]+(?<!\W)))/
```

### Matrix.org

- https://github.com/matrix-org/matrix-react-sdk/blob/50dd9da913b6f099fcab7793869dce5340d391c0/src/email.ts#L18

```
/^[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?$/i
```

### Mozilla Gecko-dev

Elvileg erre épül a Thunderbird is.

- https://github.com/mozilla/gecko-dev/blob/d36cf98aa85f24ceefd07521b3d16b9edd2abcb7/third_party/python/voluptuous/voluptuous/validators.py#L22
- https://github.com/kvesteri/validators/blob/master/validators/email.py#L5

Python kódból rekonstruálva kb:

```
/^
([-!#$%&'*+/=?^_`{}|~0-9A-Z]+\
(\.[-!#$%&'*+/=?^_`{}|~0-9A-Z]+)*\
|"([\001-\010\013\014\016-\037!#-\[\]-\177]|\
\\[\001-\011\013\014\016-\177])*")\
@\
((?:[A-Z0-9](?:[A-Z0-9-]{0,61}[A-Z0-9])?\.)+\
(?:[A-Z]{2,6}\.?|[A-Z0-9-]{2,}\.?)\
|\[(25[0-5]|2[0-4]\d|[0-1]?\d?\d)\
(\.(25[0-5]|2[0-4]\d|[0-1]?\d?\d)){3}\])$\
/i
```

### Google Closure Library

### Google Closure Library emailaddress

- https://github.com/google/closure-library/blob/4f18d359603b23dd4db402d62d796ea0e40ae48f/closure/goog/format/emailaddress.js#L156

```
goog.format.EmailAddress.SPECIAL_CHARS = '()<>@:\\\".[]';
goog.format.EmailAddress.ADDRESS_SEPARATORS_ = ',;';
goog.format.EmailAddress.CHARS_REQUIRE_QUOTES_ =
   goog.format.EmailAddress.SPECIAL_CHARS +
   goog.format.EmailAddress.ADDRESS_SEPARATORS_;
goog.format.EmailAddress.LOCAL_PART_REGEXP_STR_ =
   '[+a-zA-Z0-9_.!#$%&\'*\\/=?^`{|}~-]+';
goog.format.EmailAddress.DOMAIN_PART_REGEXP_STR_ =
   '([a-zA-Z0-9-]+\\.)+[a-zA-Z0-9]{2,63}';
goog.format.EmailAddress.EMAIL_ADDRESS_ = new RegExp(
   '^' + goog.format.EmailAddress.LOCAL_PART_REGEXP_STR_ + '@' +
   goog.format.EmailAddress.DOMAIN_PART_REGEXP_STR_ + '$');
```

- https://github.com/google/closure-library/blob/4f18d359603b23dd4db402d62d796ea0e40ae48f/closure/goog/format/internationalizedemailaddress.js

```
goog.format.InternationalizedEmailAddress.EAI_LOCAL_PART_REGEXP_STR_ =
    '((?!\\s)[+a-zA-Z0-9_.!#$%&\'*\\/=?^`{|}~\u0080-\uFFFFFF-])+';
goog.format.InternationalizedEmailAddress.EAI_LABEL_CHAR_REGEXP_STR_ =
    '(?!\\s)[a-zA-Z0-9\u0080-\u3001\u3003-\uFF0D\uFF0F-\uFF60\uFF62-\uFFFFFF-]';
goog.format.InternationalizedEmailAddress.EAI_DOMAIN_PART_REGEXP_STR_ =
    '(' + goog.format.InternationalizedEmailAddress.EAI_LABEL_CHAR_REGEXP_STR_ +
    '+[\\.\\uFF0E\\u3002\\uFF61])+' +
    goog.format.InternationalizedEmailAddress.EAI_LABEL_CHAR_REGEXP_STR_ +
    '{2,63}';
goog.format.InternationalizedEmailAddress.EAI_EMAIL_ADDRESS_ = new RegExp(
    '^' + goog.format.InternationalizedEmailAddress.EAI_LOCAL_PART_REGEXP_STR_ +
    '@' +
    goog.format.InternationalizedEmailAddress.EAI_DOMAIN_PART_REGEXP_STR_ +
    '$');
```

#### Google Closure Library linkify

Gmail üzenet szabad szövegében kattinthatóvá alakításért felel.

- https://github.com/google/closure-library/blob/fd8a584d018581e2c41f98b4b7f403c0f7992847/closure/goog/string/linkify.js#L265

```
goog.string.linkify.TOP_LEVEL_DOMAIN_ = '(?:com|org|net|edu|gov' +
   '|aero|biz|cat|coop|info|int|jobs|mobi|museum|name|pro|travel' +
   '|arpa|asia|xxx' +
   '|[a-z][a-z])\\b';
goog.string.linkify.EMAIL_RE_STRING_ =
   '(?:mailto:)?([\\w.!#$%&\'*+-/=?^_`{|}~]+@[A-Za-z0-9.-]+\\.' +
   goog.string.linkify.TOP_LEVEL_DOMAIN_ + ')';
goog.string.linkify.EMAIL_RE_ =
   new RegExp(goog.string.linkify.EMAIL_RE_STRING_, 'i');
goog.string.linkify.FIND_LINKS_RE_ = new RegExp(
   '([\\S\\s]*?)(' +
       '\\b' + goog.string.linkify.EMAIL_RE_STRING_ + '|' +
       '\\b' + goog.string.linkify.URL_RE_STRING_ + '|$)',
   'gi');
```

#### Google Closure Library editor link

Gmail `mailto:` hivatkozáson az "Edit Link" akció esetén használt

- https://github.com/google/closure-library/blob/4f18d359603b23dd4db402d62d796ea0e40ae48f/closure/goog/editor/link.js#L366

```
goog.editor.Link.LIKELY_EMAIL_ADDRESS_ = new RegExp(
    '^' +
        '[\\w-]+(\\.[\\w-]+)*' +
        '\\@' +
        '([\\w-]+\\.)+' +
        '(\\d+|\\w\\w+)$',
    'i');
```

#### Google Closure Library safeurl

HTML tisztításkor a kattinthatóság biztonságát szavatolja.

- https://github.com/google/closure-library/blob/7c5e8ef152adf9cc814875c42ab2a0244653b69c/closure/goog/html/safeurl.js#L664

```
goog.html.SAFE_URL_PATTERN_ = /^(?:(?:https?|mailto|ftp):|[^:/?#]*(?:[/?#]|$))/i;
```

- https://github.com/google/closure-library/blob/7c5e8ef152adf9cc814875c42ab2a0244653b69c/closure/goog/html/safeurl.js#L404

```
goog.html.SIP_URL_PATTERN_ = new RegExp(
   '^sip[s]?:[+a-z0-9_.!$%&\'*\\/=^`{|}~-]+@([a-z0-9-]+\\.)+[a-z0-9]{2,63}$',
   'i');
```

### PHP logical_filters

- https://github.com/php/php-src/blob/5caaf40b43303887a38d738a9c2a2f4cf6dc9b1a/ext/filter/logical_filters.c#L649

```/^(?!(?:(?:\\x22?\\x5C[\\x00-\\x7E]\\x22?)|(?:\\x22?[^\\x5C\\x22]\\x22?)){255,})(?!(?:(?:\\x22?\\x5C[\\x00-\\x7E]\\x22?)|(?:\\x22?[^\\x5C\\x22]\\x22?)){65,}@)(?:(?:[\\x21\\x23-\\x27\\x2A\\x2B\\x2D\\x2F-\\x39\\x3D\\x3F\\x5E-\\x7E]+)|(?:\\x22(?:[\\x01-\\x08\\x0B\\x0C\\x0E-\\x1F\\x21\\x23-\\x5B\\x5D-\\x7F]|(?:\\x5C[\\x00-\\x7F]))*\\x22))(?:\\.(?:(?:[\\x21\\x23-\\x27\\x2A\\x2B\\x2D\\x2F-\\x39\\x3D\\x3F\\x5E-\\x7E]+)|(?:\\x22(?:[\\x01-\\x08\\x0B\\x0C\\x0E-\\x1F\\x21\\x23-\\x5B\\x5D-\\x7F]|(?:\\x5C[\\x00-\\x7F]))*\\x22)))*@(?:(?:(?!.*[^.]{64,})(?:(?:(?:xn--)?[a-z0-9]+(?:-+[a-z0-9]+)*\\.){1,126}){1,}(?:(?:[a-z][a-z0-9]*)|(?:(?:xn--)[a-z0-9]+))(?:-+[a-z0-9]+)*)|(?:\\[(?:(?:IPv6:(?:(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){7})|(?:(?!(?:.*[a-f0-9][:\\]]){7,})(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,5})?::(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,5})?)))|(?:(?:IPv6:(?:(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){5}:)|(?:(?!(?:.*[a-f0-9]:){5,})(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,3})?::(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,3}:)?)))?(?:(?:25[0-5])|(?:2[0-4][0-9])|(?:1[0-9]{2})|(?:[1-9]?[0-9]))(?:\\.(?:(?:25[0-5])|(?:2[0-4][0-9])|(?:1[0-9]{2})|(?:[1-9]?[0-9]))){3}))\\]))$/iD```

`FILTER_FLAG_EMAIL_UNICODE` esetén:

```/^(?!(?:(?:\\x22?\\x5C[\\x00-\\x7E]\\x22?)|(?:\\x22?[^\\x5C\\x22]\\x22?)){255,})(?!(?:(?:\\x22?\\x5C[\\x00-\\x7E]\\x22?)|(?:\\x22?[^\\x5C\\x22]\\x22?)){65,}@)(?:(?:[\\x21\\x23-\\x27\\x2A\\x2B\\x2D\\x2F-\\x39\\x3D\\x3F\\x5E-\\x7E\\pL\\pN]+)|(?:\\x22(?:[\\x01-\\x08\\x0B\\x0C\\x0E-\\x1F\\x21\\x23-\\x5B\\x5D-\\x7F\\pL\\pN]|(?:\\x5C[\\x00-\\x7F]))*\\x22))(?:\\.(?:(?:[\\x21\\x23-\\x27\\x2A\\x2B\\x2D\\x2F-\\x39\\x3D\\x3F\\x5E-\\x7E\\pL\\pN]+)|(?:\\x22(?:[\\x01-\\x08\\x0B\\x0C\\x0E-\\x1F\\x21\\x23-\\x5B\\x5D-\\x7F\\pL\\pN]|(?:\\x5C[\\x00-\\x7F]))*\\x22)))*@(?:(?:(?!.*[^.]{64,})(?:(?:(?:xn--)?[a-z0-9]+(?:-+[a-z0-9]+)*\\.){1,126}){1,}(?:(?:[a-z][a-z0-9]*)|(?:(?:xn--)[a-z0-9]+))(?:-+[a-z0-9]+)*)|(?:\\[(?:(?:IPv6:(?:(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){7})|(?:(?!(?:.*[a-f0-9][:\\]]){7,})(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,5})?::(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,5})?)))|(?:(?:IPv6:(?:(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){5}:)|(?:(?!(?:.*[a-f0-9]:){5,})(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,3})?::(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,3}:)?)))?(?:(?:25[0-5])|(?:2[0-4][0-9])|(?:1[0-9]{2})|(?:[1-9]?[0-9]))(?:\\.(?:(?:25[0-5])|(?:2[0-4][0-9])|(?:1[0-9]{2})|(?:[1-9]?[0-9]))){3}))\\]))$/iDu```

- https://www.php.net/manual/en/filter.filters.validate.php

> FILTER_VALIDATE_EMAIL
> the syntax in RFC 822, with the exceptions that comments and whitespace folding and dotless domain names are not supported.
> It only checks Addr-spec part of email address. (without the display name)
>
> FILTER_VALIDATE_URL
> will only find ASCII URLs to be valid; internationalized domain names (containing non-ASCII characters) will fail.
> `var_dump(filter_var($email, FILTER_VALIDATE_EMAIL));`

### RoundCube check_email

* https://github.com/roundcube/roundcubemail/blob/0044673e112d3f1e553333ac3d6fa6e896b1223b/program/lib/Roundcube/rcube_utils.php#L95

PHP kódból visszafejtve, alapvetően kb.:

```
/^("(\\.|[^\\"])*.|([^.\\ ",:;<>@]+\.)*[^.\\ ",:;<>@]+)@\
(\[([iI][pP][vV]6:[0-9a-fA-F:.]+|[0-9.]+)\]|\
(((xn--)?[A-Za-z0-9][A-Za-z0-9-]{0,61}[A-Za-z0-9]|[A-Za-z0-9])\.)+\
(xn--[A-Za-z0-9][A-Za-z0-9-]{0,61}[A-Za-z0-9]|\
[A-Za-z0-9]{1,63}))$/
```

* Nem tartalmazhat vezérlőkaraktert (`\p{Cc}`)
* Legfeljebb 254 karakter hosszú
* IPv4 és IPv6 részletesebben is validálva
* A TLD nem lehet `/^[0-9]+$/`
* Domén név `A`, `MX`, `CNAME` vagy `AAAA` bejegyzése opcionálisan feloldva

### RoundCube parse_host

* https://github.com/roundcube/roundcubemail/blob/0044673e112d3f1e553333ac3d6fa6e896b1223b/program/lib/Roundcube/rcube_utils.php#L711

```
/^(.*)@([a-z0-9\.\-\[\]\:]+)/$
```

### RoundCube idn_convert

* https://github.com/roundcube/roundcubemail/blob/0044673e112d3f1e553333ac3d6fa6e896b1223b/program/lib/Roundcube/rcube_utils.php#L711

```
/^[^@]*@[^@]*$/
```

* a `parse_host()` is hívja

### RoundCube email_input_format

* https://github.com/roundcube/roundcubemail/blob/0044673e112d3f1e553333ac3d6fa6e896b1223b/program/include/rcmail_sendmail.php#L731

```
/<*(\S+|("[^"]+"))@\S+>*/
```

### Mailman2

- https://salsa.debian.org/mailman-team/mailman2/-/blob/master/Mailman/Utils.py#L240

Python kódból visszafejtve kb:

```
/^[^\]\[()<>|:;^,\\"\000-\037\177-\377@ ]+@([a-z0-9][-a-z0-9]*\.)+[a-z0-9][-a-z0-9]*$/i
```

Viszont a webes felület kiakad néhány jel meglététől (**TODO**: sokszor kiakad olyanoktól is mint a `#`, `?` vagy `/`):

- https://salsa.debian.org/mailman-team/mailman2/-/blob/master/Mailman/Utils.py#L280

### Mailman3

- https://gitlab.com/mailman/mailman/-/blob/ae1e83b9d859ff83bb364b0b7960cec4ea6d1213/src/mailman/email/validate.py#L29

Python kódból visszafejtve kb. _(figyelembe véve a `split_email()` miatti localpart `@` korlátozást is)_:

```
/^[-0-9a-z!#$%&'*+./=?_`{}~]+@([0-9a-z]([-0-9a-z]*[0-9a-z])?\.)+[0-9a-z]([-0-9a-z]*[0-9a-z])?$/i
```

### Django

- https://github.com/django/django/blob/e1e81aa1c4427411e3c68facdd761229ffea6f6f/django/core/validators.py#L159

```
/^([-!#$%&'*+/=?^_`{}|~0-9A-Z]+(\.[-!#$%&'*+/=?^_`{}|~0-9A-Z]+)*\Z\
|"([\001-\010\013\014\016-\037!#-\[\]-\177]|\\[\001-\011\013\014\016-\177])*"\Z)\
@(\
((?:[A-Z0-9](?:[A-Z0-9-]{0,61}[A-Z0-9])?\.)+)(?:[A-Z0-9-]{2,63}(?<!-))\Z\
|\[([A-f0-9:.]+)\]\Z\
|localhost)$/i
```

- A Mailman Postorius is használja.
- Még megpróbálja IDN punycode enkódolva is ellenőrizni a domén nevet
- IPv4 címet is ellenőriz
- IPv6 címet nem fogad el mert a numerikus validálás előtt nem vágja le az `IPv6:` előtagját és a felsorolt betűhalmaz amúgy sem engedi meg

### Ruby URI::MailTo::EMAIL_REGEXP

Az OpenStreetMap.org `email_link` beillesztője használja ezt is.

- https://github.com/ruby/ruby/blob/d6d38d9099b1780febf5cbe50431421e84162536/lib/uri/mailto.rb#L55

```
/\A[a-zA-Z0-9.!\#$%&'*+\/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*\z/
```

### Ruku

A Ruby OpenStreetMap.org website `linkify` is ezt használja (például személyes üzenetküldésnél).

- https://github.com/vmg/rinku/blob/0e0a80bad9c270d07f4a306f9dd15ec57d28fe70/ext/rinku/autolink.c#L239

C kódból visszafejtve kb.

```
/^[0-9a-z.+_%-]+@[0-9a-z_-.]*\.[0-9a-z_-]+$/i
```

### phpBB make_clickable

- https://github.com/phpbb/phpbb/blob/c0f031ba3a689bb54121060c32a05c5dae6ef6ba/phpBB/includes/functions.php#L2727

```
((?:[\w\!\#$\%\&\'\*\+\-\/\=\?\^\`{\|\}\~]+\.)*(?:[\w\!\#$\%\'\*\+\-\/\=\?\^\`{\|\}\~]|&amp;)+)@\
((((([a-z0-9]{1}[a-z0-9\-]{0,62}[a-z0-9]{1})|[a-z])\.)+[a-z]{2,63})|\
(\d{1,3}\.){3}\d{1,3}(\:\d{1,5})?)
```

- https://github.com/phpbb/phpbb/blob/dc966787e144d262dee74ac64bd449887a336f28/phpBB/includes/functions_content.php#L1000

```
/(^|[\n\t (>])(' . $email . ')/iu
```

### phpBB regisztráció

- `^.{6,60}$`
  - https://github.com/phpbb/phpbb/blob/dc966787e144d262dee74ac64bd449887a336f28/phpBB/includes/ucp/ucp_register.php#L272
- kisbetűsítve ellenőrzi az egyediségét
  - https://github.com/phpbb/phpbb/blob/c6ecef9769db14fc597e6c880009a26a15fe484e/phpBB/includes/functions_user.php#L1933
- létezzen `A` vagy `MX` DNS rekord a domain alatt
  - https://github.com/phpbb/phpbb/blob/c6ecef9769db14fc597e6c880009a26a15fe484e/phpBB/includes/functions_user.php#L1912

## Címlista tisztítók

### emailCheck.sh

* https://github.com/deajan/linuxscripts/blob/master/emailCheck.sh#L73

```
^[a-z0-9!#\$%&'*+/=?^_\`{|}~-]+(\.[a-z0-9!#$%&'*+/=?^_\`{|}~-]+)*@([a-z0-9]([a-z0-9-]*[a-z0-9])?\.)+[a-z0-9]([a-z0-9-]*[a-z0-9])?\$
```

### email_inquire

- https://github.com/gimmethat-hq/email_inquire/blob/master/lib/email_inquire/validator/email_format.rb#L9

```
NAME_ALLOWED_CHARS = /[a-z0-9._%+-]/

NAME_REGEXP = /
  \A
  [a-z0-9]
  [#{NAME_ALLOWED_CHARS}]{0,63}
  \z
/

DOMAIN_REGEXP = /
  \A
  (?:
    (?=
      [a-z0-9-]{1,63}
      \.
    )
    [a-z0-9]+
    (?:
      -
      [a-z0-9]+
    )*
    \.
  ){1,8}
  [a-z]{2,63}
  \z
/
```

## Dokumentáció

- https://emailregex.com/email-validation-summary/
- https://www.jochentopf.com/email/chars.html
- https://tools.ietf.org/html/rfc822 _STANDARD FOR THE FORMAT OF ARPA INTERNET TEXT MESSAGES, August 13, 1982_
- https://tools.ietf.org/html/rfc1738 _Uniform Resource Locators (URL), December 1994_
- https://tools.ietf.org/html/rfc2047 _MIME (Multipurpose Internet Mail Extensions) Part Three: Message Header Extensions for Non-ASCII Text, November 1996_
- https://tools.ietf.org/html/rfc2368 _The mailto URL scheme, July 1998_
- https://tools.ietf.org/html/rfc3696 _Application Techniques for Checking and Transformation of Names, 2004_
- https://tools.ietf.org/html/rfc5322 _Internet Message Format, October 2008_
- https://tools.ietf.org/html/rfc5233 _Sieve Email Filtering: Subaddress Extension, 2008_
- https://tools.ietf.org/html/rfc6068 _The 'mailto:' URI scheme, October 2010_
- https://tools.ietf.org/html/rfc6532 _Internationalized Email Headers, 2012_
- https://tools.ietf.org/html/rfc6854 _Update to Internet Message Format to Allow Group Syntax in the "From:" and "Sender:" Header Fields, March 2013_
- https://www.linuxjournal.com/article/9585 _Validate an E-Mail Address with PHP, the Right Way by Douglas Lovell on June 1, 2007_
