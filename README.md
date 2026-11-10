# YouTube 评论抓取工具

[![Bright Data](https://img.shields.io/badge/Powered%20by-Bright%20Data-FF9A00?style=flat-square)](https://www.bright.cn/) [![爬虫工具 API](https://img.shields.io/badge/Scraper%20API-Available-FF9A00?style=flat-square)](https://www.bright.cn/products/web-scraper/youtube) [![数据集](https://img.shields.io/badge/Dataset-Available-0066CC?style=flat-square)](https://www.bright.cn/products/datasets/youtube) [![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org) [![许可证：MIT](https://img.shields.io/badge/License-MIT-22C55E?style=flat-square)](LICENSE)

[![推广](https://github.com/bright-cn/Awesome-Web-Scraping/raw/main/Proxies%20and%20scrapers%20GitHub%20bonus%20banner%20CN.png)](https://www.bright.cn/products/web-scraper/youtube)

> **由 [Bright Data](https://www.bright.cn/) 提供支持的 YouTube 评论数据。**

此代码库提供两种大规模访问 YouTube 评论数据的方法：

- **[方法 1：Bright Data YouTube 评论爬虫工具 API](#方法-1bright-data-youtube-评论爬虫工具-api)**（推荐），完全托管的企业级爬虫 API，可自动处理代理、CAPTCHA 和扩展。
- **[方法 2：Bright Data YouTube 评论数据集](#方法-2bright-data-youtube-评论数据集)**，可直接下载的预采集 YouTube 评论数据集，无需抓取。

## 目录

- [为什么使用 Bright Data 抓取 YouTube 评论？](#为什么使用-bright-data-抓取-youtube-评论)
- [方法 1：Bright Data YouTube 评论爬虫工具 API](#方法-1bright-data-youtube-评论爬虫工具-api)
  - [快速开始](#开始使用-youtube-评论爬虫工具-api)
  - [1. YouTube 评论数据](#1-youtube-评论数据)
- [方法 2：Bright Data YouTube 评论数据集](#方法-2bright-data-youtube-评论数据集)
- [数据采集方式](#数据采集方式)

## 为什么使用 Bright Data 抓取 YouTube 评论？

抓取 YouTube 评论面临多项挑战：

- 速率限制：YouTube 会监控请求频率，并可能封禁超出限制的 IP。
- CAPTCHA 检测：自动访问可能会触发 CAPTCHA 验证。
- 身份验证障碍：部分数据需要登录才能访问，且平台会检测自动化操作。
- 动态内容加载：使用 JavaScript 渲染的内容很难通过简单的 HTTP 请求抓取。
- IP 封禁：从同一 IP 重复发送请求可能会导致封禁。

Bright Data 的 YouTube 评论爬虫工具 API 可通过以下功能解决这些问题：

- ✅ **内置动态代理**：自动绕过基于 IP 的速率限制
- ✅ **验证码破解**：无需任何额外设置即可处理机器人检测
- ✅ **结构化数据输出**：获取可直接用于分析的整洁 JSON
- ✅ **无需基础设施**：云端托管的抓取服务可灵活扩展至任意规模
- ✅ **99.9% 正常运行时间 SLA**：为业务关键型工作流提供可靠的数据采集

## 方法 1：Bright Data YouTube 评论爬虫工具 API

[Bright Data YouTube 评论爬虫工具 API](https://www.bright.cn/products/web-scraper/youtube) 是一种完全托管的解决方案，无需配置任何基础设施。

### 开始使用 YouTube 评论爬虫工具 API

1. **注册**一个[免费的 Bright Data 账户](https://www.bright.cn/)
2. **前往** [YouTube 评论爬虫工具 API](https://www.bright.cn/products/web-scraper/youtube)
3. 从控制面板**获取 API 令牌**
4. **安装** `requests` 库：`pip install requests`
5. **运行** `youtube-comments_scraper_api_codes/` 中的任意脚本

### 1. YouTube 评论数据

采集 YouTube 评论数据。

#### 输入参数

| 字段 | 类型 | 必填 | 说明 |
|-------|------|----------|-------------|
| `url` | 字符串 | 是 | 要抓取的 YouTube 项目的 URL |
| `limit` | 整数 | 否 | 要返回的最大结果数 |
| `include_errors` | 布尔值 | 否 | 在响应中包含错误详情 |
| `notify` | url | 否 | 采集完成时用于接收通知的 Webhook URL |
| `format` | 枚举 | 否 | 输出格式：`JSON`、`NDJSON`、`JSON Lines`、`CSV` |

#### 响应示例

```json
{
  "author": "@user12345",
  "author_channel_url": "https://www.youtube.com/@user12345",
  "comment_id": "UgyHvXk0V4tDzM7p2KN4AaABAg",
  "comment_text": "This song never gets old, brings back so many memories!",
  "is_hearted": false,
  "is_pinned": false,
  "likes": 2453,
  "published_at": "2024-08-15T10:23:14Z",
  "reply_count": 17,
  "url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ\u0026lc=UgyHvXk0V4tDzM7p2KN4AaABAg",
  "video_id": "dQw4w9WgXcQ",
  "video_url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
}
```

👉 查看[完整 Python 代码](youtube-comments_scraper_api_codes/youtube_comments_scraper.py)

## 方法 2：Bright Data YouTube 评论数据集

对于需要开箱即用的数据、又不想编写任何抓取代码的使用场景，[Bright Data YouTube 评论数据集](https://www.bright.cn/products/datasets/youtube)提供预采集并定期更新的数据，可立即下载。

**为什么使用数据集而不是 API？**

- 📦 **即时访问**：无需设置、无需代码，也无需等待采集
- 🔄 **定期更新**：按照固定计划刷新最新数据
- 📊 **多种格式**：可下载为 JSON、JSONL 或 CSV
- 🌍 **海量规模**：涵盖所有主要 YouTube 评论类别的数百万条记录
- ✅ **完全合规**：数据来源符合道德规范并已通过法律审查

👉 **[探索 YouTube 评论数据集](https://www.bright.cn/products/datasets/youtube)**

## 数据采集方式

| 功能 | Bright Data 爬虫工具 API | Bright Data 数据集 |
|---------|------------------------|---------------------|
| 所需设置 | 仅需 API 令牌 | 无 |
| 实时数据 | ✅ 是 | ❌ 预采集 |
| 自定义查询 | ✅ 完全控制 | ❌ 固定架构 |
| 包含代理 | ✅ 内置动态代理 | N/A |
| CAPTCHA 破解 | ✅ 自动 | N/A |
| 规模 | 无限制 | 无限制 |
| 结构化输出 | ✅ JSON / NDJSON / JSON Lines / CSV | ✅ JSON / JSONL / CSV |
| 支持 | 企业级全天候支持 | 企业级全天候支持 |

---

🔗 **了解更多**：[https://www.bright.cn/products/web-scraper/youtube](https://www.bright.cn/products/web-scraper/youtube)
