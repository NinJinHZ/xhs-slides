---
name: xhs-slides
description: 生成小红书3:4比例PPT风格幻灯片网页。将Markdown文章内容转换为可交互的HTML演示文稿，支持多种视觉风格，并可导出PNG图片。
---

# XHS Slides 生成器

将文章内容转换为小红书3:4比例的PPT风格幻灯片，支持多种主题风格。

## 使用方式

```bash
/xhs-slides

# 粘贴Markdown文章内容
# 指定风格（可选）
```

## 输入格式

用户提供：
1. Markdown格式的文章内容
2. 想要的视觉风格（可选，默认科技蓝）

## 可选风格

| 风格名称 | 特点 | 适用场景 |
|---------|------|---------|
| 科技蓝 | 深蓝背景 + 青蓝色调 | 科技、AI、工具评测 |
| 粉紫 | 深紫背景 + 粉紫色调 | 女性向、创意类 |
| 橙红 | 深橙背景 + 暖色调 | 励志、创业、电商 |
| 暗黑 | 纯黑背景 + 白色文字 | 开发者、极客 |
| 白底 | 白色背景 + 黑色文字 | 知识干货、教程 |
| 金色 | 深棕背景 + 金色点缀 | 高端品牌、商业 |
| 氧气 | 白色背景 + 柔和粉绿 | 小红书、清新可爱 |
| 纯净 | 浅灰背景 + 黑色文字 | 极简、干货、教程 |
| 商务橙 | 白底 + 橙色强调 | 商业、创业、效率 |
| 自然绿 | 白底 + 绿色强调 | 清单、健康、生活方式 |
| 电影 | 深色沉浸 + 流畅动画 | 演讲、演示、发布会 |
| Notion | 简洁工作风 + 蓝色强调 | 知识库、文档、效率 |
| Apple | 极致简洁 + 苹果蓝 | 科技、产品、发布会 |
| 酸性 | 镭射金属 + 霓虹色彩 | 创意、先锋、艺术 |
| 孟菲斯 | 高饱和 + 几何图形 | 创意、潮流、个性 |
| 赛博朋克 | 蓝紫暗冷 + 霓虹光感 | 科技、游戏、潮流 |
| 蒸汽波 | 荧光色 + 80年代怀旧 | 复古、潮流、艺术 |
| 醜萌 | 手绘线条 + 笨拙可爱 | 轻松、可爱、创意 |
| Y2K | 金属质感 + 像素混搭 | 复古、潮流、科技 |
| 新粗野 | 原始粗糙 + 硬朗线条 | 先锋、个性、反叛 |
| 古典中国 | 水墨 + 传统纹样 | 文化、国风、传统 |
| 大胆撞色 | 高饱和对比 + 视觉冲击 | 吸睛、潮流、个性 |
| 欧普艺术 | 几何错视 + 眩晕光效 | 艺术、先锋、视觉冲击 |
| 波普风格 | 夸张色彩 + 流行符号 | 潮流、艺术、吸睛 |

## 工作流程

1. **接收内容**：用户粘贴Markdown文章
2. **分析结构**：提取标题层级，合并相关页面
3. **选择风格**：根据内容类型推荐风格
4. **生成HTML**：创建3:4比例的幻灯片HTML
5. **导出图片**：使用Playwright截取每张幻灯片为PNG

## 输出文件

- `{标题}-presentation.html` - 可交互的HTML演示文稿
- `{标题}-slides/` - PNG图片文件夹

## 风格配置

风格通过CSS变量定义，修改以下变量即可切换风格：

```css
:root {
    --bg-primary:   /* 背景色 */
    --text-primary: /* 主文字色 */
    --text-secondary: /* 次要文字色 */
    --accent:       /* 主强调色 */
    --accent-secondary: /* 次强调色 */
    --gradient-1:   /* 渐变色1 */
}
```

### 科技蓝
```css
--bg-primary: #0a0a0f;
--text-primary: #ffffff;
--text-secondary: #a0a0b0;
--accent: #00d4ff;
--accent-secondary: #ff006e;
--gradient-1: linear-gradient(135deg, #00d4ff 0%, #0066ff 100%);
```

### 粉紫
```css
--bg-primary: #1a0a1e;
--text-primary: #ffffff;
--text-secondary: #b0a0b8;
--accent: #ff6b9d;
--accent-secondary: #c084fc;
--gradient-1: linear-gradient(135deg, #ff6b9d 0%, #c084fc 100%);
```

### 橙红
```css
--bg-primary: #1a0f0a;
--text-primary: #ffffff;
--text-secondary: #b0a0a0;
--accent: #ff9f43;
--accent-secondary: #ee5a24;
--gradient-1: linear-gradient(135deg, #ff9f43 0%, #ee5a24 100%);
```

