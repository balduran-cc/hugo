+++
author = "Balduran Chang"
categories = ["javascript", "yui", "jquery"]
date = 2015-09-24T03:01:59Z
description = ""
draft = false
slug = "javascript-access-height-and-width"
tags = ["javascript", "yui", "jquery"]
title = "javascript 存取瀏覽器的寬高"

+++


# 瀏覽器的寬高

###[window] 
window 即為瀏覽器本身，瀏覽器的高度，有分兩種，包含工具列與不包含，當然包含工具列的值會比較大，只要不 resize，這個值是不會變的。

window.innerHeight 是不包含工具列的，比較常使用到，是瀏覽器的可視範圍。
window.outerHeight 則是包含的。

[window]: https://developer.mozilla.org/en-US/docs/Web/API/Window

## 網頁文件的寬高
###[document]
document 即為當前瀏覽的網頁，網頁可能很大，比瀏覽器視窗還大，因此 document 的寬高比 window 寬高還要大是正常現象，網頁內容的高度，取值用

* document.body.clientHeight
* document.documentElement.clientHeight
* document.documentElement.scrollHeight

三者等價，用document.body就好，不要用 document.height。
[document]: https://developer.mozilla.org/en-US/docs/Web/API/document

width 以此類推，不贅述。
## 頁面捲動距離
網頁開出來之後，初始捲動的值都是 0，往下滑動之後，Y 軸的值會增加，往右滑動，X 軸的值會增加。這個數值配合 window/document height，可以算出現在出現在使用者面前的頁面是整個網頁的哪一段，例如常見的一些功能是捲到頁面底端之後出現某些模組、按鈕、圖案，就需要用這數值判斷。

以 Y 軸 (垂直)為例

* [window.scrollY]
* window.pageYOffset
* document.defaultView.scrollY
* document.defaultView.pageYOffset

這些數字永遠一樣，統一使用 [window.scrollY] 就好。
[window.scrollY]: https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollY

[window.scrollTo] 則是可以用程式控制頁面捲動到定點，在 iOS 早期的版本，手機版頁面為了讓上方網址列在讀取完之後自動收起，都會用 `window.scrollTo(0, 1);` 讓瀏覽器以為使用者已經捲動頁面而自動收起網址，不過 mobile safari 已經沒有這樣的設計。

[window.scrollBy] 則是控制捲動的幅度，稍有不同。


[Window.scrollTo]: https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollTo
[window.scrollBy]: https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollBy

## useful framework
### [YUI]
YUI 有很多好用的 [utility][YUI DOM] function，使用 `Y.DOM` 就可以拿到寬高。
 
* Y.DOM.winHeight()
* Y.DOM.winWidth()
* Y.DOM.docHeight()
* Y.DOM.docWidth()

* Y.DOM.docScrollY()
 則是可以拿到現在頁面 Y軸(垂直)的捲動值 
* Y.DOM.docScrollX()
 可以拿到現在頁面 X軸(橫向)的捲動值


[YUI]: http://yuilibrary.com/
[YUI DOM]: http://yuilibrary.com/yui/docs/api/classes/DOM.html

### [jQuery]

jQuery 太有名了，應該沒有人不知道。用 [height()][height] 就可以拿到高度，[scrollTop] 則可以取的 Y軸(垂直)捲動值，Function Naming 滿直覺的。


* $(window).height();
* $(document).height();
* $(window).width();
* $(document).width();


* $(window).[scrollTop()][scrollTop] 可以拿到現在頁面 Y軸(垂直)的捲動值 
* $(window).[scrollLeft()][scrollLeft] 可以拿到現在頁面 X軸(橫向)的捲動值

[jQuery]: https://jquery.com/
[height]: http://api.jquery.com/height/
[scrollTop]: https://api.jquery.com/scrollTop/
[scrollLeft]: https://api.jquery.com/scrollLeft/

