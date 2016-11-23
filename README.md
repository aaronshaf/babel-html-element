Because of Babel's implementation of [extends](https://github.com/babel/babel/issues/4480) and Custom Elements v1's [class requirement](https://github.com/w3c/webcomponents/issues/587), you will need something like this for transpiling custom elements to ES5.

## Example

```
npm install @webcomponents/custom-elements --save-dev
npm install babel-html-element --save-dev
```

```javascript
import '@webcomponents/custom-elements' // polyfill
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
