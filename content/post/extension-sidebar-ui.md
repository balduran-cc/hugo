+++
author = "Balduran Chang"
categories = ["extension", "firefox", "chrome"]
date = 2018-07-04T23:10:52Z
description = ""
draft = false
slug = "extension-sidebar-ui"
tags = ["extension", "firefox", "chrome"]
title = "extension sidebar UI"

+++


有開發過 Firefox addon的開發人員應該知道有一種 [side bar UI](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/user_interface/Sidebars)會佔滿瀏覽器的左邊，通常對於一些 debugging tool來說這樣的介面很有幫助，可以一邊看頁面一邊看想要偵錯的資訊。

不過這樣的 UI 在 Chrome 是不存在的。

<iframe src="//www.slideshare.net/slideshow/embed_code/key/FaSA9sUY8aaZ9W?startSlide=4" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/balduran/introduction-of-chrome-extension-development" title="Introduction of chrome extension development" target="_blank">Introduction of chrome extension development</a> </strong> from <strong><a href="//www.slideshare.net/balduran" target="_blank">Balduran Chang</a></strong> </div>

最最最最接近的是 [devtools panels](https://developer.chrome.com/extensions/devtools_panels#method-ElementsPanel-createSidebarPane)，不過非程式開發人員一般來說是不會打開 devTools的。

[這份文件](https://docs.google.com/document/d/102hfWTM5cMl-95PyfGcn89YHDTffBMMumLUBOnxLp0A/preview) 指出了在 2015的時候，chromium project (chrome的開源計畫) 曾[有過討論](https://bugs.chromium.org/p/chromium/issues/detail?id=477424)要加入 sidebar UI，但後來被標為 won't fix，也就無望了。如果 Sidebar UI有支援的話，那像 [octotree](https://github.com/buunguyen/octotree) 這類的 extension developer 就不用自己塞 html進 webpage了。

