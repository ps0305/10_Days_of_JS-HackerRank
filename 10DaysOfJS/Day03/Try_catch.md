
```js
/*
 * Complete the reverseString function
 * Use console.log() to print to stdout.
 */
function reverseString(str) {
    try {
        var splitStr = str.split("");
        var reverseArray = splitStr.reverse();
        var joinArray = reverseArray.join("");
        console.log(joinArray);
    }
    catch (error)
        {
            // Print s on a new line. If no exception was thrown, then this should be the reversed string; if an exception was thrown, this should be the original string.
            console.log(error.message);
            console.log(str);
        }
    
    
}
