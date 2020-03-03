+++
author = "Balduran Chang"
categories = ["doc", "mac", "MS", "odf", "office", "software"]
date = 2009-01-11T14:00:48Z
description = ""
draft = false
slug = "odf-and-open-xml"
tags = ["doc", "mac", "MS", "odf", "office", "software"]
title = "ODF and open XML"

+++


iWork 提供的 [iwork.com](http://view.iwork.com/) 這功能，讓我直覺想到了匹敵的微軟 office，因為兩者皆有單機軟體，再額外提供網頁空間作存取。

iwork 提供下載的檔案支援 iwork ’09, iwork ’08, PDF, doc, xls, ppt 等，是為了提供對 windows 平台的相容性，並且 [keynote](http://www.apple.com/iwork/keynote/) 09 和 keynote 08 的檔案格式不同，改成單一檔案的方式存檔。

微軟的 office 系列在 07 之後用自訂的 [open xml](http://en.wikipedia.org/wiki/Office_Open_XML) 格式，舊版程式可以加裝 add-in 來讀取，沒有 office 系列軟體的話可以安裝免費提供的 [viewer](http://www.microsoft.com/DOWNLOADS/results.aspx?pocId=&freetext=viewer&DisplayLang=en)，使用 [openoffice](http://www.openoffice.org/) 也是可以讀取，但是常常出錯。XD

[google doc](http://docs.google.com/) 倒是支援 doc, odt, xls, ods, ppt, odp，完全不支援 open XML 格式，想要使用的話要先用 convert 轉換。

讓 office 可以讀取 [ODF](http://en.wikipedia.org/wiki/OpenDocument) 格式的 add-in : [OpenXML/ODF Translator Add-in for Office](http://sourceforge.net/project/showfiles.php?group_id=169337&package_id=298780)，安裝之後可以在 office 處理 ODF 系列檔案，開啟 ODF 檔案也是先轉換成 openXML 再開啟，也可以將 ODF 轉存成 office 的格式。

如果照檔案的開放程度來看，mac 上的軟體好像比較獨斷。如果單純以觀看文件來看，PDF 已經是無庸置疑的共通格式。以檔案傳遞可編輯修改來看，ODF 和 open XML 還是沒有完結的一天，改天再來看用 HTML 解決這一切的方式。

