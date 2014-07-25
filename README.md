# Google Web Components Style Guide

This guide serves as an extension to the [Google JavaScript Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml) with additional style guidance around authoring Web Components.

## General conventions

* All elements should use [seed-element](https://github.com/PolymerLabs/seed-element) as a starting point. This provides a clean base for authoring elements that are [reusable](http://www.polymer-project.org/docs/start/reusableelements.html).
* Where possible try to follow the [SRP](http://en.wikipedia.org/wiki/Single_responsibility_principle) (Single-responsibility principle) & [first](http://addyosmani.com/first) for elements you are authoring. “Do one thing and do it well”.
* Extend existing elements over re-implementing functionality yourself. Alternatively, reuse base components (e.g. `<google-client-api>`) in your own.
* Ensure your element, methods, events, attributes, and properties are well documented.
* Use `@attribute`, `@property`, `@method`, `@event`.
* Ensure any styling hooks or accepted light DOM are documented in the element summary.
* Follow the Web Component [best practices](http://webcomponents.org/articles/web-components-best-practices/) guide where possible.
* Ensure your elements are [accessible](http://www.polymer-project.org/articles/accessible-web-components.html) from the get-go. 
* In your bower.json, depend on a specific version of Polymer (e.g. "polymer": "Polymer/polymer#~0.3.4")

## Naming

* Elements should contain a dash in their name (e.g `<my-tabs>` vs `<tabs>`), per spec.
* Google elements should be prefixed with “google” (e.g `<google-sheets`> vs `<g-sheets>`).
* Where multiple words are required for the name, they should be separated with a dash (e.g `<google-street-view-pano>` vs `<google-streetviewpano>`) for readability.
* Unless for private use, elements should use a unique name to avoid clashing with existing elements.
