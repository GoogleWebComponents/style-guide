# Google Web Components Style Guide

## General conventions

* Where possible try to follow the SRP (Single-responsibility principle) & first for elements you are authoring. “Do one thing and do it well”.
* All elements should use `<seed-element>` as a starting point.
* Extend existing elements over re-implementing functionality yourself. Alternatively, reuse base components (e.g. `<google-client-api>`) in your own
* Ensure your element, methods, events, attributes, and properties are well documented.
* Use @attribute, @property, @method, @event
* Ensure any styling hooks or accepted light DOM are documented in the element summary.
* Follow the Web Component best practices guide where possible.
* Ensure your elements are accessible from the get-go. 
* In your bower.json, depend on a specific version of Polymer (e.g. "polymer": "Polymer/polymer#~0.3.4"
