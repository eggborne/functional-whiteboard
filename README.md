```
// with recursion
const removeDuplicates = arr => {
  return (c = 0) => {
    if (c === arr.length -1) {
      return arr;
    } else {
      arr.forEach((item, i) => {
        if (i !== c && item === arr[c]) {
          arr.splice(i, 1);
          c--;
        }
      });
      return removeDuplicates(arr)(c + 1);
    }
  }
}

console.log(removeDuplicates([7, 9, "hi", 12, "hi", 7, 53])());
// output: [7, 9, "hi", 12, 53]


// without recursion
const removeDuplicatesWithoutRecursion = arr => {
  return Array.from(new Set(arr));
}

console.log('without recursion:', removeDuplicatesWithoutRecursion([7, 9, "hi", 12, "hi", 7, 53]));
// output: [7, 9, "hi", 12, 53]


// with filter
const removeDuplicatesWithFilter = arr => {
  return arr.filter((item, i) => arr.indexOf(item) === i);
}

console.log('with filter:', removeDuplicatesWithFilter([7, 9, "hi", 12, "hi", 7, 53]));
// output: [7, 9, "hi", 12, 53]
```
