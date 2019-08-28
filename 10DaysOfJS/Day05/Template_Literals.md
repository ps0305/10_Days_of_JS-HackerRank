The code in the editor has a tagged template literal that passes the area and perimeter of a rectangle to a tag function named sides. Recall that the first argument of a tag function is an array of string literals from the template, and the subsequent values are the template's respective expression values.

Complete the function in the editor so that it does the following:

* Finds the initial values of `s1` and `s2` by plugging the area and perimeter values into the formula:
> P +/- (P*2 - (16 * A)) / 4;
  where `A` is the rectangle's area and `P` is its perimeter.
* Creates an array consisting of `s1` and `s2` and sorts it in ascending order.
* Returns the sorted array.

```js
'use strict';

process.stdin.resume();
process.stdin.setEncoding('utf-8');

let inputString = '';
let currentLine = 0;

process.stdin.on('data', inputStdin => {
    inputString += inputStdin;
});

process.stdin.on('end', _ => {
    inputString = inputString.trim().split('\n').map(string => {
        return string.trim();
    });
    
    main();    
});

function readLine() {
    return inputString[currentLine++];
}

/*
 * Determine the original side lengths and return an array:
 * - The first element is the length of the shorter side
 * - The second element is the length of the longer side
 * 
 * Parameter(s):
 * literals: The tagged template literal's array of strings.
 * expressions: The tagged template literal's array of expression values (i.e., [area, perimeter]).
 */
function sides(literals, ...expressions) {
    let area = expressions[0];
    let perimeter = expressions[1];

    let s1 = (perimeter + Math.sqrt(perimeter * perimeter - (16 * area))) / 4;
    let s2 = (perimeter - Math.sqrt(perimeter * perimeter - (16 * area))) / 4;
    let arr = [s1, s2];
    arr = arr.sort((a, b) => a - b);
    return arr;
}

