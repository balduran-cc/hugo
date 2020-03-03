+++
author = "Balduran Chang"
categories = ["API", "benchmark", "endpoint"]
date = 2014-07-21T07:28:00Z
description = ""
draft = false
slug = "simple-benchmark-http-api"
tags = ["API", "benchmark", "endpoint"]
title = "simple benchmark http API."

+++


1. use Apache Benchmark

ab -n 100000 “$URL”

ab -n 3 “http://google.com/”  
Server Software: gws  
Server Hostname: google.com  
Server Port: 80

Document Path: /  
Document Length: 219 bytes

Concurrency Level: 1  
Time taken for tests: 0.471 seconds  
Complete requests: 3  
Failed requests: 0  
Broken pipe errors: 0  
Non-2xx responses: 3  
Total transferred: 1707 bytes  
HTML transferred: 657 bytes  
Requests per second: 6.37 [#/sec] (mean)  
Time per request: 157.00 [ms] (mean)  
Time per request: 157.00 [ms] (mean, across all concurrent requests)  
Transfer rate: 3.62 [Kbytes/sec] received

Connnection Times (ms)  
min mean[+/-sd] median max  
Connect: 74 75 1.0 75 76  
Processing: 83 82 1.0 82 83  
Waiting: 79 81 1.6 82 83  
Total: 154 157 2.0 158 159

Percentage of the requests served within a certain time (ms)  
50% 157  
66% 157  
75% 159  
80% 159  
90% 159  
95% 159  
98% 159  
99% 159  
100% 159 (last request)

2. Curl  
curl -s -w “%{time_total}n” -o /dev/null “$URL”  
and use for loop  
for i in {1..3}; do curl -s -w “%{time_total}n” -o /dev/null “$URL”; done

3. <span style="background-color: white; color: #333333; font-family: 'Helvetica Neue Light', HelveticaNeue-Light, 'Helvetica Neue', Helvetica, Arial, sans-serif; font-size: 14px; line-height: 19.600000381469727px;">iperf</span>  
<span style="background-color: white; color: #333333; font-family: 'Helvetica Neue Light', HelveticaNeue-Light, 'Helvetica Neue', Helvetica, Arial, sans-serif; font-size: 14px; line-height: 19.600000381469727px;">see </span><span style="color: #333333; font-family: Helvetica Neue Light, HelveticaNeue-Light, Helvetica Neue, Helvetica, Arial, sans-serif;"><span style="font-size: 14px; line-height: 19.600000381469727px;">[https://iperf.fr/](https://iperf.fr/)</span></span>  
<span style="color: #333333; font-family: Helvetica Neue Light, HelveticaNeue-Light, Helvetica Neue, Helvetica, Arial, sans-serif;"><span style="font-size: 14px; line-height: 19.600000381469727px;">  
</span></span><span style="color: #333333; font-family: Helvetica Neue Light, HelveticaNeue-Light, Helvetica Neue, Helvetica, Arial, sans-serif;"><span style="font-size: 14px; line-height: 19.600000381469727px;">If the API query contain variable, server side might implement cache mechanism, hit the same API url might not reflect truly situation. </span></span>

