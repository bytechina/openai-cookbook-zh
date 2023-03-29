# 文本编辑示例

除了 [完成 API 端点][Completion API Docs]，OpenAI 还提供 [编辑 API 端点][Edit API Docs]。了解更多信息：

* [博客文章公告（2022 年 3 月）][GPT3 Edit Blog Post]
* [编辑 API 文档][Edit API Docs]

与仅接受单个文本输入的完成不同，编辑需要两个文本输入：指令和要修改的文本。例如：

指令输入：

```text
修正OCR错误。
```

文本输入：

```text
在感知器中报告的研究背后存在某种敌意......我们的部分推动力量来自于我们在书中明确承认的事实，即资金和研究能量正在分散用于......试图在实际应用中使用联系主义方法的误导尝试。
```

[输出](https://beta.openai.com/playground/p/5W5W6HHlHrGsLu1cpx0VF4qu)：

```text
在感知器中报告的研究背后存在某种敌意......我们的部分推动力量来自于我们在书中明确承认的事实，即资金和研究能量正在分散用于......试图在实际应用中使用联系主义方法的误导尝试。
```

总的来说，指令可以是命令式的、现在时态的或过去时态的。实验一下，看看什么对您的用例最有效。

## 翻译

编辑 API 的一个应用是翻译。

大型语言模型在常见语言之间进行翻译非常出色。2021 年，[GPT-3 在 WMT14 英法基准上](https://arxiv.org/abs/2110.05448)创下了一项新的无监督翻译最新记录。

以下是使用编辑端点翻译文本的示例：

指令输入：

```text
翻译成法语。
```

文本输入：

```text
That's life.
```

[输出](https://beta.openai.com/playground/p/6JWAH8a4ZbEafSDyRsSVdgKr)：

```text
C'est la vie.
```

当然，许多可以通过编辑端点完成的任务也可以由完成端点完成。例如，您可以通过添加指令来请求翻译，如下所示：

```text。
格式：仅返回已翻译的内容，不包括原始文本。将以下文本从英语翻译成法语。

英语: That's life.
法语:
```

[Output](https://beta.openai.com/playground/p/UgaPfgjBNTRRPeNcMSNtGzcu):

```text
 C'est la vie.
```

翻译提示：

* 最常见的语言性能最佳
* 我们发现当指令使用最终语言时（例如将英语翻译成法语时，使用指令“将文本从英语翻译成法语。”而不是“Translate the following text from English to French.”），性能更好
* 反向翻译（如此处所述）也可以增加性能
* 具有冒号和重标点的文本可能会使指令跟随模型出现问题，尤其是如果指令使用冒号（例如“英语: {英语文本} 法语:”）
* 编辑端点有时会在翻译的同时重复原始文本输入，可以进行监视和过滤

在翻译方面，大型语言模型特别擅长将其他指令与翻译相结合。例如，您可以要求GPT-3将斯洛文尼亚语翻译成英语，但保持所有的LaTeX排版命令不变。以下笔记本详细介绍了我们如何将斯洛文尼亚数学书翻译成英语：

[Translation of a Slovenian math book into English](examples/book_translation/translate_latex_book.ipynb)


[Edit API Docs]: https://beta.openai.com/docs/api-reference/edits
[Completion API Docs]: https://beta.openai.com/docs/api-reference/completions
[GPT3 Edit Blog Post]: https://openai.com/blog/gpt-3-edit-insert/