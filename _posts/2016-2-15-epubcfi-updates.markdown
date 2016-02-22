---
layout: post
title:  "Epub CFI Updates"
date:   2016-2-15 19:57:12
categories: update
---

[EPUB Canonical Fragment Identifiers](http://www.idpf.org/epub/linking/cfi/epub-cfi.html) (epubcfi) allow for a powerful
and standardized way to reference locations in an ePub. They are core to the rendering and navigation features in Epub.js and have been significant updated in v0.3.

The most important update is the ability to handle [Epub Cfi Ranges](http://www.idpf.org/epub/linking/cfi/epub-cfi.html#sec-ranges). Ranges provide an easy way to reference a span of text content, without worrying about spanning the underlying Dom Elements. For instance in Moby Dick “Call me Ishmael.” can be represented by `epubcfi(/6/14[xchapter_001]!/4/2/4/2[c001s0001],/1:0,/1:16)`.

Using Epub,js you can retrieve text from anywhere in the book by passing a epubcfi range to `book.range(…)`. This will parse the epubcfi, load the chapter and pass that chapter’s document to `EpubCfi.toRange(doc)`, returning a Dom Range containing the text. You can then get the text content by calling to `range.toString()` on the range returned in the promise.

Additionally user’s selections in rendered chapters will trigger a “selected” event that returns the epubcfi range of the selected text. This forms the basis for our integration with Hypothes.is, allowing for saving the epubcfi range with the annotation.

To help with highlighting these annotations, the epubcfi parser can now ignore elements with a specified class names. It will treat the text of an ignored element as a part of the previous textNode. This allows for adding spans in a document to highlight a range of text, without it interfering with returning a correct epubcfi.

Lastly all functions of Epub.js have been organized into commonjs modules, so you can require the epubcfi parsers using `require('epubjs/src/epubcfi')`.

Below is a quick example of simple highlighting using the Rangy library.

{% include highlights.html %}
