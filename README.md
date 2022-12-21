---
description: >-
  All you need to know to bootstrap a web page with a videoconference tool in
  it.
cover: .gitbook/assets/1516304704454.jpeg
coverY: 0
---

# Getting started with ApiRTC Embedded

ApiRTC Embedded enables you to quickly insert a video conferencing interface into any webpage.

In this tutorial, we are going to go through all the step to insert the embedded component into a web page.

### Prerequisite

* Get an ApiRTC active account on [http://cloud.apizee.com](http://cloud.apizee.com).
* Retrieve your api key at [https://cloud.apizee.com/enterprise/api](https://cloud.apizee.com/enterprise/api)
* Go on your cloud.apizee.com Dashboard and make sure your account has enough minutes of communication credited [https://cloud.apizee.com/dashboardapi](https://cloud.apizee.com/dashboardapi)

### Insert the ApiRTC Embedded component into a web page

The ApiRTC Embedded component should be inserted into an `<IFrame>` HTML tag pointing to a webpage instanciating a new video conference room.

The URL is composed of `https://izeeconf.com/join/`, ended by a random string pointing a conversation name.

In the exemple below, we use [https://izeeconf.com/join/fancy-mare](https://izeeconf.com/join/fancy-mare) as a target URL.&#x20;

{% code overflow="wrap" %}
```html
  <iframe style="width:100%; height:800px" src="https://izeeconf.com/join/fancy-mare" />
```
{% endcode %}

{% embed url="https://codepen.io/rvailleux/pen/PoaZYdb" %}
Most basic use of the ApiRTC Embedded
{% endembed %}

### Go further

* [​Display a specific conversation ​​ ](go-further/point-to-a-specific-conversation.md): this is instrumental if you want to actually talk to someone.
* [Activate or deactivate features](go-further/activate-and-deactivate-features.md) : make sure your users has all they need
* [Customize the look & feel ](go-further/customize-look-and-feel.md): colors, shapes, positions to make you feel at home
