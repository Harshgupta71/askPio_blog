---
layout: post
title:  "How to configure the TLS and resolve errors related to this on Azure webApp!"
author: sal
categories: [ ]
image: 
---

Today, we are going to discuss and see how to configure the TLS and resolve errors related to this. There are different versions of TLS. 
Protocol	Published
TLS 1.0	1999
TLS 1.1	2006
TLS 1.2	2008
TLS 1.3	2018

First, you should know what TLS is, for this, you can refer the below two URLs.

1.	https://en.wikipedia.org/wiki/Transport_Layer_Security
2.	https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/

We must configure the right TLS on azure web app and on our security service (in my case I am using Cloudflare), if it is not configured properly then we will get the below error. For testing of app’s security, make sure you are using Internet Explorer or Microsoft Edge.

```
.my-link {
    This might be because the site uses outdated or unsafe TLS security settings. If this keeps happening, try contacting the website’s owner.;
}
```

![walking]({{ site.baseurl }}/assets/images/08142019/image1.png)
