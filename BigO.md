### Big O

#### What is it?
As it relates to Computer Science, an algorithm is a procedure (i.e., a well-defined set of instructions) that allows a computer to solve a problem.

Big O Notation is the language and metric used to describe an algorithm's efficiency.
* Time complexity
  * How does an algorithm's runtime grow with respect to its input?
* Space complexity
  * How does the amount of memory required by an algorithm increase as its input size grows?

#### Common runtimes
* **O(1) time ("constant time")**
  * Ex: Console logging the first element in an array
    ```javascript
    const printFirstElement = (array) => {
      console.log(array[0]);
    }
    ```
    Regardless of the array's length, this algorithm's runtime will not change.
* **O(n) time ("linear time")**
  * Ex: Console logging every element in an array
    ```javascript
    const printAllElements = (array) => {
      array.forEach((element) => {
        console.log(element);
      });
    }
    ```
    "n" represents the number of elements in the array. As "n" increases, the algorithm's runtime also grows proportionately.
* **O(n<sup>​2</sup>​) time ("quadratic time")**
  * Ex: Given an array of 10 items, console log each item 10 times
  ```javascript
  const printEachTenTimes = (array) => {
    array.forEach((element) => {
      for (let i = 0; i < 10; i++) {
        console.log(element);
      }
    });
  }
  ```
  * The outer loop executes "n" times. For each time the outer loop runs, the inner loop is executed "n" times
* **O(log n) time ("logarithmic time")**
  * Ex: Given a sorted array of strings, find the index at which an item appears
    * Why not linear time? Let's say this array contains 10 words and the target word appears last. It will take 10 "steps" to find it. Now let's say the array contains 100,000 words and the target word appears last. It will now take 100,000 "steps".
    * Logarithmic time decreases the runtime of an algorithm by a certain amount each time.
  * Binary search
    * When you are given a sorted array and you need to find a certain element, you can keep cutting the size of the array you need to search in half.
    * Let's say the array of words has a length of 20. If you divide it in half, each half contains 10 elements.
    * If you determine which half contains your target item, you can now divide that array in half, producing two arrays of length 5.
    * Continue this process until you find your target item.
    * For the mathematical breakdown, a suggested resource is [this article](https://www.interviewcake.com/concept/java/binary-search)
