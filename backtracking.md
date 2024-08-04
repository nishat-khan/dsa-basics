# Questions solvable by Backtracking 
## Question 1: Find the word in a 2D character board
**Problem Statement:**
Given a 2D board of characters, return True if the given word is found.
```python
def search_word_in_board(board, word):
    ROWS, COLUMNS = len(board), len(board[0])
    visited = set()

    def dfs(r, c, i):
        if i == len(word):
            return True
        if (
            board[r][c]!=word[i] or
            r >= ROWS or c >= COLUMNS or 
            r < 0 or c < 0 or 
            (r,c) in visited
        ):
            return False
        
        visited.add((r,c))
        res = (
            dfs(r+1, c, i+1) or
            dfs(r-1, c, i+1) or
            dfs(r, c-1, i+1) or
            dfs(r, c+1, i+1) 
        )
        visited.remove((r,c))
        return res
    for r in range(ROWS):
        for c in range(COLUMNS):
            if dfs(r, c, 0): return True
    return False
```