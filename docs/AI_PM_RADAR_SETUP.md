# AI 产品经理情报雷达

这个 Fork 将 Horizon 定制为面向 AI 产品经理的每日信息收集系统。它每天自动抓取全球 AI 动态，使用 DeepSeek 评分、去重、补充背景并生成中文日报。

## 关注方向

- 前沿技术：基础模型、多模态、Agent、推理、MCP 与基础设施
- 产品与应用：新产品、新功能、新交互、新工作流和真实落地案例
- 行业与趋势：竞争格局、融资、定价、分发、监管和企业采用
- 人物与观点：研究者、创业者、科技公司高管和行业分析者的判断

AI 评分会优先考虑产品影响、用户价值、商业模式、竞争格局、技术成熟度、证据质量和可落地性。

## 已配置的信源

- 一手来源：OpenAI、Google DeepMind、Google AI、NVIDIA
- 行业媒体：TechCrunch AI、VentureBeat AI、量子位、新智元
- 产品发现：Product Hunt、GitHub Releases、OSS Insight
- 社区信号：Hacker News、Reddit
- 人物与深度观点：Simon Willison、Latent Space、One Useful Thing、Interconnects、AI Snake Oil
- 新闻搜索：Google News 中文搜索与 GDELT 全球新闻

X/Twitter 人物名单已预设但暂未启用，因为自动抓取需要额外的 Apify Token 或浏览器 Cookie。

## DeepSeek

系统使用 `deepseek-v4-flash`，API 地址为 `https://api.deepseek.com`。密钥只保存于 GitHub Actions Secrets，不进入代码或配置文件。

在仓库的 `Settings → Secrets and variables → Actions` 中创建：

```text
DEEPSEEK_API_KEY
```

## 自动运行

GitHub Actions 每天北京时间 08:30 运行，也可以在 Actions 页面手动触发 `Daily Horizon Summary`。

运行结果会：

1. 生成中文 Markdown 日报；
2. 保存至 `data/summaries/`；
3. 发布到仓库的 `gh-pages` 分支；
4. 通过 GitHub Pages 提供网页访问。

## 后续可选增强

- 接入飞书、Slack 或 Discord Webhook
- 启用 X/Twitter 人物动态
- 将 Markdown 日报同步进 Obsidian Vault
- 根据一周使用反馈调整评分阈值、每日条数与信源权重
