## Task

Create a Polygon class that has the following properties:

    * A constructor that takes an array of integer values describing the lengths of the polygon's sides.
    * A perimeter() method that returns the polygon's perimeter.

Locked code in the editor tests the Polygon constructor and the perimeter method.

#### Note: The perimeter method must be lowercase and spelled correctly.

Consider the following code:
```
// Create a polygon with side lengths 3, 4, and 5
let triangle = new Polygon([3, 4, 5]);

// Print the perimeter
console.log(triangle.perimeter());
```
```js
/*
 * Implement a Polygon class with the following properties:
 * 1. A constructor that takes an array of integer side lengths.
 * 2. A 'perimeter' method that returns the sum of the Polygon's side lengths.
 */

class Polygon {
    constructor(height) {
        var polygonPerimeter = 0;
        for (var index in height) {
            polygonPerimeter += height[index];
        }
        this.myPerimeter = polygonPerimeter
    }

    perimeter() {
        return this.myPerimeter;
    }
}
