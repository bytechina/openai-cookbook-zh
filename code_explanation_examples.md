# 代码解释示例

GPT的代码解释可以应用于许多场景，例如：

- 生成代码中的文档（例如Python docstrings，git提交消息）
- 生成代码之外的文档（例如man页面）
- 交互式代码探索工具
- 通过自然语言向用户传达程序结果

例如，如果你想了解SQL查询，您可以给`code-davinci-002`以下示例提示：

```
一个SQL查询：
"""
SELECT c.customer_id
FROM Customers c
JOIN Streaming s
ON c.customer_id = s.customer_id
WHERE c.signup_date BETWEEN '2020-03-01' AND '2020-03-31'
AND s.watch_date BETWEEN c.signup_date AND DATE_ADD(c.signup_date, INTERVAL 30 DAY)
GROUP BY c.customer_id
HAVING SUM(s.watch_minutes) > 50 * 60
"""

问题：
1. 这个SQL查询是做什么的？
2. 为什么有人对这段时间感兴趣？
3. 一家公司可能对这个SQL查询感兴趣的原因是什么？

答案：
```

[输出]((https://beta.openai.com/playground/p/Sv1VQKbJV1TZKmiTK9r6nlj3))：

```
1. 这个SQL查询找到了在2020年3月注册并在注册后的前30天里观看超过50小时内容的所有客户。
2. 这个时间段很有趣，因为那是新冠疫情大流行的第一个月。
3. 一家公司可能对这个SQL查询感兴趣，因为它可以帮助公司了解疫情如何影响他们的业务。
```

请注意，`code-davinci-002`未经训练，因此通常需要其他结构来帮助引导其输出以及停止序列和停止生成。为了更轻松地运用提示词，请尝试使用`text-davinci-003`。

## 补充说明
OpenAI官方材料中文版翻译及人工智能重要文献编译，可关注微信公众号“量子论”了解最新进展。