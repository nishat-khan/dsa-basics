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

def reverse_linked_list(head):
    """
    Use a prev pointer to create the pattern from the beginning
    """
    prev = None
    while head:
        temp = head.next
        head.next = prev
        prev = head
        head = temp
    return prev

Todo: Reverse k nodes in a linked list
``` 