# GEO Skills 使用说明书

两个 Agent Skill 的完整手册：从安装、调用，到它们背后调用的**每一个付费接口**（含配置方法、成本估算、踩坑记录）。

## 包含什么

```
├── 一、这两个 Skill 是什么
├── 二、安装（3 种方式）
├── 三、怎么用（触发话术 + 五步流程 + 交付物）
├── 四、依赖的接口清单（付费 / 免费 / 必需 / 可选）
├── 五、接口配置方法（环境变量 / .env / 安全红线）
├── 六、成本估算（单次分析 < 0.1 元，月成本约 10 元）
├── 七、没有 API 也能用的部分（手工替代方案）
├── 八、常见问题（6 个）
└── 九、踩坑记录（5 条实战坑）
```

👉 **完整正文：[MANUAL.md](./MANUAL.md)**

## 两个配套 Skill

| Skill | 解决什么 | 仓库 |
|---|---|---|
| **geo-competitor-mining** | AI 为什么不推荐你 | [→](https://github.com/liuyingwork1234-ops/geo-competitor-mining) |
| **geo-visibility-baseline** | 做了这么多到底有没有用 | [→](https://github.com/liuyingwork1234-ops/geo-visibility-baseline) |

## 接口速查

| 接口 | 用途 | 付费 | 必需 |
|---|---|---|---|
| 大模型 API（阿里云百炼 / DeepSeek / Kimi / OpenAI）| 摸战场：问 AI 要推荐名单 | ✅ | ✅ |
| 搜索 API（Tavily / Brave / SerpAPI）| 检索层探测、找来源文章 | ✅（有免费额度）| ⭕ |
| 网页抓取 | 扒底裤：提取对标页六项 | ❌ | ✅ |
| IndexNow | 推 URL 给 Bing / Yandex | ❌ | ⭕ |
| 百度普通收录推送 | 推 URL 给百度 | ❌ | ⭕ |

**配置变量名（值不进仓库）：**

```bash
GEO_LLM_BASE_URL=
GEO_LLM_API_KEY=
GEO_LLM_MODEL=
TAVILY_API_KEY=
```

## 核心观点

> **AI 推荐的依据，首先来自别人怎么写你。**
> 所以你缺的往往不是官网做得不够好，是**不在那批「推荐几家」的盘点文里**。

> **内容被「索引」不等于被「吸收」。**
> 搜索层能查到你的官网，不代表模型知识里有你。两者要分开测。

## 三条纪律

- **问题集固定，建好后不许改** —— 改了历史数据全部不可比
- **结构可以抄，事实必须真** —— 编造数字会被 AI 交叉验证全盘否定
- **单次结果不下结论** —— 看三次以上趋势

## 相关链接

- **官网**：[oceangtm.com](https://oceangtm.com/) —— 外贸独立站 GEO 服务商
- **Skill 下载页**：[oceangtm.com/skill.html](https://oceangtm.com/skill.html) —— 免登录直接下载 zip
- **方法来源**：[为什么问 AI 推荐永远没有我们公司](https://oceangtm.com/blog/how-to-do-geo-content-fast-2026.html)

## License

MIT
