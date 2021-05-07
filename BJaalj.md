## Go through the tasks given below and complete

- Write a function called `linearSearch` which accepts an array and a value. Using the linear search algorithm search for the value. If you find the value return the index of the element otherwise return -1. Olso write teh

```js
function linearSearch(array, item) {
  for (let i = 0; i < array.length; i++) {
    if (array[i] === item) return i;
  }
  return -1;
}

// TEST

const list = [12, 45, 48, 5, 451, 2, 34, 43, 54, 66];
console.log(linearSearch(list, 66)); // 9
console.log(linearSearch(list, 166)); // -1
console.log(linearSearch(list, 54)); // 8
```

- Write a function called `binarySearch` which accepts a sorted array and a value. Using the binary search algorithm search for the value. If you find the value return the index of the element otherwise return -1. Make sure to use the binary search algorithm.

```js
function binarySearch(arr, item) {
  let left = 0;
  let right = arr.length - 1;
  while (left <= right) {
    const mid = left + Math.floor((right - left) / 2);
    if (arr[mid] === item) {
      return mid;
    }
    if (arr[mid] < item) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return -1;
}

// TEST

const list = [2, 5, 12, 34, 43, 45, 48, 54, 66, 451];
console.log(binarySearch(list, 66)); // 8
console.log(binarySearch(list, 166)); // -1
console.log(binarySearch(list, 54)); // 7
```

- Compare the worst case complexity (Big O Notation) of linear search and binary search. Compare linear search and binary search

- Assume you have a list of `240,000` items and we want to search for a particular value. In the worst case situation how many times we will run the loop in the case of binary search algorithm and linear search algorithm.
