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

## 注意事项

1. 封面页可合并引言/开篇，节省页数
2. 内容过多的页面自动精简
3. 表格自动适配宽度
4. 移动端友好的响应式设计
