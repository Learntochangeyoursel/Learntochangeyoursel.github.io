## 1. 小小双指针（移除元素）

问题描述：给你一个数组 `nums` 和一个值 `val`，你需要 原地 移除所有数值等于` val`
的元素。元素的顺序可能发生改变。然后返回 `nums` 中与
`val` 不同的元素的数量。

假设 `nums` 中不等于 val 的元素数量为 `k`，要通过此题，您需要执行以下操作：

更改 `nums` 数组，使 nums 的前` k` 个元素包含不等于 `val` 的元素。`nums` 的其余元素和 `nums` 的大小并不重要。
返回 `k`。

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

题目描述：给你一个 非严格递增排列 的数组 `nums` ，请你 原地 删除重复出现的元素，使每个元素 只出现一次 ，返回删除后数组的新长度。元素的
相对顺序 应该保持 一致 。然后返回`nums`中唯一元素的个数。
考虑 `nums `的唯一元素的数量为`k` ，你需要做以下事情确保你的题解可以被通过：

更改数组 `nums `，使 nums 的前`k` 个元素包含唯一元素，并按照它们最初在 `nums `中出现的顺序排列。`nums` 的其余元素与 `nums`
的大小不重要。

返回 k 。

`解题思路：`首先注意数组是有序的，那么重复的元素一定会相邻。

要求删除重复元素，实际上就是将不重复的元素移到数组的左侧。

考虑用 2 个指针，一个在前记作 p，一个在后记作 q，算法流程如下：

1.比较 p 和 q 位置的元素是否相等。

如果相等，q 后移 1 位
如果不相等，将 q 位置的元素复制到 p+1 位置上，p 后移一位，q 后移 1 位
重复上述过程，直到 q 等于数组长度。

返回 p + 1，即为新数组长度。


题解1
```java
  public int removeDuplicates(int[] nums) {
    if(nums == null || nums.length == 0) return 0;
    //两兄弟
    int p = 0;
    int q = 1;
    //弟弟在家总跟着哥哥跑，直到把家里跑完
    while(q < nums.length){
    //弟弟追上哥哥时，哥哥总先行一步一
        if(nums[p] != nums[q]){
            nums[p + 1] = nums[q];
            p++;
        }
        q++;
    }
    return p + 1;
```

## 删除有序数组中的重复项 II

题目描述：一个有序数组 `nums` ，请你 `原地 `删除重复出现的元素，使得出现次数超过两次的元素只出现两次 ，返回删除后数组的新长度。

不要使用额外的数组空间，你必须在 原地 修改输入数组 并在使用 `O(1)` 额外空间的条件下完成。

题解1：
```java 
   public int removeDuplicates(int[] nums) {
        if (nums == null || nums.length <= 2) {
            return nums.length;
        }
        
        int insertPos = 2; // 插入位置，因为前两个元素总是有效的
        for (int i = 2; i < nums.length; i++) {
            if (nums[i] != nums[insertPos - 2]) {
                nums[insertPos] = nums[i];
                insertPos++;
            }
        }
        return insertPos;   //返回数组新的长度
    }
```