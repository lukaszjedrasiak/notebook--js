The list is comprised of a series of nodes. The head node is the node at the beginning of the list. Each node contains data and a link (or pointer) to the next node in the list. The list is terminated when a node’s link is null. This is called the tail node.

## Additional Resources

-   [Visualizer: Singly-Linked List](https://visualgo.net/en/list?slide=6)
-   [Video: Linked List Data Structure Overview](https://www.youtube.com/watch?v=njTh_OwMljA&feature=emb_title)
-   [Cheatsheet: Linked List](https://github.com/trekhleb/javascript-algorithms/tree/master/src/data-structures/linked-list)

## Code Challenges

-   [Beginner - Middle of a Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)
-   [Intermediate - Reverse a Singly-Linked List](https://www.codecademy.com/code-challenges/code-challenge-reverse-a-singly-linked-list-javascript)
-   [Intermediate - Swap Elements in a Linked List](https://www.codecademy.com/code-challenges/code-challenge-swap-elements-in-a-linked-list-javascript)
-   [More Practice Problems](https://leetcode.com/problemset/all/?search=singly%20linked%20list)

## code

Example:
```js
const Node = require('./Node');

class LinkedList {
  constructor() {
    this.head = null;
  }

  addToHead(data) {
    const newHead = new Node(data);
    const currentHead = this.head;
    this.head = newHead;
    if (currentHead) {
      this.head.setNextNode(currentHead);
    }
  }

  addToTail(data) {
    let tail = this.head;
    if (!tail) {
      this.head = new Node(data);
    } else {
      while (tail.getNextNode() !== null) {
        tail = tail.getNextNode();
      }
      tail.setNextNode(new Node(data));
    }
  }

  removeHead() {
    const removedHead = this.head;
    if (!removedHead) {
      return;
    }
    this.head = removedHead.getNextNode();
    return removedHead.data;
  }

  printList() {
    let currentNode = this.head;
    let output = '<head> ';
    while (currentNode !== null) {
      output += currentNode.data + ' ';
      currentNode = currentNode.getNextNode();
    }
    output += '<tail>';
    console.log(output);
  }
}

module.exports = LinkedList;
```

Usage:
```js
const LinkedList = require('./LinkedList');

const seasons = new LinkedList();
seasons.printList();

seasons.addToHead('summer');
seasons.addToHead('spring');
seasons.printList();

seasons.addToTail('fall');
seasons.addToTail('winter');
seasons.printList();

seasons.removeHead();
seasons.printList();
```

## swapping nodes

```js
const LinkedList = require('./LinkedList.js')

const testList = new LinkedList();
for (let i = 0; i <= 10; i++) {
  testList.addToTail(i);
}

testList.printList();
swapNodes(testList, 2, 5);
testList.printList();
  
function swapNodes(list, data1, data2) {
  console.log(`Swapping ${data1} and ${data2}:`);
  let node1Prev = null;
  let node2Prev = null;
  let node1 = list.head;
  let node2 = list.head;

  if (data1 === data2) {
    console.log('Elements are the same - no swap to be made');
    return;
  }

  while (node1 !== null) {
    if (node1.data === data1) { 
      break;
    }
    node1Prev = node1;
    node1 = node1.getNextNode();
  }

  while (node2 !== null) {
    if (node2.data === data2) {
      break;
    }

    node2Prev = node2;
    node2 = node2.getNextNode();
  }

  if (node1 === null || node2 === null) {
    console.log('Swap not possible - one or more element is not in the list');
    return;
  }

  if (node1Prev === null) {
    list.head = node2;
  } else {
    node1Prev.setNextNode(node2);
  }

  if (node2Prev === null) { 
    list.head = node1;
  } else {
node2Prev.setNextNode(node1);
  }
  let temp = node1.getNextNode();
  node1.setNextNode(node2.getNextNode());
  node2.setNextNode(temp); 
}
```