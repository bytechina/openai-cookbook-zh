# Answers、Classification、和 Search 的废除

2021年，OpenAI在Answers、Classification和Search的beta版中发布了专门的端点。

虽然这些专用端点很方便，但是有两个缺点：

1. 这些专用端点被取得更好结果的技术所取代。
2. 这些专用端点更难以定制和优化以满足个人用例。

因此，**Answers、Classifications和Search端点正在被弃用**。

## 弃用时间表

对于那些没有使用这些端点的人，除了不再有访问权限外，其他事情都不会改变。

**对于这些端点的现有用户，访问将持续到2022年12月3日。** 在这个日期之前，我们强烈建议开发人员切换到产生更好结果的更新技术。

## 如何过渡

我们编写了指南和代码示例，以从不推荐使用的API端点过渡到更好的方法。

### Answers

[指南：如何过渡到新的Answers端点](https://help.openai.com/en/articles/6233728-answers-transition-guide)

* 选项1：过渡到基于嵌入的搜索 **(推荐)**
  * 示例代码：[Semantic_text_search_using_embeddings.ipynb](../examples/Semantic_text_search_using_embeddings.ipynb)

* 选项2：重新实现Answers端点功能
  * 示例代码：[answers_functionality_example.py](answers_functionality_example.py)

### Classification

[指南：如何过渡到新的Classifications端点](https://help.openai.com/en/articles/6272941-classifications-transition-guide)

* 选项1：过渡到fine-tuning **(推荐)**
  * 示例代码：[Fine-tuned_classification.ipynb](../examples/Fine-tuned_classification.ipynb)

* 选项2：过渡到嵌入
  * 示例代码：[Semantic_text_search_using_embeddings.ipynb](../examples/Semantic_text_search_using_embeddings.ipynb)

* 选项3：重新实现Classifications端点功能。* 示例代码: [classification_functionality_example.py](classification_functionality_example.py)

### 搜索

[指南：如何过渡到非搜索端点](https://help.openai.com/en/articles/6272952-search-transition-guide)

* 选项1：过渡到基于嵌入的搜索 **(推荐)**
  * 示例代码：[Semantic_text_search_using_embeddings.ipynb](../examples/Semantic_text_search_using_embeddings.ipynb)
* 选项2：重新实现搜索端点功能
  * 示例代码：[search_functionality_example.py](search_functionality_example.py)