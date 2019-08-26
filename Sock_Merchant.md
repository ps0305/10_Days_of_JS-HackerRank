John works at a clothing store. He has a large pile of socks that he must pair by color for sale. Given an array of integers representing the color of each sock, determine how many pairs of socks with matching colors there are.

For example, there are n = 7,socks with colors ar = [1,2,1,2,1,3,2]. There is one pair of color 1 and one of color 2. There are three odd socks left, one of each color. The number of pairs is 2.

### Function Description

Complete the sockMerchant function in the editor below. It must return an integer representing the number of matching pairs of socks that are available.

sockMerchant has the following parameter(s):

* n: the number of socks in the pile
* ar: the colors of each sock

#### Sample Input
```
9
10 20 20 10 10 30 50 10 20
```
#### Sample Output
```
3
```

```js
// Complete the sockMerchant function below.
function sockMerchant(n, ar) {
    let sortedArr = ar.sort((a, b) => a - b)
    let pairCount = 0;
    for (let i = 0; i < n - 1; i++) {
        if (sortedArr[i] === sortedArr[i + 1]) {
            pairCount++;
            i += 1;
        }
    }
    return pairCount;
}
```

### Dictionary approach

```js
function sockMerchant(n, ar) {
	let pairs = 0;
	const colors = ar.reduce((acc, val) => {
		(!!acc[val] ? acc[val] += 1 : acc[val] = 1)
		return acc;
	}, {});

	Object.keys(colors).forEach( n => {
		let _pair = parseInt( colors[n] / 2 );
		if ( _pair >= 1 ) pairs += _pair;
	});

	return pairs
}

```

#### description
In the reduce callback we setup an accumulator and the current value - doing this on the fly we check to see if our current value exists as a key in our accumulator object, if so we add one to it if not we create the key and initialize it with 1.

Let’s not forget to add the empty object as the second argument and return the accumulator after each iteration.

Now that we have an object with each color as a key ket’s loop through it.

We iterate through each key and we create a local pair variable. We initialize the pair by dividing the colors n key value by 2

Now we can check if the pair value is greater or at least equal to 1. If true we can increment the total pairs value on line 17 with the number of pairs found

We can then simply return the total count after the loop. Running it in the terminal gives us again 3 pairs - If that went too fast let’s add to our console statement and run it again
