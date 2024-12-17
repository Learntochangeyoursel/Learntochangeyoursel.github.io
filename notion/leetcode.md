## 1. 小小双指针（移除元素）

问题描述：给你一个数组 nums 和一个值 val，你需要 原地 移除所有数值等于 val 的元素。元素的顺序可能发生改变。然后返回 nums 中与
val 不同的元素的数量。
假设 nums 中不等于 val 的元素数量为 k，要通过此题，您需要执行以下操作：
更改 nums 数组，使 nums 的前 k 个元素包含不等于 val 的元素。nums 的其余元素和 nums 的大小并不重要。
返回 k。
题解1：

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int left = 0;
        //遍历数组
        for(int right = 0;right < nums.length;right++){
            //左指针等于右指针时，元素前移
            if(nums[right] != val){
                nums[left] = nums[right];
                left++;
            }
        }
        return left;
    }
}
```
题解2：
```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int left = 0;
        int right = nums.length;
        //两指针向中间遍历
        while (left < right) {
            if (nums[left] == val) {
                nums[left] = nums[right - 1];
                right--;
            } else {
                left++;
            }
        }
        return left;
    }
}

```
## 2. 删除有序数组中的重复项
题目描述：给你一个 非严格递增排列 的数组 `nums` ，请你 原地 删除重复出现的元素，使每个元素 只出现一次 ，返回删除后数组的新长度。元素的 相对顺序 应该保持 一致 。然后返回`nums`中唯一元素的个数。
考虑 `nums `的唯一元素的数量为`k` ，你需要做以下事情确保你的题解可以被通过：

更改数组 `nums `，使 nums 的前`k` 个元素包含唯一元素，并按照它们最初在 `nums `中出现的顺序排列。`nums` 的其余元素与 `nums` 的大小不重要。

返回 k 。