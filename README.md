You will need something like this for transpiling custom elements to ES5.

## Usage

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

## Relevant issues

* https://github.com/babel/babel/issues/4480
* https://github.com/w3c/webcomponents/issues/587#issuecomment-254126763

## See also

* [webcomponents/custom-elements/blob/master/src/native-shim.js](https://github.com/webcomponents/custom-elements/blob/master/src/native-shim.js) (see [Known Issues](https://github.com/webcomponents/custom-elements#known-issues))
