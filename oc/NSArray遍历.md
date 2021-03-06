# NSArray 遍历
##本小节知识点:
1. 【理解】NSArray的下标遍历
2. 【理解】NSArray的快速遍历
3. 【理解】NSArray 使用block进行遍历
4. 【理解】NSArray给所有元素发消息

---


##1.NSArray的下标遍历

```objc
    NSArray *arr = @[p1, p2, p3, p4, p5];
    for (int i = 0; i < arr.count; ++i) {
        Person *p = arr[i];
        [p say];
    }
```
---

##2.NSArray的快速遍历

```objc
    NSArray *arr = @[p1, p2, p3, p4, p5];
   for (Person *p in arr) {
        [p say];
    }
```
---


##3.NSArray 使用block进行遍历

```objc
    [arr enumerateObjectsUsingBlock:^(id obj, NSUInteger idx, BOOL *stop) {
        NSLog(@"obj = %@, idx = %lu", obj, idx);
        Person *p = obj;
        [p say];
    }];
```
---

##4.NSArray给所有元素发消息
- 让集合里面的所有元素都执行aSelector这个方法
    + \- (void)makeObjectsPerformSelector:(SEL)aSelector;
    + \- (void)makeObjectsPerformSelector:(SEL)aSelector withObject:(id)argument;

```objc
    // 让数组中所有对象执行这个方法
    // 注意: 如果数组中的对象没有这个方法会报错
//    [arr makeObjectsPerformSelector:@selector(say)];
    [arr makeObjectsPerformSelector:@selector(eat:) withObject:@"bread"];
```
