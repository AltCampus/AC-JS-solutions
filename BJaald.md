## Queue

- Linear data structure
- Flexible size
- First in Last out (LIFO)

### Implement Queue using Array

Create a class named `Queue` with the following properties and methods:

- While implementing this you can use Array to store data and use any array methods.
- Test the `Stack` class using `Test 1` and `Test 2` given below

The class `Queue` will accept one optional parameter `capacity` using which we can limit the data size. The value of `capacity` will default to `Infinity`.

Properties:

- `storage` use it to store the data for the queue. It should be an array
- `capacity` defaults to `Infinity` if the length is above capacity the item can't be added. Alert a message saying `Queue is overflowing`
- `length` it will return the length of the queue (Getter/Setter)

YOU CAN ADD OTHER PROPERTIES IF YOU NEED.

Methods:

- `enqueue` Add the element to the queue
- `dequeue` Removes an element from the queue
- `peek` returns the first element from the top of the queue
- `printAll` print all the elements of the queue from one after another from the top
- `isEmpty` Returns `true` if the queue is empty

```js
class Queue {
  constructor(capacity = Infinity) {
    this.capacity = capacity;
    this.store = [];
  }
  get length() {
    return this.store.length;
  }
  enqueue(newValue) {
    if (this.store.length >= this.capacity) {
      alert(`Stack is overflowing`);
      return;
    }
    this.store.unshift(newValue);
    return this.store.length;
  }
  dequeue() {
    return this.store.pop();
  }
  peek() {
    return this.store[this.length - 1];
  }
  printAll() {
    this.store.forEach((elm) => {
      console.log(elm);
    });
  }
  isEmpty() {
    return this.store.length === 0;
  }
}

// Test 1

const queue = new Queue();

queue.enqueue(10);
queue.enqueue(12);
queue.enqueue(120);
queue.enqueue(1);
queue.enqueue(4);

console.log(queue.dequeue()); // => 10
console.log(queue.length); // => 4
console.log(queue.dequeue()); // => 12
console.log(queue.length); // => 3

console.log(queue.peek()); // 120

console.log(queue.isEmpty()); // false

console.log(queue.dequeue()); // => 120

console.log(queue.peek()); // => 1

console.log(queue.dequeue()); // => 1
console.log(queue.dequeue()); // => 4

console.log(queue.isEmpty()); // true

// Test 2

const queue2 = new Queue(4);

queue2.enqueue(10);
queue2.enqueue(12);
queue2.enqueue(120);
queue2.enqueue(1);
queue2.enqueue(4); // alert Queue is overflowing

console.log(queue2.dequeue()); // => 10
console.log(queue2.length); // => 3
console.log(queue2.dequeue()); // => 12
console.log(queue2.length); // => 2

console.log(queue2.peek()); // 120

console.log(queue2.isEmpty()); // false

console.log(queue2.dequeue()); // => 120

console.log(queue2.peek()); // => 1

console.log(queue2.dequeue()); // => 1

console.log(queue2.isEmpty()); // true
```

### Implement Queue using Object to Store Data

Create a class named `Queue` with the following properties and methods:

- **While implementing this you can only use an Object to store data.**
- While implementing this you can use Array to store data and use any array methods.

Properties:

- `storage` use it to store the data for the queue. It should be an object
- `capacity` defaults to `Infinity` if the length is above capacity the item can't be added. Alert a message saying `Queue is overflowing`
- `length` it will return the length of the queue (Getter/Setter)

YOU CAN ADD OTHER PROPERTIES IF YOU NEED.

Methods:

- `enqueue` Returns true if the queue is empty
- `dequeue` Removes an element from the queue
- `peek` returns the first element from the top of the queue
- `printAll` print all the elements of the queue from one after another from the top
- `isEmpty` Returns `true` if the queue is empty

```js
class Queue {
  constructor(capacity = Infinity) {
    this.capacity = capacity;
    this.store = {};
    this.headIndex = 0;
    this.tailIndex = 0;
  }
  get length() {
    return this.tailIndex - this.headIndex;
  }
  enqueue(newValue) {
    if (Object.keys(this.store).length >= this.capacity) {
      alert(`Queue is overflowing`);
      return;
    }
    this.store[this.tailIndex] = newValue;
    this.tailIndex++;
    return Object.keys(this.store).length;
  }
  dequeue() {
    const item = this.store[this.headIndex];
    delete this.store[this.headIndex];
    this.headIndex++;
    return item;
  }
  peek() {
    return this.store[this.headIndex];
  }
  printAll() {
    Object.keys(this.store)
      .sort((a, b) => a - b)
      .forEach((key) => {
        console.log(this.store[key]);
      });
  }
  isEmpty() {
    return Object.keys(this.store).length === 0;
  }
}

// Test 1

const queue = new Queue();

queue.enqueue(10);
queue.enqueue(12);
queue.enqueue(120);
queue.enqueue(1);
queue.enqueue(4);

console.log(queue.dequeue()); // => 10
console.log(queue.length); // => 4
console.log(queue.dequeue()); // => 12
console.log(queue.length); // => 3

console.log(queue.peek()); // 120

console.log(queue.isEmpty()); // false

console.log(queue.dequeue()); // => 120

console.log(queue.peek()); // => 1

console.log(queue.dequeue()); // => 1
console.log(queue.dequeue()); // => 4

console.log(queue.isEmpty()); // true

// Test 2

const queue2 = new Queue(4);

queue2.enqueue(10);
queue2.enqueue(12);
queue2.enqueue(120);
queue2.enqueue(1);
queue2.enqueue(4); // alert Queue is overflowing

console.log(queue2.dequeue()); // => 10
console.log(queue2.length); // => 3
console.log(queue2.dequeue()); // => 12
console.log(queue2.length); // => 2

console.log(queue2.peek()); // 120

console.log(queue2.isEmpty()); // false

console.log(queue2.dequeue()); // => 120

console.log(queue2.peek()); // => 1

console.log(queue2.dequeue()); // => 1

console.log(queue2.isEmpty()); // true
```
