+++
author = "Balduran Chang"
date = 2015-03-14T23:18:00Z
description = ""
draft = true
slug = "webdriver-try-run"
title = "webdriver try run"

+++


用nodejs 操控 selenium做測試

1. mkdir webdriverio && cd webdriverio
1. curl -O http://selenium-release.storage.googleapis.com/2.45/selenium-server-standalone-2.45.0.jar
1. java -jar selenium-server-standalone-2.45.0.jar
1. visit selenium by `http://127.0.0.1:4444/wd/hub`

1. npm install webdriverio
1. write sample testing script.
1. `node test.js`

`
var webdriverio = require('webdriverio');
var options = {
    desiredCapabilities: {
        browserName: 'firefox'
    }
};
webdriverio
    .remote(options)
    .init()
    .url('http://www.google.com')
    .title(function(err, res) {
        console.log('Title was: ' + res.value);
    })
    .end();
`

用途
1. scrape web content
1. call browserstack to test
1. 與mocha, chai, jasmine, buster 等框架結合

source: https://github.com/webdriverio/webdriverio

