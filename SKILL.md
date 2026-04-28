---
name: collage-poetry
description: |
  从对话上下文中提取文字片段，生成可交互的拼贴诗HTML页面。
  Extract text fragments from conversation context and generate an interactive collage poetry HTML page.
license: MIT
---

# Collage Poetry · 拼贴诗

从对话上下文中提取文字片段，生成可交互的拼贴诗HTML页面。用户可以拖拽碎片自由拼贴，也可以一键AI生成。

## Usage

读取 `templates/collage-poetry.html` 模板，将 `FRAGMENTS` 数组替换为从对话中提取的文字片段（2-10字，30-60条），将生成的HTML呈现给用户。

## Fragment Extraction Rules · 片段提取规则

- 从对话记录中提取有诗意/画面感/情绪感的片段
- 过滤功能性词语（"好的""收到""嗯"等）
- 混合短短语（1-5字）和短句（5-10字），不同词性都要有
- 建议数量：30-60条

### 词性均衡

确保素材池包含以下类型的片段：
- **名词**：服务器、星空、窗外的雨、旧信件
- **动词/动宾**：重启、风穿过、咖啡冷了、错误已修复
- **形容词/副词**：蓝色、沉默的、终于、孤独
- **短句/意象**：世界安静下来、未发送的消息、裂缝中的光

## Template Structure

`templates/collage-poetry.html` 是自包含的单文件HTML：
- 无外部依赖（纯CSS+JS）
- 左右布局：左侧素材池，右侧拼贴画布
- 功能：拖拽拼贴、AI拼贴（JS随机+预设诗组交替）、一键清空、导出竖版PNG
- 视觉：旧桌面背景、碎片带不规则剪切边缘、胶带装饰、随机字体/字号/颜色
