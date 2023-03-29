# Redis

**[Redis](https://redis.io)** 通过[RediSearch模块](https://github.com/RediSearch/RediSearch) 获得对于向量搜索的一流支持。RediSearch是一个[Redis模块](https://redis.io/modules)，它为Redis提供查询、二级索引、全文搜索和向量搜索。为了使用RediSearch，您首先需要在Redis数据上声明索引。然后您可以使用RediSearch查询语言来查询您的数据。

### 特点

RediSearch使用压缩的反向索引，以达到快速索引和低内存占用。RediSearch索引通过提供精确短语匹配、模糊匹配、数值过滤等许多特性，增强了Redis。例如：

* Redis哈希中多个字段的全文索引
* 增量索引，无性能丢失
* 向量相似度搜索
* 文档排名（使用[tf-idf](https://en.wikipedia.org/wiki/Tf%E2%80%93idf)，可选用户提供权重）
* 字段加权
* 使用AND、OR和NOT运算符的复杂布尔查询
* 前缀匹配、模糊匹配和精确短语查询
* 支持[双音节音标匹配](https://redis.io/docs/stack/search/reference/phonetic_matching/)
* 自动完成建议（带有模糊前缀建议）
* 基于词干化的查询扩展[许多语言](https://redis.io/docs/stack/search/reference/stemming/)（使用[Snowball](http://snowballstem.org/)）
* 支持中文分词和查询（使用[Friso](https://github.com/lionsoul2014/friso)）
* 数值过滤和范围
* 使用[Redis geospatial indexing](/commands/georadius)的地理空间搜索
* 强大的聚合引擎
* 支持所有utf-8编码的文本
* 检索完整文档、选定字段或仅文档ID
* 对结果排序（比如按创建日期）
* 通过RedisJSON支持JSON

### Clients考虑到 Redis 周围的生态系统很大，你很可能会发现你需要的语言的客户端库。你可以使用任何标准的 Redis 客户端库来运行 RediSearch 命令，但最好使用一个包装 RediSearch API 的库。以下是一些例子，但你可以在这里找到更多的客户端库。

| 项目 | 语言 | 许可证 | 作者 | 星数 |
|----------|---------|--------|---------|-------|
| [jedis][jedis-url] | Java | MIT | [Redis][redis-url] | ![Stars][jedis-stars] |
| [redis-py][redis-py-url] | Python | MIT | [Redis][redis-url] | ![Stars][redis-py-stars] |
| [node-redis][node-redis-url] | Node.js | MIT | [Redis][redis-url] | ![Stars][node-redis-stars] |
| [nredisstack][nredisstack-url] | .NET | MIT | [Redis][redis-url] | ![Stars][nredisstack-stars] |
| [redisearch-go][redisearch-go-url] | Go | BSD | [Redis][redisearch-go-author] | [![redisearch-go-stars]][redisearch-go-url] |
| [redisearch-api-rs][redisearch-api-rs-url] | Rust | BSD | [Redis][redisearch-api-rs-author] | [![redisearch-api-rs-stars]][redisearch-api-rs-url] |

[redis-url]: https://redis.com

[redis-py-url]: https://github.com/redis/redis-py
[redis-py-stars]: https://img.shields.io/github/stars/redis/redis-py.svg?style=social&amp;label=Star&amp;maxAge=2592000
[redis-py-package]: https://pypi.python.org/pypi/redis

[jedis-url]: https://github.com/redis/jedis
[jedis-stars]: https://img.shields.io/github/stars/redis/jedis.svg?style=social&amp;label=Star&amp;maxAge=2592000
[Jedis-package]: https://search.maven.org/artifact/redis.clients/jedis

[nredisstack-url]: https://github.com/redis/nredisstack
[nredisstack-stars]: https://img.shields.io/github/stars/redis/nredisstack.svg?style=social&amp;label=Star&amp;maxAge=2592000
[nredisstack-package]: https://www.nuget.org/packages/nredisstack/

[node-redis-url]: https://github.com/redis/node-redis
[node-redis-stars]: https://img.shields.io/github/stars/redis/node-redis.svg?style=social&amp;label=Star&amp;maxAge=2592000。[node-redis-package]：https://www.npmjs.com/package/redis

[redis-om-python-url]：https://github.com/redis/redis-om-python
[redis-om-python-author]：https://redis.com
[redis-om-python-stars]：https://img.shields.io/github/stars/redis/redis-om-python.svg？style=social&amp;label=Star&amp;maxAge=2592000

[redisearch-go-url]：https://github.com/RediSearch/redisearch-go
[redisearch-go-author]：https://redis.com
[redisearch-go-stars]：https://img.shields.io/github/stars/RediSearch/redisearch-go.svg？style=social&amp;label=Star&amp;maxAge=2592000

[redisearch-api-rs-url]：https://github.com/RediSearch/redisearch-api-rs
[redisearch-api-rs-author]：https://redis.com
[redisearch-api-rs-stars]：https://img.shields.io/github/stars/RediSearch/redisearch-api-rs.svg？style=social&amp;label=Star&amp;maxAge=2592000


### 部署选项

有许多使用Redis和RediSearch的部署方式。最简单的方法是使用Docker，但也有许多其他可能的部署选项，例如:

- [Redis Cloud](https://redis.com/redis-enterprise-cloud/overview/)
- 云市场：[AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-e6y7ork67pjwg?sr=0-2&ref_=beagle&applicationId=AWSMPContessa)，[Google Marketplace](https://console.cloud.google.com/marketplace/details/redislabs-public/redis-enterprise?pli=1)，或[Azure Marketplace](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/garantiadata.redis_enterprise_1sp_public_preview?tab=Overview)
- 在本地：[Redis Enterprise Software](https://redis.com/redis-enterprise-software/overview/)
- Kubernetes：[Redis Enterprise Software on Kubernetes](https://docs.redis.com/latest/kubernetes/)
- [Docker（RediSearch）](https://hub.docker.com/r/redislabs/redisearch)
- [Docker（Redis Stack）](https://hub.docker.com/r/redis/redis-stack)


### 集群支持RediSearch有一个分布式集群版本，可在数百台服务器上扩展到数十亿个文档。目前，分布式RediSearch作为[Redis Enterprise Cloud](https://redis.com/redis-enterprise-cloud/overview/)和[Redis Enterprise Software](https://redis.com/redis-enterprise-software/overview/)的一部分可用。

有关更多信息，请参见[Redis Enterprise上的RediSearch](https://redis.com/modules/redisearch/)。

### 示例

- [产品搜索](https://github.com/RedisVentures/redis-product-search) - 电子商务产品搜索（图像和文本）
- [使用DocArray / Jina的产品推荐](https://github.com/jina-ai/product-recommendation-redis-docarray) - 基于内容的产品推荐示例，使用Redis和DocArray。
- [RecSys中的Redis VSS](https://github.com/RedisVentures/Redis-Recsys) - 3个端到端的Redis和NVIDIA Merlin推荐系统架构。
- [Azure OpenAI嵌入式问答](https://github.com/ruoccofabrizio/azure-open-ai-embeddings-qna) - 在Azure上使用OpenAI和Redis作为问答服务。
- [ArXiv论文搜索](https://github.com/RedisVentures/redis-arXiv-search) - arXiv学术论文的语义搜索


### 更多资源

有关如何使用Redis作为向量数据库的更多信息，请查看以下资源：

- [Redis向量相似性文档](https://redis.io/docs/stack/search/reference/vectors/) - Redis Vector Search的官方文档。
- [Redis-py搜索文档](https://redis.readthedocs.io/en/latest/redismodules.html#redisearch-commands) - RediSearch的Redis-py客户端库文档。
- [从基础知识到生产的向量相似性搜索](https://mlops.community/vector-similarity-search-from-basics-to-production/) - VSS和Redis作为VectorDB的入门博客文章。
- [AI驱动的文档搜索](https://datasciencedojo.com/blog/ai-powered-document-search/) - 博客文章涵盖了基于AI的文档搜索用例和架构。- [向量数据库基准测试](https://jina.ai/news/benchmark-vector-search-databases-with-one-million-data/) - Jina AI VectorDB基准测试，对比Redis和其他数据库。