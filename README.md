# Web Components Style Guide

This guide serves as an extension to the [Google JavaScript Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml) with additional style guidance around authoring Web Components. It is targeted at Google engineers, but may be useful for others too :)

## General conventions

* All elements should use [seed-element](https://github.com/PolymerLabs/seed-element) as a starting point. This provides a clean base for authoring elements that are [reusable](http://www.polymer-project.org/docs/start/reusableelements.html). It includes a [component page](http://polymerlabs.github.io/seed-element) for documentation and a setup for [unit-testing](https://github.com/PolymerLabs/seed-element/tree/master/tests).
* Where possible try to follow the [SRP](http://en.wikipedia.org/wiki/Single_responsibility_principle) (Single-responsibility principle) & [first](http://addyosmani.com/first) for elements you are authoring. “Do one thing and do it well”.
* Extend existing elements over re-implementing functionality yourself. Alternatively, reuse base components (e.g. `<google-client-api>`) in your own.
* Ensure your element, methods, events, attributes, and properties are [well documented](http://googlewebcomponents.github.io/google-signin/components/google-signin/).
* Use [@attribute](https://github.com/GoogleWebComponents/google-signin/blob/master/google-signin.html#L260), [@property](https://github.com/GoogleWebComponents/google-sheets/blob/master/google-sheets.html#L166), [@method](https://github.com/GoogleWebComponents/google-analytics/blob/master/google-analytics-base.html#L84), [@event](https://github.com/GoogleWebComponents/google-signin/blob/master/google-signin.html#L160) to document the API for your element. 
* Ensure any styling hooks or accepted light DOM are documented in the element summary.
* Follow the Web Component [best practices](http://webcomponents.org/articles/web-components-best-practices/) guide where possible.
* Ensure your elements are [accessible](http://www.polymer-project.org/articles/accessible-web-components.html) from the get-go. 
* In your bower.json, depend on a specific version of Polymer (e.g. "polymer": "Polymer/polymer#~0.3.4")

## Naming

* Elements should contain a dash in their name (e.g `<my-tabs>` vs `<tabs>`), per spec.
* Google elements should be prefixed with “google” (e.g `<google-sheets`> vs `<g-sheets>`).
* Where multiple words are required for the name, they should be separated with a dash (e.g `<google-street-view-pano>` vs `<google-streetviewpano>`) for readability.
* Unless for private use, elements should use a unique name to avoid clashing with [existing](https://github.com/GoogleWebComponents) elements.

## Attributes

* Published attributes will be camel cased where multiple words are in-use
* Default property values in attributes are null. Provide sensible default values as part of your API if values will be bound and displayed anywhere in your template.
* Use `@default` and `@required` for parameters that either have a default value or are required.


## Events

* Event names should have a prefix strongly related to the name of the element in use (e.g `drive-upload-success` vs `upload-succeeded`). This allows you to drop in multiple elements in the page without event namespacing clashing.
* It’s fine to simplify things a bit if your element name is complex, as long as the relationship is unambiguous (e.g., for a load event on a `<google-client-api-loader>` element, use `google-client-api-load` instead of `google-client-api-loader-load`).
* A unique event name should be fired for unique actions in your element that will be of interest to the outside world.
* Events should either end in verbs in the infinitive form (e.g. `google-client-api-load`) or nouns (e.g `google-drive-upload-success`).
* Use declarative event handlers over JS based (e.g. don't write `addEventListener` in your element code).

## Variables

* Do not use $ to prepend your own object properties and variables. Consider this style of naming reserved for use by Polymer and jQuery. Polymer allows you to use `$.*` within `<template>` and `this.$.*` within script to access the content of element children.
* Define constants outside of the `Polymer()` constructor, wrapped in an anonymous self-executing function.
* If you need to define private or static variables, wrap your script using [standard techniques](http://www.polymer-project.org/docs/polymer/polymer.html#static) like anonymous self-calling functions.

## Methods

* Methods should be camel-cased where multiple verbs/words are in use (e.g `selectFile()` vs `selectfile()`).

## Tests

* `<seed-element>` has a setup using Mocha and Chai that should be adapted to exercise your own element’s functionality. Examples of existing tests written by the Polymer team can be found in [core-tests](https://github.com/Polymer/core-tests).

## Licensing

Note, that this section is mostly relevant to Google engineers working on elements and follows current requirements around open-source projects.

* As with other open source code that Google releases, use the Apache 2.0 license.
* Include a [LICENSE](https://github.com/GoogleWebComponents/google-chart/blob/master/LICENSE) file at the top level of your project.
* Include a copyright comment in your [demo.html](https://github.com/GoogleWebComponents/google-youtube/blob/master/demo.html#L2) file.
* Include "license": "Apache2" in your [bower.json](https://github.com/GoogleWebComponents/google-youtube/blob/master/bower.json#L10).
