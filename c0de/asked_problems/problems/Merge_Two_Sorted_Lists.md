## Merge Two Sorted Lists

21. Merge Two Sorted Lists: https://leetcode.com/problems/merge-two-sorted-lists/

Merge two sorted linked lists and return it as a new sorted list. The new list should be made by splicing together the nodes of the given two lists.

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists in a one **sorted** list. The list should be made by splicing together the nodes of the first two lists.

Return *the head of the merged linked list*.

```js
//HACKER RANK SOLUTION

function mergeLists(head1, head2) {
    if (!head1) return head2
    if (!head2) return head1
    if(head1.data < head2.data){
        return {"data": head1.data, "next": mergeLists(head1.next, head2)}
    }else{
        return {"data": head2.data, "next": mergeLists(head1, head2.next)} 
    }
}

//Other solution
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

