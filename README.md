# 狗头军师 · 手机版

先接住情绪，再分析关系，最后给你能执行的下一步。一个装在手机主屏上的恋爱/关系军师。

## 它是什么

一个纯前端的 PWA（渐进式网页应用）：把一个开源 Codex Skill —— [goutoujunshi](https://github.com/shengjidaguai-china/goutoujunshi)（MIT）—— 的完整提示词与 43 篇参考资料打包进网页，用 ChatGPT 兼容接口的流式聊天跑起来。

- **手机优先**：iOS / Android 浏览器打开即可用，可「添加到主屏幕」，体验接近原生 App。
- **不依赖电脑**：部署到 GitHub Pages 后，任何时间、任何地点都能用，本机关机也没影响。
- **会检索资料**：按你每句话的关键词，自动从资料库里挑 1–2 篇最相关的注入上下文，省 token 又稳准。
- **档案与记忆**：MBTI / 评分 / 目标 / 对象档案、可增删的长期记忆，全部存在**本机浏览器**。
- **隐私本地化**：API Key、对话、档案只存你这台手机的 `localStorage`，不上传任何第三方（只把你的请求发给你自己填的接口）。

## 怎么用

1. 打开部署好的网址（Android 或 iOS 浏览器）。
2. 首次进入会弹出设置：填 **接口地址**、**模型**、**API Key**（只填一次）。
   - 默认接口 `https://maas.qianwenaiapi.com/compatible-mode/v1`、模型 `deepseek-v4.1-flash`，可改成任意 OpenAI 兼容接口。
3. 想当 App 用：iOS 点底部「分享 → 添加到主屏幕」；Android 点「安装/添加到主屏幕」。

## 对话方式

直接说也行，例如：

- 「她这两周回消息越来越慢，但周末又主动找我，我是不是被吊着？」
- 「这句话怎么回：……」——贴聊天记录
- 「帮我设计一次具体邀约」

军师会先接住情绪、把事实与推测分开，再给能执行的建议；需要「能直接发的话」时，会单独用引用块给出，并交代适用前提。涉及暴力、自伤、跟踪等风险时，会先给安全建议。

## 换手机 / 数据迁移

设置里有**配置码**：复制后到新手机「粘贴导入」，Key、接口、模型都一并搬过去；对话与档案也可用「清空」按钮随时删。

## 目录结构

```
index.html           界面
assets/app.css       样式（深/浅色）
assets/app.js        逻辑：流式聊天、检索、档案、记忆
assets/skill-core.js  技能提示词 + 资料索引（生成物）
assets/skill-docs.js  43 篇参考资料正文（生成物）
manifest.webmanifest / sw.js / icons/   PWA
tools/               生成脚本（python build_skill_data.py / make_icons.py）
```

## 声明

- 技能内容版权归原项目 [goutoujunshi](https://github.com/shengjidaguai-china/goutoujunshi)（MIT License）。
- 本应用与任何聊天软件无关，不读取、不解密、不导出微信 / QQ 等聊天数据。
- 建议仅供参考；危险情境请以人身安全为第一优先，并寻求专业求助。