# Polymer Framework Interoperability

Have you tried using Polymer with another framework and had issues?
Let's fix them!

The goal of this project is to figure out how to make Polymer play nice with
other popular developer tools. Because Polymer is based on Web Component
standards, _in theory_, things should "just work" but whether it be from
polyfill quirks or timing mishaps, reality sometimes proves otherwise.

## Tell Us Where Things Break

Not being an expert in every framework or library I need the community's help
to figure out where things don't quite line up. So if you're interested please:

1. [Open an issue](https://github.com/robdodson/polymer-framework-interop/issues)
2. Provide a reduced test case (ideally a [jsbin](https://jsbin.com/))
3. Help us work through the problem :)

---

## Angular 1

### Two-way Data Binding

### Problem
Out of the box, data binding to a Polymer element from an Angular controller
will only work one-way. Angular is not able to hear about property changes that
occur inside of a Polymer element.

![An arrow pointing from Angular to Polymer and an arrow with a slash through
it point from Polymer to Angular](https://s3.amazonaws.com/media-p.slid.es/uploads/387002/images/1944519/dataflow.jpeg)

### Solution
The [angular-poly-grip](https://github.com/robdodson/angular-poly-grip)
directive can be used to fix the linkage between Polymer elements and Angular
controllers so two-way binding works again. This directive listens for the
property changed events that Polymer fires and uses those events to update
the Angular scope with the new value.

### Example
[Try it on Plunkr](https://plnkr.co/edit/1wmaOehXrtd6k0GsGOeQ?p=preview)
