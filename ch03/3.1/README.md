# Exercises for Section 3.1

### 3.1.1

根据 3.1.2 节中的讨论，将下面的 C++ 程序划分为正确的词素序列。哪些词素
应该有相关联的词法值？应该具有什么值？

```
float limitedSquare(x){float x;
  /* returns x-squared, nut never more than 100 */
  return (x <= -10.0 || x >= 10.0) ? 100 : x*x;
}
```

#### Answer

```
<float> <id, limitedSquare> <(> <id, x> <)> <{>
    <float> <id, x>
    <return> 
    <(> 
      <id, x> <op, "<="> <num, -10.0> <op, "||"> <id, x> <op, ">=") <num, 10.0>
      <op, "?"> <num, 100> <op, ":"> <id, x> <op, "*"> <id, x>
    <)>
  <}>
```

### 3.1.2

像 HTML 或 XML 之类的标记语言不同于传统的程序设计语言，它们要么包含有很多
标点符号（标记），如 HTML，要么使用由用户自定义的标记集合，如 XML。而且
标记还可以带有参数。请指出如何把如下的 HTML 文档划分成适当的词素序列。
哪些词素应该具有相关联的词法值？应该具有什么样的值？

```
Here is a photo of <b>my house</b>;
<p><img src="house.gif"/><br/>
see <a href="morePix.html">More Picture</a> if you
liked that one.</p>
```

#### Answer

```
<text, "Here is a photo of"> <nodestart, b> <text, "my house"> <nodeend, b>
<nodestart, p> <selfendnode, img> <nodeattr, src, "house.gif"> <selfendnode, br>
<text, "see"> <nodestart, a> <nodeattr, href, "morePix.html"> <text, "More Picture"> <nodeend, a>
<text, "if you liked that one."> <nodeend, p>
```
