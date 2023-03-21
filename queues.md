A queue is a linear collection of nodes that exclusively adds (enqueues) nodes to the tail, and removes (dequeues) nodes from the head of the queue.

They can be implemented using different underlying data structures, but one of the more common methods is to use a singly linked list, which is what you will be using for your JavaScript `Queue` class.

Think of the queue data structure as an actual queue, or line, in a grocery store. The person at the front gets to leave the line first, and every person who joins the line has to join in the back.

Queues support three main operations:
1. Enqueue adds data to the back of the queue
2. Dequeue removes and provides data from the front of the queue
3. Peek provides data on the front of the queue

>Queues are a First In, First Out or FIFO structure.

If a queue has a limit on the amount of data that can be placed into it, it is considered a _bounded queue_.

Similar to stacks, attempting to enqueue data onto an already full queue will result in a _queue overflow_. If you attempt to dequeue data from an empty queue, it will result in a _queue underflow_.

## Additional Resources

-   [Visualizer: Queue](https://visualgo.net/en/list?slide=5)
-   [Video: Queue Datastructure](https://www.youtube.com/watch?v=zp6pBNbUB2U)
-   [Cheatsheet: Queue](https://github.com/trekhleb/javascript-algorithms/tree/master/src/data-structures/queue)

## Code Challenges

-   [Beginner - Number of Recent Calls](https://leetcode.com/problems/number-of-recent-calls)
-   [Beginner - Time Needed to Buy Tickets](https://leetcode.com/problems/time-needed-to-buy-tickets)
-   [Intermediate - Reveal Cards in Increasing Order](https://leetcode.com/problems/reveal-cards-in-increasing-order)
-   [More Practice Problems](https://leetcode.com/problemset/all/?search=queue)

## code

```js
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }

  setNextNode(node) {
    if (!(node instanceof Node)) {
      throw new Error('Next node must be a member of the Node class');
    }
    this.next = node;
  }

  setNext(data) {
    this.next = data;
  }

  getNextNode() {
    return this.next;
  }
}

module.exports = Node;
```

```js
const Node = require('./Node');

class LinkedList {
  constructor() {
    this.head = null;
  }

  addToHead(data) {
    const nextNode = new Node(data);
    const currentHead = this.head;
    this.head = nextNode;
    if (currentHead) {
      this.head.setNextNode(currentHead);
    }
  }

  addToTail(data) {
    let lastNode = this.head;
    if (!lastNode) {
      this.head = new Node(data);
    } else {
      let temp = this.head;
      while (temp.getNextNode() !== null) {
        temp = temp.getNextNode();
      }
      temp.setNextNode(new Node(data));
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
      currentNode = currentNode.next;
    }
    output = output.concat("<tail>");
    console.log(output);
  }
}

module.exports = LinkedList;
```

```js
const LinkedList = require("./LinkedList");

class Queue {
  constructor(maxSize = Infinity) {
    this.queue = new LinkedList();
    this.maxSize = maxSize;
    this.size = 0;
  }

  isEmpty() {
    return this.size === 0;
  }

  hasRoom() {
    return this.size < this.maxSize;
  }

  enqueue(data) {
    if (this.hasRoom()) {
      this.queue.addToTail(data);
      this.size++;
    } else {
      throw new Error("Queue is full!");
    }
  }

  dequeue() {
    if (!this.isEmpty()) {
      const data = this.queue.removeHead();
      this.size--;
      return data;
    } else {
      throw new Error("Queue is empty!");
    }
  }
}

module.exports = Queue;
```