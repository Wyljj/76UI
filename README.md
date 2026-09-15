# 76UI · 76 份大厂设计系统模板

76 个大厂 / 知名产品的 **design system 参考模板**（Markdown），每份都是同一套 11 章结构，
可以逐章对照着读：颜色、字体、布局、层次、形状、组件、Do's and Don'ts、响应式、迭代指南、已知缺口。

**它们是参考资料，不是规范。** 任何项目要落地设计系统，都应当在自己的仓库里写一份权威的
`DESIGN.md`（令牌 + 组件 + 护栏），把这 76 份当作「别人怎么解决同一类问题」的对照材料。

## 内容

| 文件 | 说明 |
|---|---|
| `<brand>.md` × 76 | 每份含 YAML front matter（令牌取值）+ 11 章正文 |
| 本 README | 来源、结构、用法纪律 |

覆盖的品牌：airbnb · airtable · apple · binance · bmw · bmw-m · bugatti · cal · claude · clay ·
clickhouse · cohere · coinbase · composio · cursor · dell-1996 · discord · elevenlabs · expo ·
figma · ferrari · framer · hashicorp · hp · ibm · intercom · kraken · lamborghini · linear.app ·
lovable · mastercard · meta · minimax · mintlify · miro · mistral.ai · mobbin · mongodb · nike ·
nintendo-2001 · notion · nvidia · ollama · opencode.ai · pinterest · playstation · posthog ·
raycast · renault · replicate · resend · revolut · runwayml · sanity · sentry · shopify · slack ·
spacex · spotify · stripe · supabase · superhuman · tesla · theverge · thread · tiktok · toyota ·
uber · vercel · warren-buffett · webflow · wechat · wise · x.ai · zapier（完整清单见归档的 INDEX）

## 每份模板的结构

```yaml
---
version: alpha
name: Uber-design-analysis
description: An inspired interpretation of Uber's design language …
colors: { primary: "#000000", … }
typography: { … }
---
```

正文 11 章：Overview / Colors / Typography / Layout / Elevation & Depth / Shapes / Components /
Do's and Don'ts / Responsive Behavior / Iteration Guide / Known Gaps。

写法上是「描述 + 理由 + 令牌」三件套，例如：

> 一个品牌只用一个强调色；状态色只表达状态，绝不用来装饰。

这比只抄一份色板有用得多——它记录了**为什么**这么定。

## 建议的读法

1. 先看 `description` 与 Colors：搞清这个品牌的取舍（纯黑白 + 一枚功能色？高饱和？深色画布？）。
2. 再看 Components 与 Do's and Don'ts：这两章最能直接搬到自己的项目里。
3. Typography 与 Elevation 章看**节奏**（字号阶梯、行高配对、阴影档位数量），不要抄字体本身。
4. 抄皮肤（深色营销渐变、品牌字体、装饰光斑、hero 区）通常会让业务系统变难用；只借组件级条目。

## 在这些文件上跑 Agent 的注意事项

- 文件名不要用 `claude.md` / `agents.md` 这类**与 AI 工具指令文件同名**的名字：
  Windows 大小写不敏感，会被 Claude Code 一类工具当成项目指令自动加载，把整份品牌文档灌进上下文。
  本仓库沿用 `brand-` 前缀（如 `brand-claude.md`）。
- 单份模板约 30 KB，一次别塞太多份进上下文；按章节引用即可。

## 来源与授权

内容由开源 CLI [getdesign](https://www.npmjs.com/package/getdesign)（skill「大厂设计系统 design-md」的底层工具）
导出：`npx getdesign@latest list`。

这些文档是对公开产品设计语言的**分析性描述**（inspired interpretation），不包含任何品牌官方素材、
字体文件或源码；品牌名与商标归各自所有者。若原工具或某品牌方要求下架，请提 issue，会及时删除对应文件。

## 重新生成 / 更新

```bash
# 拉取最新模板
npx getdesign@latest list

# 生成一张令牌样张页，双击用浏览器打开即可对比 76 个品牌的底色/信息面/主按钮/状态胶囊/字阶
# （样张页是「把 front matter 的令牌拼成卡片」，不是官网截图）
```
