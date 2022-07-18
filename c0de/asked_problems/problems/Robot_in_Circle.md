## Robot In Circle

1041. Robot Bounded In Circle - LEET CODE

On an infinite plane, a robot initially stands at `(0, 0)` and faces north. Note that:

- The **north direction** is the positive direction of the y-axis.
- The **south direction** is the negative direction of the y-axis.
- The **east direction** is the positive direction of the x-axis.
- The **west direction** is the negative direction of the x-axis.

The robot can receive one of three instructions:

- `"G"`: go straight 1 unit.
- `"L"`: turn 90 degrees to the left (i.e., anti-clockwise direction).
- `"R"`: turn 90 degrees to the right (i.e., clockwise direction).

The robot performs the `instructions` given in order, and repeats them forever.

Return `true` if and only if there exists a circle in the plane such that the robot never leaves the circle.

```js
    /**
    * Robo will move in circle if below conditions are true after executing the instructions
    * 1. position remains same (OR)
    * 2. direction is changed
    **/
    
    // initial position and direction
	/** dirX == 0 means not facing X axis direction
	* dirX == 1 means facing X axis positive direction (right side)
	* dirX == -1 means facing X axis negative direction (left side)
	* same for dirY
	**/
    let dirX = 0, dirY = 1;
    let x = 0, y = 0;
    
    for (let c of instructions) {
        if (c === 'G') {
            // change the position in the existing direction
            x += dirX;
            y += dirY;
        } else if (c === 'L') {
            // turn left
            // position remains same,
            // direction changes by 90%
            // dirX, dirY are swaped and dirX will become negative
            const temp = dirX;
            dirX = -1 * dirY;
            dirY = temp;
        } else { // 'R'
            // turn right
            // position remains same,
            // direction changes by 90%
            // dirX, dirY are swaped and dirY will become negative
            const temp = dirX;
            dirX = dirY;
            dirY = -1 * temp;
        }
    }
    //retain false if position remains same or direction is changes
    return (x === 0 && y === 0) || dirX !== 0 || dirY !== 1;
};
```

