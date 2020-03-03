+++
author = "Balduran Chang"
categories = ["cookie", "GAE", "python"]
date = 2009-08-25T06:23:40Z
description = ""
draft = false
slug = "e8a8ade5ae9agaee4b8ade59b9ee68789e6a899e9a0ade79a84cookie"
tags = ["cookie", "GAE", "python"]
title = "設定gae中回應標頭的cookie"

+++


ericsk在他的書「google應用服務引擎開發實戰」中P.78提到一個tip，self.request.cookies[‘name’]=’eric’可以讓responce回應時候自動送出set-cookie，可是我自己改了一下範例覺得有點詭異，當cookie不存在的時候直接用上面的程式碼設定cookie，responce並沒有回應對應的標頭啊。

按照[webob](http://pythonpaste.org/webob/reference.html#id5)的設計，應該有self.response.set_cookie(‘name’,’eric’)可以用，但是gae的[文件](http://code.google.com/intl/zh-TW/appengine/docs/python/tools/webapp/buildingtheresponse.html)裡是沒有提供這樣的函式呼叫，所以只能自己在回應標頭裡加入該有的字串，self.response.headers.add_header( ‘Set-Cookie’, ‘name=eric’)。

[參考discussion](http://groups.google.com/group/google-appengine/browse_thread/thread/6120f16c2db05f7e/e8262c5cb4d6685c?lnk=gst)

