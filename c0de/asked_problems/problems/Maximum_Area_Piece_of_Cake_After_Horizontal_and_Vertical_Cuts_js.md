## Maximum Area of a Piece of Cake After Horizontal and Vertical Cuts - Storage Optimization

1465. Maximum Area of a Piece of Cake After Horizontal and Vertical Cuts : https://leetcode.com/problems/maximum-area-of-a-piece-of-cake-after-horizontal-and-vertical-cuts/

You are given a rectangular cake of size `h x w` and two arrays of integers `horizontalCuts` and `verticalCuts` where:

- `horizontalCuts[i]` is the distance from the top of the rectangular cake to the `ith` horizontal cut and similarly, and
- `verticalCuts[j]` is the distance from the left of the rectangular cake to the `jth` vertical cut.

Return *the maximum area of a piece of cake after you cut at each horizontal and vertical position provided in the arrays* `horizontalCuts` *and* `verticalCuts`. Since the answer can be a large number, return this **modulo** `109 + 7`.

```js
var maxArea = function(h, w, hc, vc) {
 hc.sort((a,b) => a - b)
vc.sort((a,b) => a - b)
let maxh = Math.max(hc[0], h - hc[hc.length-1]),
    maxv = Math.max(vc[0], w - vc[vc.length-1])
for (let i = 1; i < hc.length; i++)
    maxh = Math.max(maxh, hc[i] - hc[i-1])
for (let i = 1; i < vc.length; i++)
    maxv = Math.max(maxv, vc[i] - vc[i-1])
return BigInt(maxh) * BigInt(maxv) % 1000000007n
};



//MY SOLUTION
var maxArea = function(h, w, hc, vc) {
 hc.sort((a,b) => a - b)
    vc.sort((a,b) => a - b)
    var maxHeight = vc[0];
    var maxWidth = hc[0];
    hc.push(h);
    vc.push(w);

    for (var i = 0; i < vc.length -1; i++) {
        console.log(vc[i], maxHeight);
        if (vc[i+1] - vc[i] > maxHeight) {
            maxHeight = vc[i+1] - vc[i];
        }
    }
    for (var i = 0; i < hc.length - 1; i++) {
        console.log(hc[i], maxWidth);
        if (hc[i+1] - hc[i] > maxWidth) {
            maxWidth = hc[i+1] - hc[i];
        }
    }
var mod = 1e9+7;
return BigInt(maxHeight) * BigInt(maxWidth) % BigInt(mod);
};
```

