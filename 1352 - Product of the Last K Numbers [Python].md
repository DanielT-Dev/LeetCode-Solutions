# Statement: [Link to Leetcode](https://leetcode.com/problems/product-of-the-last-k-numbers/description/?envType=daily-question&envId=2025-02-14)
# Solution:
```python
class ProductOfNumbers:

    def __init__(self):
        self.stream = []
        self.right = 0
        self.left = 0
        self.prefix_product = [1]
        self.zero_prefix_sums = [0]

    def add(self, num: int) -> None:
        self.stream.append(num)
        current_prefix_sum = self.zero_prefix_sums[self.right]
        currnet_product = self.prefix_product[self.right]
        self.right += 1
        self.left += 1

        # Prefix Sum Method
        if num == 0:
            current_prefix_sum += 1
        else:
            currnet_product *= num

        self.zero_prefix_sums.append(current_prefix_sum)
        self.prefix_product.append(currnet_product)
        

    def getProduct(self, k: int) -> int:
        
        if self.zero_prefix_sums[self.right] - self.zero_prefix_sums[self.right - k] > 0:
            return 0

        return self.prefix_product[self.right] // self.prefix_product[self.right - k]


# Your ProductOfNumbers object will be instantiated and called as such:
# obj = ProductOfNumbers()
# obj.add(num)
# param_2 = obj.getProduct(k)
```
