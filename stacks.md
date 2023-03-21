Stacks are another data structure with a perfectly descriptive name. Like a queue, a stack is a linear collection of nodes that adds (pushes) data to one end of the data structure (let’s say the top, for the purposes of this example). However, unlike a queue, a stack removes data (pops) from the same end of the data structure. Think of it as a stack of books, where you can only pick up the top book, and add a new book to the top.

Stacks are often thought of as a “First In, Last Out” (FILO) data structure — the first book you add to the stack won’t be removed until all other books are removed from the stack.

Queues on the other hand are thought of as a “First In, First Out” (FIFO) data structure — the first person in line will be the first person to leave the line.

Stacks provide three methods for interaction:
1. Push - adds data to the “top” of the stack
2. Pop - returns and removes data from the “top” of the stack
3. Peek - returns data from the “top” of the stack without removing it

## Additional Resources

-   [Visualizer: Stacks](https://visualgo.net/en/list?slide=4)
-   [Video: Stacks and Queues](https://www.youtube.com/watch?v=1AJ4ldcH2t4)
-   [Cheatsheet: Stacks](https://github.com/trekhleb/javascript-algorithms/tree/master/src/data-structures/stack)

## Code Challenges

-   [Beginner - Baseball Game](https://leetcode.com/problems/baseball-game)
-   [Beginner - Valid Parentheses](https://leetcode.com/problems/valid-parentheses)
-   [Intermediate - Daily Temperatures](https://leetcode.com/problems/daily-temperatures/)
-   [More Practice Problems](https://leetcode.com/problemset/all/?search=stack)

## code

```js
const LinkedList = require('./LinkedList');

class Stack {
  constructor(maxSize = Infinity) {
    this.stack = new LinkedList();
    this.maxSize = maxSize;
    this.size = 0;
  }

  // Add helper methods below this line
  hasRoom() {
    return this.size < this.maxSize;
  }
  isEmpty() {
    return this.size === 0;
  }

  push(value) {
    if (this.hasRoom()) {
      this.stack.addToHead(value);
      this.size++;
    } else {
      throw new Error('Stack is full');
    }
  }

  pop() {
    if (!this.isEmpty()) {
      const value = this.stack.removeHead();
      this.size--;
      return value;
    } else {
      throw new Error('Stack is empty');
    }
  }

  peek() {
    if (!this.isEmpty()) {
      return this.stack.head.data;
    } else {
      return null;
    }
  }
}

module.exports = Stack;
```