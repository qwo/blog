+++
title = "RC 8: Alternative to GSuite: Named domains with Zoho"
description = ""
tags = ["recurse"]
date = "2017-01-11T11:43:03-05:00"

+++

## Edit

This method isn't possible anymore as email forwarding requires premium to forward email but sending email possible.

To use send from GMAIL from Zoho configure the below settings

1. Under [Gmail -> Settings](https://mail.google.com/mail/u/0/#settings/accounts), Click "add a mail account" 
2. Select the email provider with `smtp.zoho.com`  over port `465` using your confirmed email. This will use SSL over email. 
3. If you use SSO using another provider, you will have to generate a one time password to use from [https://accounts.zoho.com/u/h#security/app_password](https://accounts.zoho.com/u/h#security/app_password).


I've been a long supporter of Google Services; Practically it's wired into our online identity. And the nature of your Google account, it touches everything now. It builds value when it can aggregate all the parts of your identity across their properties. Just check out your [Google MyActivities](https://myactivity.google.com/myactivity), they have information on all your interaction with all of Google's services across your devices. The difficulty of sticking with GSuite means splitting your data between different profiles.

![Google Data Policy](https://lh3.googleusercontent.com/7rXUaoonkz2FCWwYwUl6-K6kn-QNMqjwlnOXlA1KeIVO4Og2afcQ0dxl2UgdFlySbTxmRcdiMe0FUm9axj8jiuDbf1ZE6ZY_BMvfzcYTBTmg6dP8eGLMG80VGlw8ka5AyhUxWIiox6B20nC1bjP1pIFM0iNSeqJDFcmmfFYqDuiFXIN_jruFSAWAkvyFeLMuikhty7MTWIgq-xipb0STjGOMrXJg0j8tKZfD2ip-lbBetH-Mb5f_u6GXNbofJHf6fmOjOloe6uclSzcgVa3Joc2NBvn5bQpB89AzFKUCJ-hVxlOcP_xHXw_g3WE-fh1SJfuwQlP812uvuZ9ZmkRzw7KIEAmgct97r8n8IuwrT3sUISP9ulFO4StTD-d8uAO6V-aQ_ZN9IBJzLvOzrrfmmo6PuKw2SHqoYLzoRPhVFyqWwMR8LmL6TlcG4TumfrJ2dyb7yQEp7brTBHbv6EpGPX1Glw6WJ6OkX18kb63XlnJxaMeaG7Z6PQnGIY_WGrwT0UzyvpLGvcVhzt1NBKcbW1zNL3-onOx6c1-86KcuyftxVrvxYWaRlJA3juECTS8xS0y1cQ4fA_wIAbVE39gfXSycKx8RZAhIigcBXc6WnYwlL7kXubCcCrJjOJRKphaZpnsvqCGnWjGdBaXS7Jy5cwnmXDkyqz25Z3B1nXBM9Es=w620-h465-no)
<div class="caption">_All your data in one place..._</div>

 My sole vain reason of adopting GSuite was to set up a named domain email for `stanley[at]stanzheng.com`. However, after a month and some change, switching and juggling between two existing google profiles was a tiresome and frustrating experience. Whether that was going to YouTube and have to resub to different channels or having entirely different Google Photos sets. After a while, you build a _single Google identity_ and it's hard to migrate off of it, even internally.

Moving to Zoho
---
Namely, my only usage for adopting GSuite was to do email reliably. Many of the businesses offerings for GSuite compared to normal Google services was _not enough_ of a value proposition for me to continue paying a monthly subscription in addition further split my data.

After learning a painful fun amount about [DKIM and SPF records](https://mandrill.zendesk.com/hc/en-us/articles/205582267-About-SPF-and-DKIM), I ditched my dedicated email and GSuite with it. I switched to [Zoho](http://www.zoho.com/), a credible mail server company that offers pricing for small businesses but offers domain email for one account for free. Perfect! All that I needed actually, after forwarding and setting up SMTP everything became normal.

 GSuite also provides some good tools to migrate import/export your content and definitely use them! I got bit when the content was still _owned_ by my GSuite account but shared into my migrated account which caused everything to get __deleted__. Lucky after the panic mode subsided, I was able to load an [offline browser profile](https://support.google.com/docs/answer/6388102?co=GENIE.Platform%3DDesktop&hl=en) and sneakily load all my offline backed up documents from my profile from local.

Although..
--
If you work or go to university, 9/10 of times you'll have a GSuite / (Google for Work/School) account. It definitely makes sense for the administration for midsized companies. But if you're just looking for a simple way to do domain email only, adopting GSuite might be an overkill.
