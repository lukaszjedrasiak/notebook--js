An individual node contains data and links to other nodes. Each data structure adds additional constraints or behavior to these features to create the desired structure.

Example
```js
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }

  setNextNode(node) {
    if (node instanceof Node || node === null) {
      this.next = node;
    } else {
      throw new Error('Next node must be a member of the Node class.');
    }
  }
  
  getNextNode() {
    return this.next;
  }
}

module.exports = Node;
```

Usage:
```js
const strawberryNode = new Node('Berry Tasty');
const vanillaNode = new Node('Vanilla');
const coconutNode = new Node('Coconuts for Coconut');

vanillaNode.setNextNode(strawberryNode);
strawberryNode.setNextNode(coconutNode);

// first node
let currentNode = vanillaNode;

// iterate over node path until the end (next === null)
while (currentNode !== null) {
  console.log(currentNode.data);
  currentNode = currentNode.next;
}
```