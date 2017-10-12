# Two Sum IV in BFS and DFS

I know little about BFS and DFS before. But when I was tackling this leetcode problem, I got a clear idea of how BFS and DFS could be applied to solve the tree, or graph algorithms.

The question description is here:
https://leetcode.com/problems/two-sum-iv-input-is-a-bst/description/

Here are the python solutions in BFS and DFS:

## BFS(iterative)

```python
class Solution:
  def findTarget(self, root, k):
    if not root:
      return False

    bfs, s = [root], set()
    for i in bfs:
      if k - i in s:
        return True
      s.add(i.val)
      if root.left: bfs.append(root.left)
      if root.right: bfs.append(root.right)
    
    return False
```
Brief explanation:

The general idea is to traverse each of the node of the tree, and insert its value to the `bfs` array. If we are able to find a complementary value in the `set`, that means we have already find the pairs.

Note that this is BFS, which is Breadth First Search. We search the values level by level.

## DFS(recursive)

```py
class Solution:
  def dfs(self, node, k):
    if not node:
      return False
    if k - node.val in self.s:
      return True

    self.s.add(node.val)

    return self.dfs(node.left, k) or self.dfs(node.right, k)

  def findTarget(self, root, k):
    self.s = set()
    return self.dfs(root, k)
```

Brief explanation:

The general idea is the same. The only difference is the tranversal sequence. Using recursion, the sequence becomes DFS, Depth First Search.

