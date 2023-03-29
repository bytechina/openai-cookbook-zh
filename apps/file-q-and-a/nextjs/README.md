# 文件问答

文件问答是一个 [Next.js](https://nextjs.org/) 应用程序，可使用 OpenAI API 在您的文件中查找答案。您可以上传文件并询问与其内容相关的问题，应用程序将使用嵌入和 GPT 从最相关的文件中生成答案。

## 要求

要运行此应用程序，您需要一个 OpenAI API 密钥。您可以在[此处](https://beta.openai.com/account/api-keys)创建一个新的 API 密钥。

## 设置

如果您尚未安装 Node.js 和 npm，请从[https://nodejs.org/en/download/](https://nodejs.org/en/download/)中安装它们。

在终端中，导航到此示例应用程序的 `nextjs` 目录，然后安装依赖项：

```
npm install
```

将 .env.local.example 文件复制到 .env.local 文件中，并填写 OpenAI API 密钥字段。

## 开发

运行开发服务器：

```
npm run dev
```

使用您的浏览器打开 [http://localhost:3000](http://localhost:3000) 查看应用程序。

## 部署

您可以将应用程序部署到 [Vercel](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme)——Next.js 创建者的平台上。有关更多详细信息，请查看 [Next.js 部署文档](https://nextjs.org/docs/deployment)。

## 限制

上传的文件和生成的嵌入在浏览器刷新时不会持续存在。如果您想存储更多嵌入，我们建议使用一个矢量数据库（例如 Pinecone、Weaviate、Milvus、Qdrant、Redis、FAISS 等）。此演示的 `nextjs-with-flask-server` 版本使用 Pinecone 矢量数据库。

应用程序有时可能会生成不在文件中的答案，或者产生关于未上传的文件存在的幻觉。