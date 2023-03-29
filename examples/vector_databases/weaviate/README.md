"# Weaviate <> OpenAI

[​Weaviate](https://weaviate.io) 是一个开源的向量搜索引擎([文档](https://weaviate.io/developers/weaviate) - [Github](https://github.com/weaviate/weaviate)), 可以存储并搜索OpenAI嵌入式和数据对象。该数据库允许您进行相似性搜索、混合搜索（将多种搜索技术，如基于关键字和向量搜索组合在一起）和生成式搜索（如问答）。Weaviate还支持各种基于OpenAI的模块(e.g. [`text2vec-openai`](https://weaviate.io/developers/weaviate/modules/retriever-vectorizer-modules/text2vec-openai), [`qna-openai`](https://weaviate.io/developers/weaviate/modules/reader-generator-modules/qna-openai))，允许您快速高效地进行向量化和查询数据。

您可以通过以下三种方式来运行Weaviate（包括OpenAI模块，如果需要的话）：

1. 在Docker容器中开源运行（[示例](./docker-compose.yml)）
2. 使用Weaviate云服务（[开始](https://weaviate.io/developers/weaviate/quickstart/installation#weaviate-cloud-service)）
3. 在Kubernetes集群中（[了解更多](https://weaviate.io/developers/weaviate/installation/kubernetes)）

### 示例

该文件夹包含各种Weaviate和OpenAI示例。

| 名称 | 描述 | 语言 | Google Colab |
| --- | --- | --- | --- |
| [Weaviate和OpenAI入门](./getting-started-with-weaviate-and-openai.ipynb) | 使用Weaviate中的OpenAI向量化模块(`text2vec-openai`)进行*语义向量搜索*的简单入门 | Python Notebook | [链接](https://colab.research.google.com/drive/1RxpDE_ruCnoBB3TfwAZqdjYgHJhtdwhK) |
| [使用Weaviate和OpenAI进行混合搜索](./hybrid-search-with-weaviate-and-openai.ipynb) | 使用Weaviate中的OpenAI向量化模块(`text2vec-openai`)进行*混合搜索*的简单入门 | Python Notebook | [链接](https://colab.research.google.com/drive/1E75BALWoKrOjvUhaznJKQO0A-B1QUPZ4) |"| [使用 Weaviate 和 OpenAI 进行问题回答](./question-answering-with-weaviate-and-openai.ipynb) | 使用 Weaviate (`qna-openai`) 中的 OpenAI Q&A 模块进行 *问题回答 (Q&A)* 的简单入门 | Python Notebook | [链接](https://colab.research.google.com/drive/1pUerUZrJaknEboDxDxsuf3giCK0MJJgm) |
| [Docker-compose 示例](./docker-compose.yml) | 具有所有 OpenAI 模块的 Docker-compose 文件 | Docker |