# STL 容器（Standard Template Library Container）

## unordered_map 哈希表

### definition

```
unordered_map<type1,type2> mp;
其中type1是键的数据类型，type2是值的类型
```

### traverse

```
引用遍历：更快、更节省内存；修改 p 会直接影响 mp
for (auto &p : mp) {
    cout << p.first << " : " << p.second << endl;
}
值拷贝遍历:拷贝每个元素（复制一份）;只读、不修改时
for (auto p : mp) {
    cout << p.first << " : " << p.second << endl;
}
```



## vector数组

#### 初始化

```
vector<int> dp(n+1,0);
n+1代表的是长度，后面那个0代表的是值
```

#### 找最大值

```
 int maxVal = *max_element(nums.begin(), nums.end());
```

