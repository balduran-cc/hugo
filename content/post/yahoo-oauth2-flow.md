+++
author = "Balduran Chang"
date = 2015-06-08T23:09:52Z
description = ""
draft = true
slug = "yahoo-oauth2-flow"
title = "Yahoo oauth2 flow"

+++


#yahoo oauth2
##work flow
https://developer.yahoo.com/oauth2/guide/flows_authcode/

server side要拉user資料，一定是通過explicit grant flow，如果是client side app才會是走implicit grant flow。

### get developer credential
拿到每個developer自己一組key/secret。

### redirect user to oauth endpoint
developer key為一組參數，將user轉入oauth endpoint

### Yahoo redirect user back to developer app
user 允許app取得個人資料後，yahpp endpoing轉回developer app，同時提供authorization code供之後使用

### developer app use authorization code to get token
authorization code 拿到之後，developer可以從token endpoint繼續拿到
1. access_token
2. refresh_token

### use access token to poke API
access token 過期前都可以用，過期後就拿refresh token取得新token

## trouble shooting
{"error":"invalid_grant"}
redirect_url必須一樣。


ref:
1. https://developer.linkedin.com/docs/signin-with-linkedin#images
2. https://dev.twitter.com/web/sign-in/desktop-browser
3. https://dev.twitter.com/web/sign-in/implementing
4. http://app.balduran.cc/index.php

