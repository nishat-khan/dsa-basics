Linked lists are linear linked nodes

1. Uni directional 
2. Bi directional

```python
class LinkedListNode:
    def __init__(self, val, next=None):
        self.val = val
        self.next = next

def print_linked_list(head):
    """
    head is a pointer to the head node of linked list
    Use a temp pointer so that head pointer is not disturbed
    """
    temp = head
    while not temp:
        print(temp.val)
        temp = temp.next

Todo: Reverse k nodes in a linked list
``` 