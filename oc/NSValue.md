# NSValue
##本小节知识点:
1. 【理解】NSValue基本概念
2. 【理解】常见结构体的包装
3. 【理解】任意数据的包装
---

##1.NSValue基本概念
- NSNumber是NSValue的子类, 但NSNumber只能包装数字类型

- NSValue可以包装任意值
    + 因此, 可以用NSValue将结构体包装后,加入NSArray\NSDictionary中

---

##2. 常见结构体的包装
- 为了方便 结构体 和NSValue的转换,Foundation提供了以下方法
- 将结构体包装成NSValue对象

```objc
+ (NSValue *)valueWithPoint:(NSPoint)point;
+ (NSValue *)valueWithSize:(NSSize)size;
+ (NSValue *)valueWithRect:(NSRect)rect;
```

- 从NSValue对象取出之前包装的结构体

```
- (NSPoint)pointValue;
- (NSSize)sizeValue;
- (NSRect)rectValue;
```
---

##3.任意数据的包装
- NSValue提供了下列方法来包装任意数据

```objc
+ (NSValue *)valueWithBytes:(const void *)value objCType:(const char *)type;
+ value参数 : 所包装数据的地址
+ type参数 : 用来描述这个数据类型的字符串, 用@encode指令来生成

- 从NSValue中取出所包装的数据
- (void)getValue:(void *)value;
```


---
