# 代码编辑示例

OpenAI的[编辑功能](https://openai.com/blog/gpt-3-edit-insert/)对于编辑代码特别有用。

与完成功能不同，编辑需要两个输入：要编辑的文本和指令。

例如，如果你想编辑一个Python函数，你可以提供该函数的文本以及像“添加文档字符串”这样的指令。

`code-davinci-edit-001`的示例输入文本：

```
def tribonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    elif n == 2:
        return 1
    elif n == 3:
        return 2
    else:
        return tribonacci(n-1) + tribonacci(n-2) + tribonacci(n-3)
```

示例指令输入：

```
添加文档字符串
```

```
使用Python 3.9的约定添加类型
```

```
提高运行时间
```

```
添加一个测试
```

```
将其翻译成JavaScript（或Rust或Lisp或你喜欢的任何语言）
```

在改进运行时间并将其转换为JavaScript之后，示例输出：

```
function tribonacci(n) {
  let a = 0;
  let b = 1;
  let c = 1;
  for (let i = 0; i < n; i++) {
    [a, b, c] = [b, c, a + b + c];
  }
  return a;
}
```

正如你所看到的，`code-davinci-edit-001`成功将函数的运行时间从指数级降到了线性级，并完成了从Python到JavaScript的转换。

在[OpenAI Playground](https://beta.openai.com/playground?mode=edit&model=code-davinci-edit-001)中尝试使用`code-davinci-edit-001`进行代码编辑。

## 补充说明
OpenAI官方材料中文版翻译及人工智能重要文献编译，可关注微信公众号“量子论”了解最新进展。