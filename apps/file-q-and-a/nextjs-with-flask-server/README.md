# 使用Next.js和Flask的File Q&A

File Q&A是一个Web应用程序，可以让你在文件中查找答案。你可以上传文件并提问与它们的内容相关的问题，应用程序将使用嵌入和GPT从最相关的文件中生成答案。

## 需求

运行该应用程序需要：

- 一个OpenAI API密钥。你可以在此处创建新的API密钥[here](https://beta.openai.com/account/api-keys)。
- 一个Pinecone API密钥和索引名称。你可以在此处创建新的帐户和索引[here](https://www.pinecone.io/)。
- Python 3.7或更高版本和pipenv用于Flask服务器。
- Node.js和npm用于Next.js客户端。

## 设置和开发

### 服务器

填写config.yaml文件并加入你的Pinecone API密钥、索引名称和环境。

运行Flask服务器：

```
cd server
bash script/start "<你的OPENAI_API_KEY>"
```

### 客户端

导航到客户端目录并安装Node依赖项：

```
cd client
npm install
```

运行Next.js客户端：

```
cd client
npm run dev
```

使用浏览器打开[http://localhost:3000](http://localhost:3000)以查看应用程序。

## 限制

该应用程序有时可能会生成不在文件中的答案，或者幻想有没有上传的文件存在。