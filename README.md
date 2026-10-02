# Trees
# 🌳 Binary Tree & Binary Search Tree – LeetCode Solutions

This repository contains my **Java solutions for Binary Tree and Binary Search Tree problems on LeetCode**.

The solutions mainly use **recursion** to perform tree traversal and BST operations.

---

## 📌 Problems Covered

| # | Problem | LeetCode |
|---|---|---|
| 1 | Inorder Traversal | **94** |
| 2 | Binary Tree Preorder Traversal | **144** |
| 3 | Binary Tree Postorder Traversal | **145** |
| 4 | Count Complete Tree Nodes | **222** |
| 5 | Search in a Binary Search Tree | **700** |
| 6 | Insert into a Binary Search Tree | **701** |

---

# 1. Inorder Traversal

### LeetCode 94 – Binary Tree Inorder Traversal

**Traversal order:** Left → Root → Right

```java
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();

        if (root == null)
            return result;

        result.addAll(inorderTraversal(root.left));
        result.add(root.val);
        result.addAll(inorderTraversal(root.right));

        return result;
    }
}
```

---

# 2. Preorder Traversal

### LeetCode 144 – Binary Tree Preorder Traversal

**Traversal order:** Root → Left → Right

```java
class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> r = new ArrayList<>();

        if (root == null)
            return r;
        else {
            r.add(root.val);
            r.addAll(preorderTraversal(root.left));
            r.addAll(preorderTraversal(root.right));
        }

        return r;
    }
}
```

---

# 3. Postorder Traversal

### LeetCode 145 – Binary Tree Postorder Traversal

**Traversal order:** Left → Right → Root

```java
class Solution {
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> r = new ArrayList<>();

        if (root == null)
            return r;
        else {
            r.addAll(postorderTraversal(root.left));
            r.addAll(postorderTraversal(root.right));
            r.add(root.val);
        }

        return r;
    }
}
```

---

# 4. Height / Number of Nodes

### LeetCode 222 – Count Complete Tree Nodes

This recursive solution counts the total number of nodes in the tree.

```java
class Solution {
    public int countNodes(TreeNode root) {
        if (root == null)
            return 0;
        else
            return 1 + countNodes(root.left) + countNodes(root.right);
    }
}
```

> **Note:** Although this is listed under the tree basics/height section, the LeetCode problem itself asks for the **number of nodes**, not the height.

---

# 5. Search in a Binary Search Tree

### LeetCode 700 – Search in a Binary Search Tree

For a BST:
- If `val < root.val` → search the **left subtree**
- If `val > root.val` → search the **right subtree**
- If `val == root.val` → return the current node

```java
class Solution {
    public TreeNode searchBST(TreeNode root, int val) {
        if (root == null || root.val == val)
            return root;

        if (val < root.val)
            return searchBST(root.left, val);
        else
            return searchBST(root.right, val);
    }
}
```

---

# 6. Insert into a Binary Search Tree

### LeetCode 701 – Insert into a Binary Search Tree

The new value is inserted as a **leaf node** while maintaining the BST property.

```java
class Solution {
    public TreeNode insertIntoBST(TreeNode root, int val) {
        if (root == null)
            return new TreeNode(val);

        if (val < root.val)
            root.left = insertIntoBST(root.left, val);
        else
            root.right = insertIntoBST(root.right, val);

        return root;
    }
}
```

---

## 🧠 Key Concepts

### Binary Tree Traversals

```text
Inorder   → Left → Root → Right
Preorder  → Root → Left → Right
Postorder → Left → Right → Root
```

### Binary Search Tree

For every node in a BST:

```text
Left subtree  <  Root  <  Right subtree
```

This property makes searching and insertion more efficient than in a general binary tree.

---

## 💻 Language

**Java**

## 📚 Platform

**LeetCode**

---

⭐ More Binary Tree and BST solutions will be added as I continue practicing.
