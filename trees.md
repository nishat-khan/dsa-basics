# Trees

## Question 1: Invert Binary Tree

**Problem Statement:**

Invert a binary tree.

**Solution:**

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def invert_tree(root):
    """
    Remember to invert the structure, not just the values 
    """
    if root is None:
        return None
    root.left, root.right = root.right, root.left
    invert_tree(root.left)
    invert_tree(root.right)
    return root
```

## Question 2: Validate a Binary Search Tree

**Problem Statement:**

Validate a Binary Search Tree

```python
def validate_binary_search_tree(root):
    """
    Use a helper to check the node value with the limits in the left and right subtrees.
    """
    def helper(node, left_vals=float('-Inf'), right_vals=float('Inf')):
        if not node:
            return True
        if not (left_vals<node.val<right_vals):
            return False
        return (helper(root.left, left_vals, root.val) and helper(root.right, root.val, right_vals))
    
    return helper(root)
```

## Question 3: Tree Traversal

**Problem Statement:**

3 types of tree traversal, in-, pre-, post-order

**Solution:**
```python
def in_order(root):
    """
    In-order = left, root and then right node value
    """
    res = []
    def helper(root, res):
        if not root:
            return 
        helper(root.left, res)
        res.append(root.val)
        helper(root.right, res)
    helper(root, res)
    return res

def pre_order(root):
    """
    Pre-order = Root, left and then right node value
    """
    res = []
    def helper(root, res):
        if not root:
            return 
        res.append(root.val)
        helper(root.left, res)
        helper(root.right, res)
    helper(root, res)
    return res

def post_order(root):
    """
    Post-order = Left, right and then root node value
    """
    res = []
    def helper(root, res):
        if not root:
            return 
        helper(root.left, res)
        helper(root.right, res)
        res.append(root.val)
    helper(root, res)
    return res
```