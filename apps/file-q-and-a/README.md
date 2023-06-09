# 文件问答

文件问答是一个 [Next.js](https://nextjs.org/) 应用程序，使用 OpenAI API 以便你在文件中找到答案。你可以上传文件并询问与其内容相关的问题，该应用程序将使用嵌入和 GPT 从最相关的文件生成答案。

此存储库包含应用程序的两个版本：

- `/nextjs`：一个独立的 Next.js 应用程序，它将嵌入在浏览器中进行本地存储。您需要一个 OpenAI API 密钥才能使用此应用程序。请阅读其 [README](./nextjs/README.md) 了解更多信息。
- `/nextjs-with-flask-server`：一个 Next.js 应用程序，它使用 Flask 服务器作为代理来访问 OpenAI API，使用 Pinecone 作为矢量数据库来存储嵌入。您需要 OpenAI API 密钥和 Pinecone API 密钥才能使用此应用程序。请阅读其 [README](./nextjs-with-flask-server/README.md) 了解更多信息。

要运行应用程序的任何版本，请按照各自子目录中的 README.md 文件中的说明操作。

## 工作原理

上传文件后，从文件中提取文本。然后将此文本分为较短的文本块，并为每个文本块创建一个嵌入。当用户提出问题时，为问题创建嵌入，并执行相似度搜索以找到与问题最相似（即与问题嵌入具有最高的余弦相似性）的文件块嵌入。然后，向完成端点发出 API 调用，提示包括问题和最相关的文件块。如果答案可以在提取中找到，则生成模型会在文件块中给出答案。

## 限制

该应用程序有时可能会生成不在文件中的答案，或出现关于未上传的文件存在的幻觉。