# dom-adaptive

Polymer web component dom template adaptive/responsive to element size.
It works simillar to media queries but adapt to element not screen size.


## Docs & Demo

[http://paio-co-kr.github.io/dom-adaptive](http://paio-co-kr.github.io/dom-adaptive)

## Usage
dom-adaptive requires [Polymer](https://www.polymer-project.org). For details take a look at docs page.
```html
<link rel="import" href="bower_components/polymer/polymer.html">
<link rel="import" href="bower_components/dom-adaptive/dom-adaptive.html">
...
</head>
<body>
...
<div>
  <dom-adaptive max-width="700">
    shown if parent div width is smaller than 700px
  </dom-adaptive>
  <dom-adaptive min-width="700">
    shown if parent div width is 700px or larger
  </dom-adaptive>
</div>
...
```
