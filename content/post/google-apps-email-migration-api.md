+++
author = "Balduran Chang"
categories = ["API", "app", "google", "mail"]
date = 2007-11-19T07:03:37Z
description = ""
draft = false
slug = "google-apps-email-migration-api"
tags = ["API", "app", "google", "mail"]
title = "Google Apps Email Migration API"

+++


Google Apps Email 釋出 [Migration API](http://code.google.com/apis/apps/email_migration/developers_guide_protocol.html)，可從任何地方搬移 e-mail 到 Google Apps Email，為什麼不靠 IMAP 系統呢？是考量到使用者可能沒有 IMAP 伺服器或是安全因素必須採用主動 push migration 的方式，因此提供 API 讓應用程式使用。

例如 LimitNone 的 [gMove](http://www.limitnone.com/products.php?p=gmove) 就是這樣的一套工具，可以搬移 Microsoft Outlook calendar (行事曆), email, contacts (聯絡人) and tasks 到 Gmail 或是 google app。

google 力推 app，想讓一般企業也使用，但是我覺得 app 是做佛心來的，學校、慈善團體應該是獲益最大的，而一般中小企業可能沒有迫切需要有自己的 domain name 和 mail address，而夠大的企業又要保密，怎麼可能讓 google 代管呢？

所以讓使用者自己獻上 e-mail 內容 (誤)。

