# dom-adaptive

[Polymer](https://www.polymer-project.org) web component dom template adaptive/responsive to element size.
It works similar to media queries but adapt to element not screen size. It's based on [dom-if](https://www.polymer-project.org/1.0/api/#dom-if) implementation toggled by [IronResizableBehavior](https://elements.polymer-project.org/elements/iron-resizable-behavior)

Stamps the template if the `minWidth`,`minHeight`,`maxWidth`,`maxHeight` properties are met parents size.

When properties don't meet parents size, the stamped content is hidden but not removed from dom. When properties meet parents size again, the content is simply re-shown. This approach is used due to its favorable performance characteristics: the expense of creating template content is paid only once and lazily.

Set the `restamp` property to true to force the stamped content to be created / destroyed when the property conditions change.

## Docs & Demo

[http://paio-co-kr.github.io/dom-adaptive](http://paio-co-kr.github.io/dom-adaptive)

## Usage
- adaptive to width
```html
<div>
  <dom-adaptive max-width="700">
    shown if parent div width is smaller than 700px
  </dom-adaptive>
  <dom-adaptive min-width="700">
    shown if parent div width is 700px or larger
  </dom-adaptive>
</div>
```
- combinations
```html
  <dom-adaptive max-width="300" max-height="300">
    small view
  </dom-adaptive>
  <dom-adaptive min-width="300" min-height="300" max-width="500" max-height="500">
    medium view
  </dom-adaptive>
  <dom-adaptive min-width="500" min-height="500">
    large view
  </dom-adaptive>
```

## Note
If dom-adaptive won't work as it is expected, It's because it didn't get `resize` event properly. Host element must call `notifyResize` manually Implementing IronResizableBehavior. It's by Polymer resize event design. ref : [PolymerElements/iron-pages#13](https://github.com/PolymerElements/iron-pages/issues/13)

In case you want `dom-adaptive` out of Polymer env, You can prepare yourself other libs like [javascript-detect-element-resize](https://github.com/sdecima/javascript-detect-element-resize), [jQuery-mutate](http://www.jqui.net/jquery-projects/jquery-mutate-official/), etc, then call `notifyResize` manually.
