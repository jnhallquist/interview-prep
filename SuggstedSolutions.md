### You are given a sorted array of integers and a target integer. If this array contains the target integer, return the index at which it is found. Otherwise, return 'Not found'.

```javascript
const searchArrayForInteger = (array, target) => {
  const middleIndex = (array.length / 2) - 1;

  if (target === array[middleIndex]) {
    return middleIndex;
  }

  if (target < array[middleIndex]) {
    for (let i = 0; i <= middleIndex; i++) {
      if (array[i] === target) {
        return i;
      }
    }
  } else {
    for (let i = middleIndex; i < array.length; i++) {
      if (array[i] === target) {
        return i;
      }
    }
  }

  return 'Not found';
};
```

### Given two arrays of integers and a target sum, determine whether the first array contains a number which, when added to a number from the second array, equals the target sum. Return all pairs of numbers whose sum equals the target sum.

```javascript
const findPairsWithSum = (array1, array2, target) => {
  const pairs = [];
  let missingNumber;

  for (let i = 0; i < array1.length; i++) {
    missingNumber = target - array1[i];
    if (array2.includes(missingNumber)) {
      pairs.push([array1[i], missingNumber]);
    }
  }

  return pairs.length > 0 ? pairs : 'No pairs';
};
```

### Determine if a given string contains all unique characters.

```javascript
const hasUniqueCharacters = (str) => {
  const charMap = new Map();
  let idx = 0;
  let numOfRepeatedChars = 0;
  let currentChar;

  do {
    currentChar = str.charAt(idx);

    if (!charMap.get(currentChar)) {
      charMap.set(currentChar, 1);
    } else {
      numOfRepeatedChars++;
    }

    idx++;
  } while (idx < str.length && numOfRepeatedChars === 0);

  return numOfRepeatedChars === 0;
};
```

### Given an array of integers, move all zeroes to the end of the array. Preserve the order of the original array. Do not create a temporary array.

```javascript
const moveZeroes = (arr) => {
  // Tracking length of array
  let i = 0;
  // Tracking zeroes
  let j = 0;

  while (j < arr.length) {
    if (arr[j] === 0) {
      j++;
    } else {
      arr[i] = arr[j];
      i++;
      j++;
    }
  }

  while (i < arr.length) {
    arr[i] = 0;
    i++;
  }

  return arr;
};
```
