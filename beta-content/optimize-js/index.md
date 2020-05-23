---
title: What is Optimize.js
date: 2020-05-19
description: Optimize
---

Ship less javascript to the browser
https://nolanlawson.github.io/test-optimize-js/
**Load Performance**

_Latency and Bandwith_
http://cloudping.info/
Put assets on CDN

_Caching_
cache-control response headers
if you already have it, just use the one you have. Not talking to server will be faster than talking to a server
no-store: the browser gets a new version every time. Use this if you need to see a new page everytime.
no-cache: this means you can store a copy, but you can't use it without checking with the server. Check to see if you have right version, if it does, it doesn't need to send you that file.
max-age: Tell the browser not to bother if whatever asset it has is less than a certain number of seconds old.

caching is great unless it messes up. If you send broken javascript file, you don't want that cached. Do cache busting.

Possible solution: `content-addressable-storage` which gives the js file a unique identifier like: main.567eea7aa72b3ee48649.js. Build it, check the file, give it a unique identifier, and get file. If you build a new version of file, the js file will have a new identifier number. So if user requests main.567eea7aa72b3ee48649.js, we tell them tohold on to this file for a year. If we update the app, we say here's the new version and we get cache busting.

caching for CDNs

_Service Worker_
Service Worker, some cool stuff to do with this like

_Lazy Load_
You don't need everything at once. Send less code, so they can parse less code. As they need stuff, send it later. We don't know what user is going to do, don't make them pay the javascript cost upfront.

_Analyzing Budnle Sizes_
Slim the dependencies.

lazy loading components with react-loadable
When they first see the initial landing page, if you're not using something that is being loaded, load that thing later. So get code progressively as user needs it. Just load what we need to get the page up, as you navigate around, we can serve you the other files. If one bundle requires the same thing we loaded on another one. So we're not paying tax to get it everytime but it's progressivley loading. Everything we have in memory stays, so we don't have to pay an additional network load costs.This allows us to cut down and initial load cost and parsing cost. By shipping less code, our code is faster because we're doing less of something. Main bundled is \_\_\_KB that is shipped over wire, then get things as you need them.

_HTTP/2_

_code splitting_
Don't load everything up front that's not essential for the first page load. Code splitting allows you to split out pieces of application so to defer the loading until later. Goal: First load is really quick and defer the load of other pieces until later. Defer the code for other things until ater.

Summary:
1st thing to do, set cache headers.
