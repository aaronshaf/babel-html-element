You will need something like this for transpiling custom elements to ES5.

## Usage

```
npm install babel-html-element --save-dev
```

```javascript
import HTMLElement from 'babel-html-element'

export default class MyCustomElement extends HTMLElement {
  attributeChangedCallback(name, oldValue, newValue) {}
  connectedCallback() {}
  disconnectedCallback() {}
  updateRendering() {}
}
```

## Relevant issues

* https://github.com/babel/babel/issues/4480
* https://github.com/w3c/webcomponents/issues/587#issuecomment-254126763
