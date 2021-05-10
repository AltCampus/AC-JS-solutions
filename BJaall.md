## Implement Sorting Algorithms

We learned about different sorting algorithms in the previous block. Implement the sorting algorithms you learned in the videos as a function.

1. Write down the steps to perform for different sorting algorithms i.e bubble, insertion and selection. Write in your own words. After writing the algorithm take an example of an array and draw the diagram for each step for different algorithm.

Example:

#### Bubble Sort

step-1: We will compare the first item with the second. If the first item is bigger than the second item we will swap them so that the bigger one stays in the second position.

step-2: And then compare second with third item. If second item is bigger than the third, we swap them. otherwise, they stayed in their position. Hence, the biggest among first three is in the third position.

step-3: We keep doing it. Until we hit the last element of the array. In that way we bubble up the biggest item of the array to the right most position of the array.

step-4: Now we will repeat the step 1, 2 and 3 but we will keep in mind not to touch the last element.

![Bubble Sort Example](./bubble.png)

<!-- You answer -->

2. Create a function named `bubbleSort` that accepts an array of numbers and returns the array with sorted values. The elements should be in ascending order. Use the bubble sorting algorithms. After writing the function test it with an array and check if you are getting the right output.

```js
function bubbleSort(arr) {
  let len = arr.length;
  for (let i = len - 1; i >= 0; i--) {
    for (let j = 1; j <= i; j++) {
      if (arr[j - 1] > arr[j]) {
        let temp = arr[j - 1];
        arr[j - 1] = arr[j];
        arr[j] = temp;
      }
    }
  }
  return arr;
}
console.log(bubbleSort([7, 5, 2, 4, 3, 9])); //[2, 3, 4, 5, 7, 9]
console.log(bubbleSort([9, 7, 5, 4, 3, 1])); //[1, 3, 4, 5, 7, 9]
console.log(bubbleSort([1, 2, 3, 4, 5, 6])); //[1, 2, 3, 4, 5, 6]
```

3. Create a function named `selectionSort` that accepts an array of numbers and returns the array with sorted values. The elements should be in ascending order. Use the selection sorting algorithms. After writing the function test it with an array and check if you are getting the right output.

```js
function selectionSort(arr) {
  let minIdx,
    temp,
    len = arr.length;
  for (let i = 0; i < len; i++) {
    minIdx = i;
    for (let j = i + 1; j < len; j++) {
      if (arr[j] < arr[minIdx]) {
        minIdx = j;
      }
    }
    temp = arr[i];
    arr[i] = arr[minIdx];
    arr[minIdx] = temp;
  }
  return arr;
}

console.log(bubbleSort([7, 5, 2, 4, 3, 9])); //[2, 3, 4, 5, 7, 9]
console.log(bubbleSort([9, 7, 5, 4, 3, 1])); //[1, 3, 4, 5, 7, 9]
console.log(bubbleSort([1, 2, 3, 4, 5, 6])); //[1, 2, 3, 4, 5, 6]
```

4. Create a function named `insertionSort` that accepts an array of numbers and returns the array with sorted values. The elements should be in ascending order. Use the insertion sorting algorithms. After writing the function test it with an array and check if you are getting the right output.

```js
function insertionSort(arr) {
  let n = arr.length;
  for (let i = 1; i < n; i++) {
    let current = arr[i];
    let j = i - 1;
    while (j > -1 && current < arr[j]) {
      arr[j + 1] = arr[j];
      j--;
    }
    inputArr[j + 1] = current;
  }
  return inputArr;
}
console.log(bubbleSort([7, 5, 2, 4, 3, 9])); //[2, 3, 4, 5, 7, 9]
console.log(bubbleSort([9, 7, 5, 4, 3, 1])); //[1, 3, 4, 5, 7, 9]
console.log(bubbleSort([1, 2, 3, 4, 5, 6])); //[1, 2, 3, 4, 5, 6]
```

5. After writing all the sorting algorithm check the output with the array given below and make sure you are getting the right output.

```js
let values = [76, 34, 12, 32, 4, 2, 123, 5667, 8, 1, 3];
```
