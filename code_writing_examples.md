# 编写代码示例

GPT-3 能够写代码和文本。

以下是 `code-davinci-002` 写的 SQL 查询示例：

```
SQL 表（和列）：
* Customers（customer_id，signup_date）
* Streaming（customer_id，video_id，watch_date，watch_minutes）

一个高效的 SQL 查询语句，它列出了在 2020 年 3 月注册并在首个 30 天内观看超过 50 小时视频的客户：
```
[输出](https://beta.openai.com/playground/p/r2mw99cANoa0TJHok725CeaC):

```
SELECT c.customer_id
FROM Customers c
JOIN Streaming s
ON c.customer_id = s.customer_id
WHERE c.signup_date BETWEEN '2020-03-01' AND '2020-03-31'
AND s.watch_date BETWEEN c.signup_date AND DATE_ADD(c.signup_date, INTERVAL 30 DAY)
GROUP BY c.customer_id
HAVING SUM(s.watch_minutes) > 50 * 60

```

`code-davinci-002` 能够从变量名中推断出相关单位，例如它推断出 `watch_minutes` 是以分钟为单位的，因此在与 50 小时进行比较之前需要乘以 60 进行换算。

为了更轻松地编写提示词，你还可以尝试 `text-davinci-003`。

## 补充说明
OpenAI官方材料中文版翻译及人工智能重要文献编译，可关注微信公众号“量子论”了解最新进展。