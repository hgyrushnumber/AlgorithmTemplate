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
初始化二维数组：
vector<vector<int>> vec(3, vector<int>(4, 0)) 创建3行4列全0矩阵
只初始化行数，不初始化列数
vector<vector<int>> vec(3, vector<int>());  // 显式初始化空子vector

```

#### 找最大值

```
 int maxVal = *max_element(nums.begin(), nums.end());
```

## unordered_set哈希集

### 初始化

```
unordered_set<string> fruits = {"apple", "banana", "orange"};
也和unordered_map差不多，只不过没有key，value，他能快速找到set中是否存在该元素
```

### 检查set中是否存在该元素

```
fruits.count()
```

### queue队列

#### 初始化

```
queue<type> name;
```

#### 经典用法

```

```

