---
layout: post
title:  "Annotations in Ebooks"
date:   2015-10-18 19:57:12
categories: update
---

Epub.js, a JavaScript library for rendering ebooks (using the ePub format) in the browser and on mobile devices, is used by a growing community in projects ranging from library catalogues to self published novels. Recently there has been a return to the our roots with several projects adopting it for academic research. The first request from these projects is always: how can we allow annotation in our reader?

We’re excited to announce that we’ve been awarded a grant from the [Hypothes.is Open Annotation Fund](http://anno.fund/) to add support for the [Epub Open Annotation Specification](http://www.idpf.org/epub/oa/). This will allow Epub.js to support highlights and annotations in an flexible and unintrusive way.

[Hypothes.is]("https://hypothes.is") is building an open platform for discussion on the web. It leverages annotation to enable sentence-level critique or note-taking on top of many form of digital media, from webpages, to pdfs and epubs. Their efforts are based on the Annotator project, and annotation standards for digital documents being developed by the W3C Web Annotation Working Group.

Our [current integration with Hypothes.is](https://s3.amazonaws.com/epubjs/examples/hypothesis.html) is nearly two years old now and the interface needs rethinking and updating. Sliding panels coming in from both side aren't ideal and obscure content. The design too closely mimics a printed book and as a result the paginated rendering hinders being able to make annotations across pages.

A scrolling view would allow navigating the book and using the Hypothes.is toolbar at the same time. We’re going to create a new example reader with the controls, navigation and Hypothes.is integrated together with scrolling text.

The next major release of Epub.js (v0.3) will update much of the library, allowing for continuous scrolling rendering and bringing a cleaner, simpler and better documented API. A compatibility script allow updating from the current API with minimal effort.

You can view an [example of the new renderer](https://s3.amazonaws.com/epubjs/examples/single-full.html), and be a part of the development on the [v0.3 branch on github](https://github.com/futurepress/epub.js/tree/v0.3).
