+++
title = "Ditching GSuite"
description = ""
date = "2016-12-23T16:07:48-05:00"

+++

I've been a long supporter of Google Services; Practically it's wired into our online identity. And the nature of your Google account, it touches everything now. It builds value when it can aggregate all the parts of your identity across their properties. Just check out your [Google MyActivities](https://myactivity.google.com/myactivity), they have information on all your interaction with all of Google's services across your devices. The difficulty of sticking with GSuite means splitting your data between different profiles.

![Google Data Policy](https://lh3.googleusercontent.com/0GzIv4Pa75u8-0wIneBK8st_NeQ8zq06z0qZfPnrrpII_4LC8IrPof0UjcsO3p-js3mpASbNmj4CrGC9I2KR6kAwgcnKpa6ydDyzy_CgwMKKzAsMbPMMHHzLWo8PxYVM_ToYTcY437b3CW1u7MRxIY7rDEKMq-hwWhCWTnWAw_zQrCChbJAkq97GzIC26olZrdCzYnRPqc5I4YDK7UAg_kzX3E9Hm7K1jZ5Zv52_hNgapxoMmzkEutTgSMcLGhtACelgZpdwJKI0Ggna3u2neFuSCr7Tf8ploZLL9J7cCxfgJzTJsKdFNyepUeAPdKCRcm7TEt4j6hiBJZs-sfWChgMBU1n7rdcADkVF2gE-VVDybEiCvpcTuzvuY3GkYzFHKBe1ljyBCseKDMEGxeVf-RIfYuMIYj4p5cO9BaD6vRuD0iuVBmWs-Dqe2cCt_Xu0oiWPOeCYYH3aDNxXehF8t_ZFIY4X_pvXY7pbk-mMn6VK-FN5CarEHMdO4qzqECCQOF1YPKZ-D_RaIZatfM2whEjC3Wu3zKyDJAzNfwBSn2PqbF4PwSIx3fTPJOchum3FpjVC5mBLqApLxMgm4REEiv-fvALNPcE-roiEB6ZG3z6UBfmHzGmARA=w620-h465-no)
_All your data in one place..._

 My sole vain reason of adopting GSuite was to set up a named domain email for `stanley[at]stanzheng.com`. However, after a month and some change, switching and juggling between two existing google profiles was a tiresome and frustrating experience. Whether that was going to YouTube and have to resub to different channels or having entirely different Google Photos sets. After a while, you build a _single Google identity_ and it's hard to migrate off of it, even internally.

Moving to Zoho
---
Namely, my only usage for adopting GSuite was to do email reliably. Many of the businesses offerings for GSuite compared to normal Google services was _not enough_ of a value proposition for me to continue paying a monthly subscription in addition further split my data.

After learning a painful fun amount about [DKIM and SPF records](https://mandrill.zendesk.com/hc/en-us/articles/205582267-About-SPF-and-DKIM), I ditched my dedicated email and GSuite with it. I switched to [Zoho](http://www.zoho.com/), a credible mail server company that offers pricing for small businesses but offers domain email for one account for free. Perfect! All that I needed actually, after forwarding and setting up SMTP everything became normal.

 GSuite also provides some good tools to migrate import/export your content and definitely use them! I got bit when the content was still _owned_ by my GSuite account but shared into my migrated account which caused everything to get __deleted__. Lucky after the panic mode subsided, I was able to load an [offline browser profile](https://support.google.com/docs/answer/6388102?co=GENIE.Platform%3DDesktop&hl=en) and sneakily load all my offline backed up documents from my profile from local.

Although..
--
If you work or go to university, 9/10 of times you'll have a GSuite / (Google for Work/School) account. It definitely makes sense for the administration for midsized companies. But if you're just looking for a simple way to do domain email only, adopting GSuite might be an overkill.
