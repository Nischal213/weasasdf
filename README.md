# Simple code for a binary tree along with traversal algorithms

class BinaryTreeNode:

    def __init__(self, data) -> None:
        self.left = None
        self.data = data
        self.right = None

    def add_item(self, data):
        if data < self.data:
            if self.left is None:
                self.left = BinaryTreeNode(data)
            else:
                self.left.add_item(data)
        elif data > self.data:
            if self.right is None:
                self.right = BinaryTreeNode(data)
            else:
                self.right.add_item(data)

    def pre_order_traversal(self):
        elements = []
        elements.append(self.data)
        if self.left:
            elements += self.left.pre_order_traversal()
        if self.right:
            elements += self.right.pre_order_traversal()
        return elements

    def in_order_traversal(self):
        elements = []
        if self.left:
            elements += self.left.in_order_traversal()
        elements.append(self.data)
        if self.right:
            elements = elements + self.right.in_order_traversal()
        return elements

    def post_order_traversal(self):
        elements = []
        if self.left:
            elements += self.left.post_order_traversal()
        if self.right:
            elements += self.right.post_order_traversal()
        elements.append(self.data)
        return elements


root = BinaryTreeNode(56)
root.add_item(32)
root.add_item(28)
root.add_item(44)
root.add_item(62)
root.add_item(58)
root.add_item(88)

