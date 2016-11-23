Custom Elements [require ES6 classes](https://github.com/w3c/webcomponents/issues/587) but Babel poorly implements [extends](https://github.com/babel/babel/issues/4480). You will need something like this for transpiling custom elements to ES5.

## Example

```
npm install babel-html-element --save-dev
```

```javascript
import HTMLElement from 'babel-html-element'

export default class MyCustomElement extends HTMLElement {
  static get observedAttributes() { return [] }
  attributeChangedCallback(name, oldValue, newValue) {}
  connectedCallback() {}
  disconnectedCallback() {}
}
```

```javascript
customElements.define('my-element', MyCustomElement)
```

## See also

* [webcomponents/custom-elements/blob/master/src/native-shim.js](https://github.com/webcomponents/custom-elements/blob/master/src/native-shim.js) (see [Known Issues](https://github.com/webcomponents/custom-elements#known-issues))

## Custom Elements polyfill

```
npm install @webcomponents/custom-elements --save-dev
```
```javascript
import '@webcomponents/custom-elements'
```

Or:

```html
<script src="https://unpkg.com/@webcomponents/custom-elements@1.0.0-alpha.3"></script>
```
