
We define `S` to be a sequence of distinct sequential integers from `1` to `n`; in other words, `S={1,2,3,4,5,...,n}` We want to know the maximum bitwise AND value of any two integers,`a` and `b` (where `a < b`), in sequence `S` that is also less than a given integer `K`

Complete the function in the editor so that given `n`
and `k`, it returns the maximum `a&b < k`.
```js
/*
*	Return the largest value of any a & b < k in S (where a < b).
* 	
*	n: Set S is a sequence of distinct integers from 1 to n (i.e., {1, 2, ..., n}).
*	k: An integer.
*/

function getMaxLessThanK(n, k) {
    let max = 0;
    let curr = -1;
    for (let i = 1; i < n; i++) {
        for (let j = i + 1; j <= n; j++) {
            curr = i & j;
            if (curr < k && curr > max) {
                max = curr;
            }
        }
    }
    return max;
}
