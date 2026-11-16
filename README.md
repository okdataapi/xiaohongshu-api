# 小红书数据接口（Xiaohongshu / RedNote API）：笔记、评论、博主、热点、蒲公英

**小红书数据 API · 小红书笔记搜索 · 小红书评论采集 · 小红书博主数据 · 小红书热点 · 蒲公英达人报价。**

这个仓库是 [okdata](https://okdata.online/zh/?src=gh-xiaohongshu-api) 的小红书接口示例：30 个接口在线可用，一个 API Key 调用，按次计费（$0.02 起），参数错误这类还没请求数据源就被拦下的调用不扣费。不用登录平台账号，不用 Cookie，不开浏览器，所以也不存在账号被风控的问题。

[免费注册拿 Key（送 $0.1 试用额度）](https://okdata.online/zh/signup/?src=gh-xiaohongshu-api) · [全部接口文档](https://okdata.online/zh/apis/?src=gh-xiaohongshu-api) · [接入 AI（MCP）](https://okdata.online/zh/mcp/?src=gh-xiaohongshu-api)

## 接口清单

| 接口 | 说明 | 价格 | 路径 |
|---|---|---|---|
| [小红书笔记搜索](https://okdata.online/zh/apis/xiaohongshu/notes/search/) | 按关键词搜笔记，可按最新或最热，带图片和作者。 | $0.02 / 次 | `GET /v1/xiaohongshu/notes/search` |
| [小红书笔记详情](https://okdata.online/zh/apis/xiaohongshu/notes/get/) | 一篇笔记的全文、全部图片（视频笔记只给封面，不含视频文件链接）、点赞、收藏和评论数。 | $0.02 / 次 | `GET /v1/xiaohongshu/notes/get` |
| [小红书笔记评论](https://okdata.online/zh/apis/xiaohongshu/notes/comments/list/) | 笔记下的评论，带点赞和回复数。 | $0.02 / 次 | `GET /v1/xiaohongshu/notes/comments/list` |
| [小红书博主信息](https://okdata.online/zh/apis/xiaohongshu/users/get/) | 博主的粉丝、获赞与收藏、笔记数和简介。 | $0.02 / 次 | `GET /v1/xiaohongshu/users/get` |
| [小红书博主笔记列表](https://okdata.online/zh/apis/xiaohongshu/users/notes/list/) | 博主发布的笔记，从新到旧。 | $0.02 / 次 | `GET /v1/xiaohongshu/users/notes/list` |
| [小红书热点话题](https://okdata.online/zh/apis/xiaohongshu/trends/list/) | 小红书当前推荐给创作者的热点话题，带热度。 | $0.02 / 次 | `GET /v1/xiaohongshu/trends/list` |
| [小红书蒲公英达人搜索](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/search/) | 在小红书官方达人广场「蒲公英」按笔记内容或昵称找达人，可按粉丝数和笔记类型筛选，按粉丝、互动、阅读或报价排序。返回粉丝数、日常笔记阅读和互动中位数、内容类目，以及图文和视频笔记报价（元）。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/search` |
| [小红书蒲公英达人详情](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/get/) | 达人在蒲公英上的资料：粉丝数、获赞与收藏、阅读和互动中位数、内容和特色标签，以及图文和视频笔记的报价（元）和是否开放接单。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/get` |
| [小红书商城商品搜索](https://okdata.online/zh/apis/xiaohongshu/shop/products/search/) | 按关键词搜小红书商城商品：标题、现价和原价（元）、图片和店铺。销量不以数字显示。 | $0.02 / 次 | `GET /v1/xiaohongshu/shop/products/search` |
| [小红书商城商品评价](https://okdata.online/zh/apis/xiaohongshu/shop/products/reviews/list/) | 小红书商城商品买家评价的第一页：星级、内容、购买的款式、晒图和点赞数。App 不提供后续页。 | $0.02 / 次 | `GET /v1/xiaohongshu/shop/products/reviews/list` |
| [小红书图片搜索](https://okdata.online/zh/apis/xiaohongshu/images/search/) | 按关键词搜图片，每条是一张图片和它所在的笔记：原图、笔记标题、正文、作者、点赞、评论和收藏。这里没有分享数，笔记详情里有。 | $0.02 / 次 | `GET /v1/xiaohongshu/images/search` |
| [小红书评论回复](https://okdata.online/zh/apis/xiaohongshu/comments/replies/list/) | 按一级评论 ID 和所在笔记 ID 取评论下的回复：内容、回复者、点赞和发布时间。评论不存在时和没有回复一样，返回空结果。 | $0.02 / 次 | `GET /v1/xiaohongshu/comments/replies/list` |
| [小红书话题笔记](https://okdata.online/zh/apis/xiaohongshu/topics/notes/list/) | 话题（标签）页下最热的笔记，一次约 10 篇：标题、正文、作者、点赞、评论、收藏、分享、图片和话题标签。 | $0.02 / 次 | `GET /v1/xiaohongshu/topics/notes/list` |
| [小红书话题详情](https://okdata.online/zh/apis/xiaohongshu/topics/get/) | 按话题页 ID 取一个话题（标签）：名称、简介、浏览量、页面上显示的讨论人数和话题链接。 | $0.02 / 次 | `GET /v1/xiaohongshu/topics/get` |
| [小红书账号搜索](https://okdata.online/zh/apis/xiaohongshu/users/search/) | 按关键词找账号：用户 ID、小红书号、昵称、头像、粉丝数（App 显示的约数）和官方认证。 | $0.02 / 次 | `GET /v1/xiaohongshu/users/search` |
| [小红书商城商品详情](https://okdata.online/zh/apis/xiaohongshu/shop/products/get/) | 按商品 ID 取小红书商城的一件商品：标题、现价和原价（元）、图片、已售件数、评分、评价数和店铺。看到的是 App 海外用户的商品页，促销可能和国内用户看到的不同。 | $0.02 / 次 | `GET /v1/xiaohongshu/shop/products/get` |
| [小红书搜索联想词](https://okdata.online/zh/apis/xiaohongshu/keywords/related/) | 在小红书搜索框输入关键词时给出的联想词，按它的顺序排，一次约 10 个。只有词和名次，没有指数。 | $0.02 / 次 | `GET /v1/xiaohongshu/keywords/related` |
| [小红书视频笔记详情（视频地址）](https://okdata.online/zh/apis/xiaohongshu/videos/get/) | 按 ID 或链接取一篇视频笔记：标题、正文、作者、点赞、评论、收藏和分享，加上视频文件地址、时长和封面、平台生成的字幕（有的话），以及是否为报备的品牌合作笔记。只用于视频笔记；图文笔记用笔记详情。 | $0.02 / 次 | `GET /v1/xiaohongshu/videos/get` |
| [小红书蒲公英关键词搜索指数](https://okdata.online/zh/apis/xiaohongshu/pgy/keywords/history/) | 关键词在小红书上最近约三个月（时间范围由平台定）的逐日搜索指数，带每天的相关笔记数、曝光、阅读和互动。搜索指数是平台的度量，不是搜索次数。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/keywords/history` |
| [小红书蒲公英关联词](https://okdata.online/zh/apis/xiaohongshu/pgy/keywords/related/) | 小红书用户搜一个词之前和之后还会搜的词，一次最多约 100 个，各带相关度名次、搜索指数、相关笔记数和阅读量。用来拓词选题。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/keywords/related` |
| [小红书蒲公英达人粉丝画像](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/audience/get/) | 按蒲公英达人 ID 取粉丝画像：性别、年龄段、省份、城市、兴趣和手机品牌各段的占比，以及数据所属日期。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/audience/get` |
| [小红书蒲公英达人数据表现](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/metrics/) | 按蒲公英达人 ID 取近 30 或 90 天日常或合作笔记的表现：笔记数和视频笔记数，曝光、阅读、互动和涨粉中位数，互动率、完播率，点赞过百和过千的笔记占比，超过多少同类达人，以及曝光和阅读的来源占比。完整视图另有逐篇笔记数据和约半年前笔记的长尾阅读。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/metrics` |
| [小红书蒲公英达人笔记](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/notes/list/) | 按蒲公英达人 ID 取一页蒲公英「笔记案例」：阅读、点赞、收藏、外溢进店人数、是否合作及合作品牌。可只看合作笔记或跨域合作笔记、只看图文或视频，按最新、阅读最多或互动最多排，按内容特征或类目筛，阅读数可只算自然流量。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/notes/list` |
| [小红书蒲公英达人粉丝趋势](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/followers/history/) | 按蒲公英达人 ID 取近 30 或 60 天每天的粉丝数，以及这段时间的净增和增长率。看达人是在稳定涨粉，还是突然掉粉或刷粉。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/followers/history` |
| [小红书蒲公英相似达人](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/related/) | 按蒲公英达人 ID 取蒲公英推荐的相似达人：ID、昵称、小红书号、所在地、内容类目、粉丝数、阅读和互动中位数，以及图文和视频笔记报价（元）。一页 4 位，通常共几位到几十位。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/related` |
| [小红书蒲公英内容广场热门笔记](https://okdata.online/zh/apis/xiaohongshu/pgy/notes/trending/) | 蒲公英内容广场的热门笔记榜：小红书热门、产品种草、电商推广、蒲公英合作、客资收集、电商热门、种草直达、应用推广 8 个榜，看整榜或只看和某些词有关的，近 3、7、14 或 30 天，可只要图文或视频。每篇有标题、发布时间、阅读、点赞、收藏、评论、图片，以及达人的 ID、昵称和粉丝数。每个榜只有前 100 篇。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/notes/trending` |
| [小红书蒲公英达人合作成本概览](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/costs/metrics/) | 按蒲公英达人 ID 取预估合作成本：图文和视频笔记的预估 CPM、单次互动、单次阅读和单个进店成本，各带优于多少同类达人；单篇笔记曝光、阅读、互动和进店的中位数；近 30 天粉丝增长和发文数；邀约回复率、「好联系」和「活跃」标记；蒲公英标注的亮点、内容类目占比和合作过的行业。可看日常或合作笔记口径。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/costs/metrics` |
| [小红书蒲公英达人粉丝概览](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/followers/metrics/) | 按蒲公英达人 ID 取粉丝质量：粉丝数和近 30 天净增，以及活跃、互动、阅读和购买粉丝各有多少、占全部粉丝的比例和超过多少同类达人。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/followers/metrics` |
| [小红书蒲公英达人核心数据趋势](https://okdata.online/zh/apis/xiaohongshu/pgy/creators/costs/history/) | 按蒲公英达人 ID 取近 30 或 90 天每天的核心数据：CPM、单次互动、单次阅读和单个进店成本，单篇笔记曝光、阅读、互动和进店人数的中位数，以及整段的汇总。可看日常或合作笔记口径。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/creators/costs/history` |
| [小红书蒲公英笔记数据](https://okdata.online/zh/apis/xiaohongshu/pgy/notes/get/) | 按笔记 ID 取蒲公英给品牌看的这篇笔记数据：曝光、阅读、点赞、收藏、评论、分享和带来的关注，报备的合作品牌，品牌组件的点击率档位，以及标题、正文、图片、发布时间和达人。蒲公英只有自己达人的笔记数据，没有数据的笔记返回不存在。 | $0.04 / 次 | `GET /v1/xiaohongshu/pgy/notes/get` |

## 快速开始

1. 在 [okdata 控制台](https://okdata.online/zh/signup/?src=gh-xiaohongshu-api) 用邮箱注册，拿到 `okd_` 开头的 Key。
2. 调一次接口：

```bash
export OKDATA_API_KEY=okd_...
curl -G "https://api.okdata.online/v1/xiaohongshu/notes/search" \
  -H "Authorization: Bearer $OKDATA_API_KEY" \
  --data-urlencode 'query=防晒霜 推荐'
```

Python 版在 [examples/quickstart.py](examples/quickstart.py)（只用标准库，会顺带演示翻页）：`python3 examples/quickstart.py`。

返回统一的结构：列表在 `data.items`，下一页用 `page.next_cursor` 传回 `cursor`，这次扣了多少钱在 `meta.billing.amount`，平台不提供的字段为 null 并在 `meta.unavailable` 里写明原因。

## 让 AI 直接用（MCP）

Claude Code：

```bash
claude mcp add --transport http --scope user okdata https://api.okdata.online/mcp --header "Authorization: Bearer $OKDATA_API_KEY"
```

Cursor、Cherry Studio、WorkBuddy 等支持远程 MCP 的客户端：

```json
{
  "mcpServers": {
    "okdata": {
      "url": "https://api.okdata.online/mcp",
      "headers": {
        "Authorization": "Bearer okd_..."
      }
    }
  }
}
```

接好以后直接用中文说需求，比如「小红书笔记搜索：防晒霜 推荐」。AI 会先用免费的 `find`、`describe` 找接口和看价格，再用 `call` 取数据。

## 常见问题

**要登录平台账号吗？** 不用。数据是公开内容，okdata 在服务端获取，你的账号完全不参与。

**怎么收费？** 每个接口单独定价，表里写的就是一次调用的价格；按条计费的接口按实际返回条数算。请求到了数据源的调用，返回为空、查不到或出错也照常计费（按条计费的按 1 条算）；参数错误这类还没请求数据源就被拦下的不扣费。新账号送 $0.1 试用额度，之后按需充值，没有订阅。价格页：https://okdata.online/zh/pricing/

**和官方开放平台有什么区别？** 官方开放平台只能读授权给你的账号自己的数据，而且要企业资质和审核；这里是平台上任何人都能看到的公开数据，比如搜索结果、别人的笔记或视频、评论、热榜。

**能翻页吗？** 列表接口每页一次调用，把 `page.next_cursor` 原样传回 `cursor` 就是下一页，24 小时内有效。

**出错了怎么办？** 每个错误都有固定的 `code`、中文说明 `message_zh`，以及会不会扣费（`charged`）和要不要重试（`retry`）。全部错误码：https://okdata.online/zh/docs/errors/

## English

Examples for the okdata Xiaohongshu (RedNote) API: 30 live endpoints behind one API key, pay per call from $0.02, no platform login or cookies. Sign up at https://okdata.online/signup/?src=gh-xiaohongshu-api, docs at https://okdata.online/apis/, MCP at https://okdata.online/mcp/.

## License

MIT. The data comes from the okdata API; its terms apply to API use.