### 暗黑
```css
--bg-primary: #0a0a0a;
--text-primary: #ffffff;
--text-secondary: #808080;
--accent: #ffffff;
--accent-secondary: #cccccc;
--gradient-1: linear-gradient(135deg, #ffffff 0%, #888888 100%);
```

### 白底
```css
--bg-primary: #ffffff;
--text-primary: #000000;
--text-secondary: #666666;
--accent: #000000;
--accent-secondary: #333333;
--gradient-1: linear-gradient(135deg, #000000 0%, #444444 100%);
```

### 金色
```css
--bg-primary: #1a1510;
--text-primary: #ffffff;
--text-secondary: #b0a090;
--accent: #ffd700;
--accent-secondary: #ffaa00;
--gradient-1: linear-gradient(135deg, #ffd700 0%, #ffaa00 100%);
```

### 氧气（清新氧气感）
```css
--bg-primary: #fdfcfb;
--text-primary: #2d3436;
--text-secondary: #636e72;
--accent: #fd79a8;
--accent-secondary: #00cec9;
--gradient-1: linear-gradient(135deg, #fd79a8 0%, #a29bfe 50%, #00cec9 100%);
```

### 纯净（极简干净）
```css
--bg-primary: #f8f9fa;
--text-primary: #1a1a1a;
--text-secondary: #666666;
--accent: #1a1a1a;
--accent-secondary: #333333;
--gradient-1: linear-gradient(135deg, #1a1a1a 0%, #444444 100%);
```

### 商务橙（一人公司操作系统风格）
```css
--bg-primary: #fafaf8;
--text-primary: #1a1a1a;
--text-secondary: #666666;
--accent: #ff6b35;
--accent-secondary: #ff8c5a;
--gradient-1: linear-gradient(135deg, #ff6b35 0%, #ff8c5a 100%);
```

### 自然绿（清单勾选风格）
```css
--bg-primary: #f8faf5;
--text-primary: #1a2e1a;
--text-secondary: #4a5d4a;
--accent: #2d8a4e;
--accent-secondary: #5cb85c;
--gradient-1: linear-gradient(135deg, #2d8a4e 0%, #5cb85c 100%);
```

### 电影（深色沉浸+流畅动画）
```css
--bg-primary: #0a0a12;
--text-primary: #ffffff;
--text-secondary: #a0a0b0;
--accent: #ff6b4a;
--accent-secondary: #4af0c8;
--gradient-1: linear-gradient(135deg, #ff6b4a 0%, #ff9f6b 100%);
```

### Notion（简洁工作风）
```css
--bg-primary: #ffffff;
--text-primary: #37352f;
--text-secondary: #9b9a97;
--accent: #2eaadc;
--accent-secondary: #eb5757;
--gradient-1: linear-gradient(135deg, #2eaadc 0%, #4a9eff 100%);
```

### Apple（极致简洁）
```css
--bg-primary: #ffffff;
--text-primary: #1d1d1f;
--text-secondary: #86868b;
--accent: #0071e3;
--accent-secondary: #34c759;
--gradient-1: linear-gradient(135deg, #0071e3 0%, #34c759 100%);
```

### 酸性设计（Acid Design）
```css
--bg-primary: #0a0a0f;
--text-primary: #ffffff;
--text-secondary: #c0c0c0;
--accent: #ff00ff;
--accent-secondary: #00ffff;
--gradient-1: linear-gradient(135deg, #ff00ff 0%, #00ffff 50%, #ffff00 100%);
```

### 孟菲斯风格（Memphis）
```css
--bg-primary: #ffffff;
--text-primary: #1a1a1a;
--text-secondary: #666666;
--accent: #ff3366;
--accent-secondary: #ffcc00;
--gradient-1: linear-gradient(135deg, #ff3366 0%, #00ccff 50%, #ffcc00 100%);
```

### 赛博朋克（Cyberpunk）
```css
--bg-primary: #0d0d1a;
--text-primary: #ffffff;
--text-secondary: #8888aa;
--accent: #ff00ff;
--accent-secondary: #00ffff;
--gradient-1: linear-gradient(135deg, #ff00ff 0%, #0066ff 100%);
```

### 蒸汽波（Vaporwave）
```css
--bg-primary: #1a0a2e;
--text-primary: #ffffff;
--text-secondary: #b0a0c0;
--accent: #ff71ce;
--accent-secondary: #01cdfe;
--gradient-1: linear-gradient(135deg, #ff71ce 0%, #01cdfe 50%, #05ffa1 100%);
```

### 醜萌风格（Naive Design）
```css
--bg-primary: #fff5e6;
--text-primary: #2d2d2d;
--text-secondary: #666666;
--accent: #ff6b6b;
--accent-secondary: #4ecdc4;
--gradient-1: linear-gradient(135deg, #ff6b6b 0%, #ffe66d 100%);
```

