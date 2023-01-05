# JavaScript DOM

## DOM

### What is the DOM?
DOM is the Document Object Model.

The DOM is a (potentially) large object that describes the structure of our content. The DOM is represented by the document object. This object represents all elements on the webpage and is the entry point for accessing those elements. **Remember!** The DOM is not the source code.

```js
// returns a representation of the current html document
document

// returns a representation of the body element
document.querySelector('body')
document.getElementById('idName')
document.getElementsByClassName('className')

// use document object to change style
document.querySelector('body').style.backgroundColor = 'red'
// use document object to insert a text value
document.getElementById('idName').innerText = 'some words'
// use document object to get all values in a group of nodes(container in DOM tree)
const group = document.getElementsByClassName('className')
for (let i = 0; i < group.length; i++){
    console.log(group[i].innerText)
}
```