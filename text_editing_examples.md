# 文本编辑示例

除了 [完成 API 文档][Completion API Docs]，OpenAI 还提供 [编辑 API 文档][Edit API Docs]。了解更多信息：

* [博客文章公告（2022 年 3 月）][GPT3 Edit Blog Post]
* [编辑 API 文档][Edit API Docs]

与仅接受单个文本输入的完成不同，编辑需要两个文本输入：指令和要修改的文本。例如：

指令输入：

```
修正OCR错误。
```

文本输入：

```
Therewassomehostilityntheenergybehindthe researchreportedinPerceptrons....Part of ourdrivecame,aswequiteplainlyacknoweldgednourbook,fromhe facthatfundingndresearchnergywerebeingdissipatedon. . .misleadingttemptsouseconnectionistmethodsnpracticalappli-cations.
```

[输出](https://beta.openai.com/playground/p/5W5W6HHlHrGsLu1cpx0VF4qu)：

```
There was some hostility in the energy behind the research reported in Perceptrons....Part of our drive came, as we quite plainly acknowledged in our book, from the fact that funding and research energy were being dissipated on...misleading attempts to use connectionist methods in practical applications.
```

总的来说，指令可以是命令式的、现在时态的或过去时态的。可以实验一下，看看哪些操作对你最有效。

## 翻译

编辑 API 的一个应用是翻译。

大语言模型在常见语言之间进行翻译非常出色。2021 年，[GPT-3 在 WMT14 英法基准上](https://arxiv.org/abs/2110.05448)创下了一项新的无监督翻译最新记录。

以下是使用编辑文档翻译文本的示例：

指令输入：

```
翻译成法语。
```

文本输入：

```
That's life.
```

[输出](https://beta.openai.com/playground/p/6JWAH8a4ZbEafSDyRsSVdgKr)：

```text
C'est la vie.
```

当然，许多可以通过编辑文档完成的任务也可以由完成文档的方式处理。例如，你可以通过添加指令来请求翻译，如下所示：

```
将以下文本从英语翻译成法语。

英语: That's life.
法语:
```

[输出](https://beta.openai.com/playground/p/UgaPfgjBNTRRPeNcMSNtGzcu):

```
 C'est la vie.
```

翻译提示：

* 最常见的语言性能最佳
* 指令使用最终语言时，性能更好（例如将英语翻译成法语时，使用指令`Traduire le texte de l'anglais au français.`而不是`Translate the following text from English to French.`）
* 反向翻译（如此处所述）也可以增加性能
* 具有冒号和重标点的文本可能会使指令跟随模型出现问题，尤其是如果指令使用冒号（例如“英语: {英语文本} 法语:”）
* 编辑文档有时会在翻译的同时重复原始文本输入，可以进行监视和过滤

在翻译方面，大语言模型特别擅长将其他指令与翻译相结合。例如，您可以要求GPT-3将斯洛文尼亚语翻译成英语，但保持所有的LaTeX排版命令不变。以下文章详细介绍了我们如何将斯洛文尼亚数学书翻译成英语：

[Translation of a Slovenian math book into English](examples/book_translation/translate_latex_book.ipynb)


[Edit API Docs]: https://beta.openai.com/docs/api-reference/edits
[Completion API Docs]: https://beta.openai.com/docs/api-reference/completions
[GPT3 Edit Blog Post]: https://openai.com/blog/gpt-3-edit-insert/

## 补充说明
OpenAI官方材料中文版翻译及人工智能重要文献编译，可关注微信公众号“量子论”了解最新进展。