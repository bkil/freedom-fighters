# Email account properties and limitations

Sending limits where not otherwise specified over SMTP or the API suitable to be used through a FOSS client application.

## Freemium

### Gmail.com before Workspace

These limits do not seem to apply any more as of 2024

* max. 500 recipient/body
* max. 500 recipient/interval
* max. 60 received/minute
* interval: 24h
* https://support.google.com/mail/answer/22839?hl=en

### Gmail.com in Google Workspace

These limits come from an error message received in 2024 relating to a free personal account:

* max. 100 recipient/body
* max. 2000 recipient/interval
* interval: 24h
* https://support.google.com/a/answer/166852

> 2024-01-07
> Error
> Permanent SMTP error: permanent:
> 5.4.5 Daily user sending limit exceeded. For more information on Gmail;
> 5.4.5 sending limits go to;
> 5.4.5 https://support.google.com/a/answer/166852
> -gsmtp

### Mailbox.org

* max. 1k-10k/interval
* interval: day
* https://kb.mailbox.org/en/private/e-mail-article/is-there-a-limit-on-the-amount-of-e-mails-that-i-can-send-from-my-account

### Mail.de

* max. 50 recipient/interval
* interval: day
* https://mail.de/en/products/

### Mail.Ru

* max. 10k-50M recipient/interval depending on spam report rate
* interval: calendar month
* https://help.mail.ru/enmail-help/rules/general

### Microsoft

* max. 500 recipient/body
* max. 5000 recipient/interval
* max. 1000 new contact/day
* interval: day
* https://support.microsoft.com/en-us/office/sending-limits-in-outlook-com-279ee200-594c-40f0-9ec8-bb6af7735c2e

### Yandex.Mail

* max. 35 recipient/body
* max. 500 recipient/interval
* interval: 24h
* https://yandex.com/support/mail/web/letter/create/send-many-letters.html

### Zoho Lite

* max. 50 recipient/interval
* interval: day of 00:00-23:59 local time
* https://help.zoho.com/portal/en/kb/crm/connect-with-customers/email/articles/email-limits#Limits_for_Individual_Emails

## Donation-based

## Paid

### Apple iCloud

* max. 1000 body/interval
* max. 500 recipient/body
* max. 1000 unique contact/interval
* interval: day
* https://support.apple.com/en-us/HT202305

### Fastmail

* max. recipient 4000/24h, 2000/h, 1000/10m
* max. received: 60/min, 4000/24h, <50% per peer
* interval: 24h
* https://www.fastmail.help/hc/en-us/articles/1500000277382-Account-limits

### Google Workspace

* max. 100 recipient/body
* max. 10k recipient/interval (3000 external)
* max. 3000 unique contact/interval (2000 external)
* max. 60 received/minute
* interval: 24h
* https://support.google.com/a/answer/166852#imap&zippy=%2Cfree-trial-account-limits
* https://support.google.com/a/answer/1366776

### ik.me

* max. 10 recipient/body
* max. 100 recipient/interval
* interval: 24h
* https://www.infomaniak.com/en/support/faq/search?q=rate+limits

### NameCheap

Per domain sending limit:

* EasyWP: 50/day
* Stellar, Nebula Reseller, Private Email trial: 50/hour
* Stellar Plus, Galaxy Expert, Universe Pro Reseller, Value, Professional, Reseller: 200/hour
* Ultimate, Starter Email, Private Email, Business Email, Business Office Email: 500/hour
* Business SSD, Pro Email: 1000/hour
* Ultimate Email: 1500/hour
* Stellar Business: 10000/hour
* VPS, Dedicated Servers: unlimited
* https://www.namecheap.com/support/knowledgebase/article.aspx/133/22/do-you-have-any-restrictions-on-sending-out-emails/

### Posteo

* max. recipient 500/h, 1000/day
* interval: day
* https://posteo.de/en/site/terms

## References

* https://github.com/deltachat/provider-db/tree/master/_providers
* https://github.com/deltachat/eppdperf/blob/main/results/e-mail_provider_comparison.ods
* https://github.com/deltachat/deltachat-pages/blob/master/assets/blog/eppd-comparison-final.pdf
