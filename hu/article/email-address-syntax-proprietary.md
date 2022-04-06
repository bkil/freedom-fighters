# Email címek szintaxisának ellenőrzése zárt oldalakon

## Bevezetés

A koncepció, hogy amikor a kéretlen levelektől minél védettebb címet szeretnénk létrehozni, érdemes tudnunk, hogy a különféle szolgáltatók elfogadnák-e, illetve a különféle címaratók mennyire könnyen felfedeznék fel.

Érdemes megjegyezni, hogy az itt szereplő példákat már csak azért sem szabad átvenni, mivel azok többsége mind logikailag, mind a szabványok tekintetében hibásak.

## Szolgáltatók

### KH KGFB

`^([a-zA-Z0-9_.-]|\\+)+@([a-zA-Z0-9_-])+(\\.([a-zA-Z0-9_-])+)?\\.([a-zA-Z0-9])+$`

### Gmail regisztráció

* https://support.google.com/mail/answer/9211434?hl=en

> [0-9a-z.]{6,30}
> Usernames cannot contain an ampersand (&), equals sign (=), underscore (_), apostrophe ('), dash (-), plus sign (+), comma (,), brackets (<,>),

TODO:

* ??? `[!#$%*/?^`{|}~]`
* ??? `[\\]`

### Gmail fogadás

Sikertelen a fogadás ha ezt tartalmazza: `%`, `!`

Ekvivalencia:

```
a.b.c.d+.*?#~}$`|'{&/=^_-@GmaIl.cOm
"a.b.c.d+.*?#~}$`|'{&/=^_-"@GmaIl.cOm
@googlemail.com
@gmail.de
@gmail.fr
@gmail.dk
@gmail.co
@gmail.com.br
@gmail.cm
...
```

## Komdat

```
/^(?=.{1,254}$)(?=.{1,64}@)[-!#$%&'*+\/0-9=?A-Z^_`a-z{|}~]+(\.[-!#$%&'*+\/0-9=?A-Z^_`a-z{|}~]+)*@[A-Za-z0-9]([A-Za-z0-9-]{0,61}[A-Za-z0-9])?(\.[A-Za-z0-9]([A-Za-z0-9-]{0,61}[A-Za-z0-9])?)*$/
```

## Szókereső

- grep, Java, JavaScript, PCRE:

`\w` (Unicode) = `[_[:alnum:]]` = `[_0-9A-Za-z]`

## Címaratók

Harvesterek

### PHP címarató

```
$html ='<div><a href="mailto:test@live.com">test</a></div>';

$r = '`\<a([^>]+)href\=\"mailto\:([^">]+)\"([^>]*)\>`ism';
preg_match_all($r, $html, $matches, PREG_SET_ORDER);

$r = '`\<a([^>]+)href\=\"mailto\:([^">]+)\"([^>]*)\>(.*?)\<\/a\>`ism';
preg_match_all($r,$html, $matches, PREG_SET_ORDER);
var_dump($matches);
```

### GoogleTagManager.com

`gtm.js`:

```
\b[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}\b
\b[A-Z0-9._%+-]+@(?:[A-Z0-9-]+\.)+[A-Z]{2,4}\b
[A-Z0-9._%-]+@[A-Z0-9._%-]+\.[A-Z]{2,4}
^[A-Z0-9._%-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$
^[A-Z0-9._%+-]{1,64}@(?:[A-Z0-9-]{1,63}\.){1,125}[A-Z]{2,63}$
```

### Egyéb címarató ötletek

`grep -E -o "\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,6}\b" test.html`

`/(mailto:)(.+)(\")/`

`~<mailto(.*?)>~`

## Validációs ötletek

### Gmail validáció

`lcs_client_bin.js`:

`/^(?:([^:/?#.]+):)?(?:\/\/(?:([^\\/?#]*)@)?([^\\/?#]*?)(?::([0-9]+))?(?=[\\/?#]|$))?([^?#]+)?(?:\?([^#]*))?(?:#([\s\S]*))?$/`

`m=a.js`:

`/(?:^|[-+%|!~=/\\?@"'(){}[\]<>*.;\s#])(?:from:|to:|)\(?([+a-zA-Z0-9_.][+a-zA-Z0-9_.-]*@(?:[a-zA-Z0-9-]+\.)+[a-zA-Z0-9]{2,6})\)?(?=$|[-+%|!~=/\\?@"'(){}[\]<>*.;\s#])/g`

### EmailRegex

https://www.emailregex.com/

```
(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])
```

### Python validáció

`r"(^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$)"`

### JavaScript validáció

`/^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/`

### PHP validáció

`/^(?!(?:(?:\x22?\x5C[\x00-\x7E]\x22?)|(?:\x22?[^\x5C\x22]\x22?)){255,})(?!(?:(?:\x22?\x5C[\x00-\x7E]\x22?)|(?:\x22?[^\x5C\x22]\x22?)){65,}@)(?:(?:[\x21\x23-\x27\x2A\x2B\x2D\x2F-\x39\x3D\x3F\x5E-\x7E]+)|(?:\x22(?:[\x01-\x08\x0B\x0C\x0E-\x1F\x21\x23-\x5B\x5D-\x7F]|(?:\x5C[\x00-\x7F]))*\x22))(?:\.(?:(?:[\x21\x23-\x27\x2A\x2B\x2D\x2F-\x39\x3D\x3F\x5E-\x7E]+)|(?:\x22(?:[\x01-\x08\x0B\x0C\x0E-\x1F\x21\x23-\x5B\x5D-\x7F]|(?:\x5C[\x00-\x7F]))*\x22)))*@(?:(?:(?!.*[^.]{64,})(?:(?:(?:xn--)?[a-z0-9]+(?:-[a-z0-9]+)*\.){1,126}){1,}(?:(?:[a-z][a-z0-9]*)|(?:(?:xn--)[a-z0-9]+))(?:-[a-z0-9]+)*)|(?:\[(?:(?:IPv6:(?:(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){7})|(?:(?!(?:.*[a-f0-9][:\]]){7,})(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,5})?::(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,5})?)))|(?:(?:IPv6:(?:(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){5}:)|(?:(?!(?:.*[a-f0-9]:){5,})(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,3})?::(?:[a-f0-9]{1,4}(?::[a-f0-9]{1,4}){0,3}:)?)))?(?:(?:25[0-5])|(?:2[0-4][0-9])|(?:1[0-9]{2})|(?:[1-9]?[0-9]))(?:\.(?:(?:25[0-5])|(?:2[0-4][0-9])|(?:1[0-9]{2})|(?:[1-9]?[0-9]))){3}))\]))$/iD`

### Perl validáció

```
/(?(DEFINE)(?<address>(?&mailbox) | (?&group)) (? (?&name_addr) | (?&addr_spec)) (? (?&display_name)? (?&angle_addr)) (? (?&CFWS)? < (?&addr_spec) > (?&CFWS)?) (? (?&display_name) : (?:(?&mailbox_list) | (?&CFWS))? ; (?&CFWS)?) (? (?&phrase)) (? (?&mailbox) (?: , (?&mailbox))*) (? (?&local_part) \@ (?&domain)) (? (?&dot_atom) | (?&quoted_string)) (? (?&dot_atom) | (?&domain_literal)) (? (?&CFWS)? \[ (?: (?&FWS)? (?&dcontent))* (?&FWS)? \] (?&CFWS)?) (? (?&dtext) | (?&quoted_pair)) (? (?&NO_WS_CTL) | [\x21-\x5a\x5e-\x7e]) (? (?&ALPHA) | (?&DIGIT) | [!#\$%&'*+-/=?^_`{|}~]) (? (?&CFWS)? (?&atext)+ (?&CFWS)?) (? (?&CFWS)? (?&dot_atom_text) (?&CFWS)?) (? (?&atext)+ (?: \. (?&atext)+)*) (? [\x01-\x09\x0b\x0c\x0e-\x7f]) (? \\ (?&text)) (? (?&NO_WS_CTL) | [\x21\x23-\x5b\x5d-\x7e]) (? (?&qtext) | (?&quoted_pair)) (? (?&CFWS)? (?&DQUOTE) (?:(?&FWS)? (?&qcontent))* (?&FWS)? (?&DQUOTE) (?&CFWS)?) (? (?&atom) | (?&quoted_string)) (? (?&word)+) # Folding white space (? (?: (?&WSP)* (?&CRLF))? (?&WSP)+) (? (?&NO_WS_CTL) | [\x21-\x27\x2a-\x5b\x5d-\x7e]) (? (?&ctext) | (?&quoted_pair) | (?&comment)) (? \( (?: (?&FWS)? (?&ccontent))* (?&FWS)? \) ) (? (?: (?&FWS)? (?&comment))* (?: (?:(?&FWS)? (?&comment)) | (?&FWS))) # No whitespace control (? [\x01-\x08\x0b\x0c\x0e-\x1f\x7f]) (? [A-Za-z]) (? [0-9]) (? \x0d \x0a) (? ") (? [\x20\x09]) ) (?&address)/x</address>
```

### Java validáció

```
(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])
```

### Ruby validáció

`/\A([\w+\-].?)+@[a-z\d\-]+(\.[a-z]+)*\.[a-z]+\z/i`

### ASP.NET RegularExpressionValidator

`^\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$`

### C# validáció

```
^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$
```

### VB.NET validáció

`^[_a-z0-9-]+(.[a-z0-9-]+)@[a-z0-9-]+(.[a-z0-9-]+)*(.[a-z]{2,4})$`

### SQL validáció

```
select email
 from table_name where
 patindex ('%[ &'',":;!+=\/()<>]%', email) > 0
 or patindex ('[@.-_]%', email) > 0
 or patindex ('%[@.-_]', email) > 0
 or email not like '%@%.%'
 or email like '%..%'
 or email like '%@%@%'
 or email like '%.@%' or email like '%@.%'
 or email like '%.cm' or email like '%.co'
 or email like '%.or' or email like '%.ne'
