`https://frontend.boom.camp/week-4/3-day-18/1-toy-problem`

**Instruction**: No reverse built in functions are allowed, e.g `[1, 1, 2, 3, 5].reverse()`

**Tip**: Use sorting algorithm (e.g: Bubble sort), or manual sorting


Solutions:

Basic:

```
//Solution#1: .reverse()
function reverseFib(n){
  let arr = [];
  for (let i = 0; i < n; i++){
    if (i < 2){
      arr.push(1)
    } else{
      arr.push(arr[i-1] + arr[i-2])
    }
  }
  return arr.reverse()
}

console.log(reverseFib(6))
``` 


``` 
//Solution#2: Using sorting algorithm: Bubble sort
#!/usr/bin/env node
function fibResult(n){
  let fibResult = [];
  for (let i = 0; i < n; i++){
    if (i < 2){              //i = 0,1:  We cannot add single number so, add 1 to array
      fibResult.push(1)
    } else{
      fibResult.push(fibResult[i-1] + fibResult[i-2])
    }
  }
  return fibResult
}

/**
//Interpretation

[1]                   1 = 1 (First iteration added to array)

[ [1, 1] ]            1+1 = 2
[ 1, [1, 2] ]         1+2 = 3  
[ 1, 1, [2, 3] ]      2+3 = 5
[ 1, 1, 2, [3, 5] ]   3+5 = 8

**/

function reverseFib(lists){
  let itemsArray = fibResult(lists)
   do {
    swapped = false;
    for (let i = 0; i < itemsArray.length; i++) {
      if (itemsArray[i] < itemsArray[i + 1]) {            // Compare:                       1 < 2 = true
        let tmp = itemsArray[i];                          // Assign:                        tmp = 1
        itemsArray[i] = itemsArray[i + 1];                // Move next element from first:  From [1 , ..] as [2, ..]
        itemsArray[i + 1] = tmp;                          // Move first element as last:    From [.., 2] into [..,1]
        swapped = true;								      // Done first element!

        console.log("Position(s): ", tmp, itemsArray[i])  // Element: itemsArray[i] = 2, as swapped element
      }
    }
  } while (swapped);

  return itemsArray;
}

reverseFib(6) // [ 1, 1, 2, 3, 5, 8 ]

//[ 1, [1, 2], 3, 5, 8 ] = Position: [1,2]
//[ 1, [2, 1], 3, 5, 8 ]

//[ 1, 2, [1, 3], 5, 8 ] = Position: [1,3]
//[ 1, 2, [3, 1], 5, 8 ]

//[ 1, 2, 3, [1, 5], 8 ] = Position: [1,5]
//[ 1, 2, 3, [5, 1], 8 ]

//[ 1, 2, 3, 5, [1, 8] ] = Position: [1,8]
//[ 1, 2, 3, 5, [8, 1] ]

//[ [1, 2], 3, 5, 8, 1 ] = Position: [1,2]
//[ [2, 1], 3, 5, 8, 1 ]

//[ 2, [1, 3], 5, 8, 1 ] = Position: [1,3]
//[ 2, [3, 1], 5, 8, 1 ]

//[ 2, 3, [1, 5], 8, 1 ] = Position: [1,5]
//[ 2, 3, [5, 1], 8, 1 ]

//[ 2, 3, 5, [1, 8], 1 ] = Position: [1,8]
//[ 2, 3, 5, [8, 1], 1 ]

//[ [2, 3], 5, 8, 1, 1 ] = Position: [2,3]
//[ [3, 2], 5, 8, 1, 1 ]

//[ 3, [2, 5], 8, 1, 1 ] = Position: [2,5]
//[ 3, [5, 2], 8, 1, 1 ]

//[ 3, 5, [2, 8], 1, 1 ] = Position: [2,8]
//[ 3, 5, [8, 2], 1, 1 ]

//[ [3, 5], 8, 2, 1, 1 ] = Position: [3,5]
//[ [5, 3], 8, 2, 1, 1 ]

//[ 5, [3, 8], 2, 1, 1 ] = Position: [3,8]
//[ 5, [8, 3], 2, 1, 1 ]

//[ [5, 8], 3, 2, 1, 1 ] = Position: [5,8]
//[ [8, 5], 3, 2, 1, 1 ]

``` 


Advance:
```
//TODO:
```