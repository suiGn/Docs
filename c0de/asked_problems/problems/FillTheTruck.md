## Fill the Truck:

1710. Maximum Units on a Truck - LEET CODE

You are assigned to put some amount of boxes onto **one truck**. You are given a 2D array `boxTypes`, where `boxTypes[i] = [numberOfBoxesi, numberOfUnitsPerBoxi]`:

- `numberOfBoxesi` is the number of boxes of type `i`.
- `numberOfUnitsPerBoxi` is the number of units in each box of the type `i`.

You are also given an integer `truckSize`, which is the **maximum** number of **boxes** that can be put on the truck. You can choose any boxes to put on the truck as long as the number of boxes does not exceed `truckSize`.

Return *the **maximum** total number of **units** that can be put on the truck.*

```js
 var maximumUnits = function(boxTypes, truckSize) {
            var sortedBox = boxTypes.sort((a,b)=>{
        return b[1]-a[1];
    });

    var remainSize = truckSize;
    var totleUnits = 0;

    for (let i = 0; i < sortedBox.length; i++) {
        if (remainSize - sortedBox[i][0] > 0){
            remainSize -= sortedBox[i][0];
            totleUnits += sortedBox[i][0] * sortedBox[i][1];
        }else if (remainSize - sortedBox[i][0] === 0 || remainSize - sortedBox[i][0] < 0) {      
            totleUnits += remainSize * sortedBox[i][1];
            remainSize = 0;
        }
    }
    return totleUnits;
};
```


