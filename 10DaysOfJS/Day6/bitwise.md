

```js
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
