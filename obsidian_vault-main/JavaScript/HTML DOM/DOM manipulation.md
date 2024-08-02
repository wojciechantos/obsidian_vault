
Tags: [[JavaScript]]

---
 
DOM - Document Object Model is a tree-like representation of the contents of a web page - a tree of "nodes" with different relationships depending on how they're arranged in the HTML document.

```html
<div id="container"> //parent
  <div class="display"></div> // child of 'container' / sibling to 'controls'
  <div class="controls"></div>
</div>
```


**CREATING ELEMENTS**

```js
// Syntax
const element = document.createElement('element');

parentElement.appendChild(element);

// examples
const div = document.createElement('div');
body.appendChild(div);

const ul = document.createElement('ul');
const li = document.createElement('li');

ul.appendChild(li);
```

---

**REMOVING ELEMENTS**

`// Syntax`
`// removeChild method`
`parent.removeChild(child);`

`// remove method`
`child.remove();`

`// examples`
`ul.removeChild(li);`

`// or`
`li.remove();`

---

**QUERYING ELEMENTS**

- the `querySelector()` method returns the first element that matches a CSS selector
- to return all matching elements, use `querySelectorAll()` instead

`// Syntax`
`// by id`
`const element = document.querySelector('#elementId');`
`const element = document.querySelectorAll('#elementId');`

`// by class name`
`const element = document.querySelector('.className');`
`const element = document.querySelectorAll('.className');`

---

**MODIFYING ELEMENT ATTRIBUTES**

`// General`

`element.setAttribute(attribute, value);`
`element.removeAttribute(attribute);`

`// Examples`

`element.style.fontSize = '18px';`

`element.id = 'newId';`

`element.innerText = 'Example text';`

`//modifying the class`
`element.classList.add('myClass');`
`element.classList.remove('myClass');`



