# 代码编辑示例

OpenAI的[edits](https://openai.com/blog/gpt-3-edit-insert/)端点对于编辑代码特别有用。

与自动补全不同，编辑需要两个输入：要编辑的文本和指令。

例如，如果您想要编辑一个Python函数，您可以提供该函数的文本以及像“添加文档字符串”这样的指令。

`code-davinci-edit-001`的示例文本输入：

```python
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

```text
添加文档字符串
```

```text
使用Python 3.9约定添加类型
```

```text
提高运行时间
```

```text
添加一个测试。
```

```text
将其翻译成JavaScript（或Rust或Lisp或您喜欢的任何语言）
```

在改进运行时间并将其转换为JavaScript之后，示例输出：

```JavaScript
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

正如您所看到的，`code-davinci-edit-001`成功将函数的运行时间从指数级降到了线性级，并完成了从Python到JavaScript的转换。

在[OpenAI Playground](https://beta.openai.com/playground?mode=edit&model=code-davinci-edit-001)中尝试使用`code-davinci-edit-001`进行代码编辑。