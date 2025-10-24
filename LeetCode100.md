## leetcode

### 1、题目描述就是：给你一个 **非空** 整数数组 `nums` ，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。

#### 我最开始想到的方法是使用unordered_map但是这个方法存在的不足就是空间复杂度达到了O(n);但是这个方法无论是三个还是四个都通用。

#### chat给出的方法是使用异或，关于异或就是计组中涉及到的知识，相同为0，不同为1；对应的符号是	^;初始的时候0 ^ a = a

#### 根据这个推广每个数字出现 **k 次**，只有一个数字出现 **一次** 时：位计数（bit counting）算法

```
模运算：10 % 4=2
int singleNumber(vector<int>& nums, int k) {
    int ans = 0;
    for (int i = 0; i < 32; i++) {      // 遍历每一位
        int bitSum = 0;
        for (int n : nums) {
            if ((n >> i) & 1) bitSum++; // 统计该位上的1
        }
        if (bitSum % k != 0) {          // 如果余数不为0
            ans = ans | (1 << i);            // 该位属于只出现一次的数
        }
    }
    return ans;
}
ans | (1 << i)实际上是按位或运算
```



### 2、题目描述：给定一个大小为 `n` 的数组 `nums` ，返回其中的多数元素。多数元素是指在数组中出现次数 **大于** `⌊ n/2 ⌋` 的元素。(Boyer–Moore 投票算法)

```c++

int majorityElement(vector<int>& nums) {
    int count = 0;
    int candidate = 0;
    for (int i = 0; i < nums.size(); i++) {
        if (count == 0) {
            candidate = nums[i];
        }
        if (candidate == nums[i]) {
            count++;
        } else {
            count--;
        }
    }
    return candidate;
}

```

### 3、背包问题与BFS的问题比较

部分背包问题可以使用BFS解决，但是BFS的效率没有DP效率高



```
 int mid = left + (right - left) / 2; // 防止溢出
```

