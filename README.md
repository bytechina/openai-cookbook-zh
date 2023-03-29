# OpenAI Cookbook

OpenAI Cookbook 分享使用 [OpenAI API] 完成常见任务的示例代码。

要运行这些示例，您需要 OpenAI 帐户和关联的 API 密钥。

大多数代码示例都是用 Python 编写的，但这些概念也可以应用在任何语言中。

## 最近添加的 🆕 ✨

- [如何为 ChatGPT 模型格式化输入](examples/How_to_format_inputs_to_ChatGPT_models.ipynb)[2023年3月1日]
- [使用向量数据库和Redis进行嵌入搜索](https://github.com/openai/openai-cookbook/tree/main/examples/vector_databases/redis)[2023年2月15日]
- [通过向量化进行网站问答](https://github.com/openai/openai-cookbook/tree/main/apps/web-crawl-q-and-a)[2023年2月11日]
- [通过向量化进行文件问答](https://github.com/openai/openai-cookbook/tree/main/apps/file-q-and-a)[2023年2月11日]
- [在 Weights＆Biases 中向量可视化](https://github.com/openai/openai-cookbook/blob/main/examples/Visualizing_embeddings_in_W%26B.ipynb)[2023年2月9日]
- [使用 Pinecone 检索增强型生成式问答](https://github.com/openai/openai-cookbook/blob/main/examples/vector_databases/pinecone/Gen_QA.ipynb)[2023年2月8日]

## 指南和示例

- API用法
  - [如何处理速率限制](examples/How_to_handle_rate_limits.ipynb)
    - [避免命中速率限制的示例并行处理脚本](examples/api_request_parallel_processor.py)
  - [如何使用 tiktoken 计算字块数量](examples/How_to_count_tokens_with_tiktoken.ipynb)
  - [如何进行流式交互](examples/How_to_stream_completions.ipynb)
- ChatGPT
  - [如何对 ChatGPT 模型格式化输入](examples/How_to_format_inputs_to_ChatGPT_models.ipynb)
- GPT-3
  - [指南：如何使用大语言模型](how_to_work_with_large_language_models.md)
  - [指南：提高可靠性的技术](techniques_to_improve_reliability.md)
  - [如何使用多步提示编写单元测试](examples/Unit_test_writing_using_a_multi-step_prompt.ipynb)
  - [文本写作示例](text_writing_examples.md)
  - [文本解释示例](text_explanation_examples.md)
  - [文本编辑示例](text_editing_examples.md)
  - [代码编写示例](code_writing_examples.md)
  - [代码解释示例](code_explanation_examples.md)
  - [代码编辑示例](code_editing_examples.md)
- 向量化
  - [文本比较示例](text_comparison_examples.md)
  - [如何获取向量](examples/Get_embeddings.ipynb)
  - [基于向量化进行问答](examples/Question_answering_using_embeddings.ipynb)
  - [基于向量化进行语义搜索](examples/Semantic_text_search_using_embeddings.ipynb)
  - [基于向量化进行推荐](examples/Recommendation_using_embeddings.ipynb)
  - [聚类向量](examples/Clustering.ipynb)
  - [在2D中向量可视化](examples/Visualizing_embeddings_in_2D.ipynb) 或 [在3D中向量可视化](examples/Visualizing_embeddings_in_3D.ipynb)
  - [向量化长文本](examples/Embedding_long_inputs.ipynb)
- 微调GPT-3
  - [指南：微调GPT-3实现文本分类的最佳实践](https://docs.google.com/document/d/1rqj7dkuvl7Byd5KQPUJRxc19BJt8wo0yHNwK84KfU3Q/edit)
  - [微调分类](examples/Fine-tuned_classification.ipynb)
- DALL-E
  - [如何使用DALL-E生成和编辑图像](examples/dalle/Image_generations_edits_and_variations_with_DALL-E.ipynb)
- Azure OpenAI(来自Microsoft Azure的备用API)
  - [如何通过Azure OpenAI使用ChatGPT](examples/azure/chat.ipynb)
  - [如何从Azure OpenAI中获取交互信息](examples/azure/completions.ipynb)
  - [如何从Azure OpenAI中获得向量信息](examples/azure/embeddings.ipynb)
  - [如何通过Azure OpenAI微调GPT-3](examples/azure/finetuning.ipynb)
- 应用程序
  - [针对文件的问答](apps/file-q-and-a/)
  - [关于网页抓取的问答](apps/web-crawl-q-and-a)

## 相关资源

除了这里的代码示例，您还可以从以下资源中了解有关[OpenAI API]的信息：

- 在[OpenAI Playground](https://beta.openai.com/playground)中尝试API
- 在[OpenAI文档](https://platform.openai.com/docs/introduction)中阅读有关API的信息
- 在[OpenAI社区论坛](https://community.openai.com/top?period=monthly)中讨论API
- 在[OpenAI帮助中心](https://help.openai.com/en/)中寻求帮助
- 查看[OpenAI示例](https://beta.openai.com/examples)中的例子
- 通过[ChatGPT](https://chat.openai.com/)免费试用研究成果
- 通过[OpenAI Blog](https://openai.com/blog/)获取最新动态

## 参与贡献

如果您想要查看示例或指南，请随时在[issues page](https://github.com/bytechina/openai-cookbook-zh/issues)上提出建议。