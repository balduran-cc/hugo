+++
author = "Balduran Chang"
date = 2015-07-14T04:23:19Z
description = ""
draft = true
slug = "free"
title = "Free stock price data on WEB"

+++


##Yahoo YQL interface
https://finance-yql.media.yahoo.com/v7/finance/chart/VTI?period2=1436872781&period1=1436527181&interval=1m&indicators=quote&includeTimestamps=true&includePrePost=true&events=div%7Csplit%7Cearn&corsDomain=finance.yahoo.com

JSON format

## Yahoo finance API
Format : http://chartapi.finance.yahoo.com/instrument/1.0/[TICKER]/chartdata;type=quote;range=1d/csv

Example: http://chartapi.finance.yahoo.com/instrument/1.0/GOOG/chartdata;type=quote;range=1d/csv

[TICKER]: This is the ticker symbol of the security



## Google finance API
http://www.google.com/finance/getprices?i=60&p=1d&f=d,o,h,l,c,v&df=cpct&q=VTI

The URL format is: http://www.google.com/finance/getprices?i=[PERIOD]&p=[DAYS]d&f=d,o,h,l,c,v&df=cpct&q=[TICKER]
[PERIOD]: Interval or frequency in seconds
[TICKER]: This is the ticker symbol of the stock

f fields
d,o,h,l,c,v
DATE,CLOSE,HIGH,LOW,OPEN,VOLUME

## NetFonds
free data from http://www.netfonds.no/quotes/paperdump.php?paper=VTI.A

http://www.netfonds.no/quotes/tradedump.php?date=20150713&paper=VTI.A&csv_format=txt
http://www.netfonds.no/quotes/tradedump.php?date=20150713&paper=VTI.A&csv_format=csv

http://www.netfonds.no/quotes/posdump.php?date=20150713&paper=VTI.A&csv_format=txt


Type the ticker symbol next to "paper=" parameter followed by the exchange code:
NASDAQ: O
NYSE: N
AMEX: A

http://www.netfonds.no/quotes/paperhistory.php?paper=VTI.A&csv_format=csv


## stooq 
http://stooq.com/db/h/
http://stooq.com/db/

## quantquote
https://quantquote.com/historical-stock-data



## import JSON in google spreadsheet
1. need using script editor
2. save script as ImportJSON.gs
3. use that function by `=ImportJSON()`

https://gist.github.com/paulgambill/cacd19da95a1421d3164

https://github.com/fastfedora/google-docs/blob/master/scripts/ImportJSON/Code.gs