### Y2K风格（Retro Futurism）
```css
--bg-primary: #1a1a2e;
--text-primary: #ffffff;
--text-secondary: #a0a0c0;
--accent: #00d4ff;
--accent-secondary: #ff00ff;
--gradient-1: linear-gradient(135deg, #00d4ff 0%, #ff00ff 50%, #ffd700 100%);
```

### 新粗野主义（Neo-Brutalism）
```css
--bg-primary: #f5f5dc;
--text-primary: #000000;
--text-secondary: #333333;
--accent: #ff0000;
--accent-secondary: #0000ff;
--gradient-1: linear-gradient(135deg, #ff0000 0%, #ffff00 100%);
```

### 古典中国风（Classical Chinese）
```css
--bg-primary: #faf8f5;
--text-primary: #2d2d2d;
--text-secondary: #666666;
--accent: #c41e3a;
--accent-secondary: #1e5631;
--gradient-1: linear-gradient(135deg, #c41e3a 0%, #d4af37 50%, #1e5631 100%);
```

### 大胆撞色（Bold Color Clashing）
```css
--bg-primary: #0a0a0f;
--text-primary: #ffffff;
--text-secondary: #c0c0c0;
--accent: #ff00ff;
--accent-secondary: #ffff00;
--gradient-1: linear-gradient(135deg, #ff00ff 0%, #00ffff 100%);
```

### 欧普艺术（Op Art）
```css
--bg-primary: #000000;
--text-primary: #ffffff;
--text-secondary: #c0c0c0;
--accent: #ffffff;
--accent-secondary: #ff0000;
--gradient-1: linear-gradient(135deg, #ffffff 0%, #ff0000 100%);
```

### 波普风格（Pop Art）
```css
--bg-primary: #ff0066;
--text-primary: #ffffff;
--text-secondary: #ffe6f2;
--accent: #ffff00;
--accent-secondary: #00ffff;
--gradient-1: linear-gradient(135deg, #ff0066 0%, #ffff00 50%, #00ffff 100%);
```

## HTML幻灯片规范

### 布局要求
- 幻灯片尺寸：600px × 800px（3:4比例）
- 使用固定像素值，确保截图准确性

### 页面结构

| 页面 | 内容 |
|------|------|
| 封面 | 标签 + 标题 + 副标题 + 引言 |
| 内容页 | 标题 + 正文/列表/表格 |
| 结尾页 | 总结/引用 + 署名 |

### 视觉规范

1. **字体**：Noto Sans SC（中文）+ Space Mono（英文装饰）
2. **标题**：32-42px，加粗
3. **正文**：14px，行高1.6
4. **装饰**：顶部色条 + 点阵/网格背景

## 示例

用户输入：
```
/xhs-slides

风格：氧气

# Perplexity Computer

> 2026年2月发布

## 一、功能
- AI搜索
- 代码生成
```

Skill生成：
- 氧气风格的3:4比例HTML幻灯片
- PNG图片导出

## 依赖

- Python 3.x
- playwright (`pip install playwright && playwright install chromium`)

## 竖构图排版设计规范

针对3:4比例的小红书竖版幻灯片，遵循以下排版原则：

### 1. 信息层级策略

- **主标题**：最大字号（36-48px），加粗，居中或顶部对齐
- **副标题**：中等字号（18-24px），颜色使用次要色（text-secondary）
- **正文**：标准字号（14-16px），行高1.6-1.8
- **强调词**：使用accent色突出

### 2. 留白与安全边距

- **上下边距**：建议80-120px（封面可更大）
- **左右边距**：40-60px
- **内容区**：垂直居中或上1/3处（根据内容类型）
- **段落间距**：24-32px

### 3. 视觉动线设计

- 封面：视线从上→下的自然流动
- 内容页：标题→正文→辅助信息的层级
- 使用颜色/大小对比引导阅读顺序
- 避免信息过于密集

### 4. 模块化布局

- **两列布局**：适合对比、场景卡片
- **卡片圆角**：12-16px
- **卡片间距**：16-24px
- **列表项**：使用符号（▸ 或 ✓）引导

### 5. 竖构图视觉技巧

- **居中法则**：主文案居中，干净高端
- **解构排版**：可尝试打破网格的创意排版
- **弥散光晕**：标题下方添加渐变光晕强调
- **分屏美学**：多场景用上下分屏

### 6. 封面页特别处理

- 标签（tagline）在最上
- 主标题居中或居上
- 副标题/引言在下方
- 背景使用网格/光晕增加层次

## 注意事项

1. 封面页可合并引言/开篇，节省页数
2. 内容过多的页面自动精简
3. 表格自动适配宽度
4. 移动端友好的响应式设计
