# 文本比较示例

[OpenAI API embeddings endpoint](https://beta.openai.com/docs/guides/embeddings)可用于测量文本之间的相关性或相似性。

通过利用GPT-3对文本的理解，这些向量在无监督学习和迁移学习设置中[实现了最先进的结果](https://arxiv.org/abs/2201.10005)。

向量可以用于语义搜索、推荐、群集分析、近似重复检测等等。

要了解更多信息，请阅读OpenAI的博客文章:

* [介绍文本和代码向量 (2022年1月)](https://openai.com/blog/introducing-text-and-code-embeddings/)
* [新的与改进的向量模型 (2022年12月)](https://openai.com/blog/new-and-improved-embedding-model/)

## 语义搜索

向量化可以单独用于搜索，也可以作为大型系统中的一个特征。

使用向量化进行搜索的最简单方法如下:

* 在搜索之前(预计算):
  * 将你的文本语料库分成小于字块限制(对于`text-embedding-ada-002`，限制为8,191个字块)的块。
  * 向量化每个文本块。
  * 将这些向量存储在你自己的数据库或向量搜索的提供程序(如[Pinecone](https://www.pinecone.io)， [Weaviate](https://weaviate.io)或[Qdrant](https://qdrant.tech))。
* 在搜索时(实时计算):
  * 向量化搜索查询。
  * 在你的数据库中找到最相似的向量。
  * 返回前排结果。

使用向量进行搜索的示例在[Semantic_text_search_using_embeddings.ipynb](examples/Semantic_text_search_using_embeddings.ipynb)中。

在更高级的搜索系统里，向量化的余弦相似度可以作为排序搜索结果的许多特征之一。

## 答题

从源文档中获取正确答案是从GPT-3中获得可靠答案的最佳方法。 通过使用上面的语义搜索过程，你可以低成本搜索相关信息的文档语料库，然后将该信息通过提示提供给GPT-3来回答问题。 我们在[Question_answering_using_embeddings.ipynb](examples/Question_answering_using_embeddings.ipynb) 里演示了该方法。

## 推荐

推荐和搜索非常相似，只是输入不是自由格式的文本查询，而是集合中的项目。

我们在 [Recommendation_using_embeddings.ipynb](examples/Recommendation_using_embeddings.ipynb) 中展示了如何使用向量进行推荐的示例。

与搜索类似，这些余弦相似度分数可以单独用于排列项目，也可以作为更大排列算法中的特征。

## 自定义向量

尽管无法调整OpenAI的向量模型权重，但你仍然可以使用训练数据来自定义向量到应用程序。

在[Customizing_embeddings.ipynb](examples/Customizing_embeddings.ipynb)中，我们提供了一种使用训练数据自定义向量的示例方法。该方法的思想是训练一个自定义矩阵，以便通过乘以向量获得新的定制向量。有了良好的训练数据，该自定义矩阵将有助于强调与你的训练标签相关的特征。你可以等效地将矩阵乘法视为（a）向量的修改或（b）用于测量向量之间距离函数的修改。

## 补充说明
OpenAI官方材料中文版翻译及人工智能重要文献编译，可关注微信公众号“量子论”了解最新进展。