```

### JavaScript validáció

- https://stackoverflow.com/questions/46155/how-to-validate-an-email-address-in-javascript

```
/^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i
/^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
/^[^\s@]+@[^\s@]+$/
/^[^\s@]+@[^\s@]+\.[^\s@]+$/
```

### Regular-Expressions.info

- http://www.regular-expressions.info/email.html

```
/\A(?:[a-z0-9!#$%&'*+/=?^_‘{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_‘{|}~-]+)*
 |  "(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]
      |  \\[\x01-\x09\x0b\x0c\x0e-\x7f])*")
@ (?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?
  |  \[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}
       (?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:
          (?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]
          |  \\[\x01-\x09\x0b\x0c\x0e-\x7f])+)
     \])\z/
```

```
/^(?=[A-Z0-9][A-Z0-9@._%+-]{5,253}$)[A-Z0-9._%+-]{1,64}@
(?:(?=[A-Z0-9-]{1,63}\.)[A-Z0-9]+(?:-[A-Z0-9]+)*\.){1,8}[A-Z]{2,63}$/

/[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?/

/[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+(?:[A-Z]{2}|com|org|net|gov|mil|biz|info|mobi|name|aero|jobs|museum)\b/

```

### di.fm validáció

```
/^((([a-z]|\d|[!#\$%&'\*\+\-\/=\?\^_`{\|}~]|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])+(\.([a-z]|\d|[!#\$%&'\*\+\-\/=\?\^_`{\|}~]|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])+)*)|((\x22)((((\x20|\x09)*(\x0d\x0a))?(\x20|\x09)+)?(([\x01-\x08\x0b\x0c\x0e-\x1f\x7f]|\x21|[\x23-\x5b]|[\x5d-\x7e]|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])|(\\([\x01-\x09\x0b\x0c\x0d-\x7f]|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF]))))*(((\x20|\x09)*(\x0d\x0a))?(\x20|\x09)+)?(\x22)))@((([a-z]|\d|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])|(([a-z]|\d|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])([a-z]|\d|-|\.|_|~|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])*([a-z]|\d|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])))\.)+(([a-z]|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])|(([a-z]|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])([a-z]|\d|-|\.|_|~|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])*([a-z]|[\u00A0-\uD7FF\uF900-\uFDCF\uFDF0-\uFFEF])))$/i
```

### tawk.to validáció

`app.js`:

`/^((mailto:){0,1}[a-zA-Z0-9_\.\-\+])+@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]+)$/`

```
/^(?:[\w!#\$%&'\*\+\-\/=\?\^`\{\|\}~]+\.)*[\w!#\$%&'\*\+\-\/=\?\^`\{\|\}~]+@\
(?:(?:(?:[a-zA-Z0-9](?:[a-zA-Z0-9\-](?!\.)){0,61}[a-zA-Z0-9]?\.)+\
[a-zA-Z0-9](?:[a-zA-Z0-9\-](?!$)){0,61}[a-zA-Z0-9]?)|\
(?:\[(?:(?:[01]?\d{1,2}|2[0-4]\d|25[0-5])\.){3}(?:[01]?\d{1,2}|2[0-4]\d|25[0-5])\]))$/i
```

### Egyéb validációs ötletek

`[A-Z0-9a-z._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,64}`

- https://pastebin.com/LTRTwPV6

`/^([A-Za-z0-9_-.])+@([A-Za-z0-9_-.])+.([A-Za-z]{2,4})$/`

`/b[A-Z0-9._%+-]+@[A-Z0-9.-]+.[A-Z]{2,6}b/i`

- https://pastebin.com/hYppdraa

`/^([a-zA-Z0-9_.+-])+@(([a-zA-Z0-9-])+.)+([a-zA-Z0-9]{2,4})+$/`

`/^([\w-.]+@([\w-]+.)+[\w-]{2,4})?$/`

- https://stackoverflow.com/questions/66729962/sed-to-remove-proper-email-addresses-from-file

```
/[A-Za-z0-9][A-Za-z0-9._%+-]+@[A-Za-z0-9][A-Za-z0-9.-]+\.[A-Za-z]{2,3}/
```

- https://stackoverflow.com/questions/201323/how-can-i-validate-an-email-address-using-a-regular-expression

```
/^\S+@\S+\.\S+$/
/.+@[^@]+\.[^@]{2,}$/
/^[^@]+@[^@]+\.[^@]{2}[^@]*$/
/^[^@]+@[^@]+\.[^@]{2,4}$/
/^[^\s@]+@[^\s@]+\.[^\s@]{2,}$/
/^[^@]+@[^@]+\.[a-z-A-Z]{2,4}$/
/^[^\s@]+@([^\s@.,]+\.)+[^\s@.,]{2,}$/
/([-!#-'*+/-9=?A-Z^-~]+(\.[-!#-'*+/-9=?A-Z^-~]+)*|"([]!#-[^-~ \t]|(\\[\t -~]))+")@[0-9A-Za-z]([0-9A-Za-z-]{0,61}[0-9A-Za-z])?(\.[0-9A-Za-z]([0-9A-Za-z-]{0,61}[0-9A-Za-z])?)+/
/([-!#-'*+/-9=?A-Z^-~]+(\.[-!#-'*+/-9=?A-Z^-~]+)*|"([]!#-[^-~ \t]|(\\[\t -~]))+")@([-!#-'*+/-9=?A-Z^-~]+(\.[-!#-'*+/-9=?A-Z^-~]+)*|\[[\t -Z^-~]*])/
/([-!#-'*+/-9=?A-Z^-~]+(\.[-!#-'*+/-9=?A-Z^-~]+)*|"([]!#-[^-~ \t]|(\\[\t -~]))+")@([0-9A-Za-z]([0-9A-Za-z-]{0,61}[0-9A-Za-z])?\.)*(net|org|com|info|etc)/
/^([-!#-\'*+\/-9=?A-Z^-~]{1,64}(\.[-!#-\'*+\/-9=?A-Z^-~]{1,64})*|"([]!#-[^-~ \t]|(\\[\t -~]))+")@[0-9A-Za-z]([0-9A-Za-z-]{0,61}[0-9A-Za-z])?(\.[0-9A-Za-z]([0-9A-Za-z-]{0,61}[0-9A-Za-z])?)+$/
/^([\w\!\#$\%\&\'\*\+\-\/\=\?\^\`{\|\}\~]+\.)*[\w\!\#$\%\&\'\*\+\-\/\=\?\^\`{\|\}\~]+@((((([a-z0-9]{1}[a-z0-9\-]{0,62}[a-z0-9]{1})|[a-z])\.)+[a-z]{2,6})|(\d{1,3}\.){3}\d{1,3}(\:\d{1,5})?)$/i
/^([^.@]+)(\.[^.@]+)*@([^.@]+\.)+([^.@]+)$/
```
