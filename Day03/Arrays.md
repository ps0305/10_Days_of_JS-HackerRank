### Task

Complete the getSecondLargest function in the editor below. It has one parameter: an array,
`nums`, of `n` numbers. The function must find and return the second largest number in `nums`.

```js
/**
*   Return the second largest number in the array.
*   @param {Number[]} nums - An array of numbers.
*   @return {Number} The second largest number in the array.
**/
function getSecondLargest(nums) {
    // Complete the function
    let sortedArr = nums.sort((a,b) => a - b);
    let uniqueSort = sortedArr.filter((num, index, arr) => {
        return index === arr.indexOf(num);
    })
    return uniqueSort[uniqueSort.length - 2];

}


console.log('~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~');


function getSecondLargest(nums) {
  // We’re going to need to find the largest number in the array and store it in a
  // variable so we can test our other numbers against it.

  let largetNum = Math.max(...nums);
  let secondLargest;

  // Then, we need to loop through our array and see which number holds the highest value
  // and ISN’T our largestNumber. First, let’s start with our loop.
  for (let i = 0; i < nums.length; i++) {
    //Here we need to make sure we’re not testing the largetNumber variable against itself!
    if (nums[i] !== largetNum) {
      // Now, since we didn’t assign a value to secondLargest, it’s going to be undefined
      // and we can’t test our numbers against it. We can define it while testing our
      // number’s value with a simple if statement.
      if (secondLargest == undefined || nums[i] > secondLargest) {
        secondLargest = nums[i];

        // The tricky part here is testing the last index in the array.
        // There’s no nums[i + 1] to test against! Let’s make sure not to overlook that.
      } else if ((i = nums.length - 1)) {
        if (secondLargest == undefined || nums[i] > secondLargest) {
          secondLargest = nums[i];
        }
      }
    }
  }
  // And voila! We have our second largest number from our array!
  console.log(secondLargest);
  return secondLargest;
}
