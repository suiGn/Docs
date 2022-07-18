## Two Sum

Write a function that takes a list of numbers and a `target` number, and then returns the number of unique pairs that add up to the `target` number.

```js
var mergeTwoLists = function(list1, list2) {
 let head = {};
  curr = head;
  while (list1 && list2) {
    if (list1.val > list2.val) {
      curr.next = list2;
      list2 = list2.next;
    } else {
      curr.next = list1;
      list1 = list1.next;
    }
	curr = curr.next;
  }

  if (list1) {
    curr.next = list1;
  }

  if (list2) {
    curr.next = list2;
  }

  return head.next || null;
};
```

## 