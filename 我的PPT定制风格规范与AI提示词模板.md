# 我的 PPT 定制风格规范与 AI 提示词模板
> **风格全称**：企业学术满框大字三线表风格 (Academic-Enterprise FullFrame Large-Font Style)  
> **风格代号**：`academic-fullframe`  
> **适用场景**：科研成果汇报、学位论文答辩、企业技术攻关与专利汇报、SOTA 算法指标横评、技术路线评审

---

## 快速使用：一键复制给下一个 AI 的通用提示词 (Prompt)

> 💡 **使用方法**：无论是换用新的 AI 助手（如 ChatGPT、Claude、DeepSeek、其他 Antigravity 实例等），还是在新对话中制作 PPT，只需将下面引用框内的这段提示词**直接复制并发送给 AI**，对方就能立即精准复刻这套高规格风格。

```markdown
请严格按照我的专属【企业学术满框大字三线表风格 (academic-fullframe)】为我设计和生成 PPT（或生成 PptxGenJS 代码）。请严格遵循以下 9 大核心设计铁律：

1. 【画布母版与几何比例】：
   - 必须采用标准 16:9 现代宽屏（13.333" × 7.50"，即 33.867cm × 19.05cm）。
   - 顶部通栏：经典企业科技蓝条（y: 0.0, h: 0.76", fill: "4472C4"）。
   - 顶部文字：左侧章节大序号（Arial Black, 34pt, 白色），右侧精炼主标题（微软雅黑加粗, 28pt, 白色）。

2. 【满框排布，边框不留虚白 (Zero Margin Waste)】：
   - 内容区必须最大限度铺满画面：左边距 x: 0.28"，右边距至 13.05"（内容可用总宽度达 12.77"）。
   - 纵向上紧贴顶栏下沿 y: 0.88"，底端拉满至 y: 7.30"（内容可用总高度达 6.42"）。
   - 严禁在周边保留大面积无意义的灰白色空隙！

3. 【纯正科研三线表规范 (Scientific Three-Line Table)】：
   - 顶线：2.2pt 粗深色实线（#1E293B）。
   - 栏目线（表头下划线）：1.2pt 深色实线（#1E293B）。
   - 底线：2.2pt 粗深色实线（#1E293B）。
   - 绝对严禁出现竖线（vertical lines 为 null），绝对严禁出现内部横向网格线！
   - 表格必须占据 12.77" 全宽居中展示，严禁与窄文本卡强行左右挤在同一页。

4. 【字号准则——以注满框图的最大字号再小一号为准 (Max-1 Sizing)】：
   - 必须追求极佳的远距离可读性，杜绝小气拥挤的排版，严禁出现 <15pt 的蚊子字！
   - 表头文字：18~19pt Bold；表格数据：17pt Regular；Ours 冠军行：18pt Bold。
   - 卡片大标题/分栏标题：18.5~19pt Bold。
   - 卡片正文/解析文本：16.5~17.5pt，行间距 lineSpacingMultiple 设为 1.25~1.30。
   - 核心突破数字看板（KPI Callout）：38~42pt 超大 Bold。

5. 【关键成果与核心突破数字标红加粗 (Highlight in Bold Red)】：
   - 在所有分析文本、总结卡片及表格冠军数据中，关键突破性数字（如检出量、AP值、涨幅百分比、Recall、F1等）与硬核结论词汇（如“全场第1”、“断层第一”、“100%全覆盖”、“抗漏检实力顶尖”）必须设为醒目的加粗红色（#DC2626）。

6. 【基准对比模型必须标注发表年份 (Model Publication Years)】：
   - 涉及对比的所有 SOTA 基准算法，必须在名称后附带括号标注其论文发表年份（例如：FusionMamba (2024)、ITFuse (2024)、SFDFuse (2024)、MAEFuse (2024)、Ours (LAMF, 2026)）。

7. 【主副标题文字极度精炼 (Streamlined Headings)】：
   - 顶栏主标题控制在 6~12 个字内，直接明了（如“1.3 实验环境与基准设定”、“1.3 实景实证：夜市密集街景”），剔除冗长啰嗦的修饰语。

8. 【零底注与多余杂质 (No Footnotes / Annotations)】：
   - 页面左下角与底部严禁放置课题组署名水印、版权小字或“注：...”等次要注释，保持整张画布纯粹专注于硬核技术成果。

9. 【原生矢量图表 (Native Office Charts)】：
   - 数据对比柱状图、条形图等必须使用原生图表对象（如 PptxGenJS 的 addChart），内嵌数据源，支持双击在 Excel 中自由编辑。
```

---

## 9 大设计铁律深度解析

### 铁律 1：画布母版与顶栏规范 (Canvas & Master Geometry)
* **比例**：16:9（`13.333" × 7.50"` / `LAYOUT_16x9`）。
* **顶栏背景条**：
  * 坐标：`x: 0.0, y: 0.0, w: 13.333, h: 0.76`。
  * 填充色：企业科技蓝 `#4472C4`（无边框）。
* **章节大序号**：
  * 文本：如 `1.3`。
  * 坐标：`x: 0.28, y: 0.0, w: 1.20, h: 0.76`。
  * 字体：`Arial Black`，字号 `34pt`，颜色 `#FFFFFF`，垂直居中对齐。
* **精炼主标题**：
  * 文本：如 `实验环境与基准设定`。
  * 坐标：`x: 1.45, y: 0.0, w: 11.50, h: 0.76`。
  * 字体：`Microsoft YaHei`（微软雅黑加粗），字号 `28pt`，颜色 `#FFFFFF`，垂直居中对齐。

---

### 铁律 2：满屏排布，边框不留虚白 (Zero Margin Waste)
传统模板边缘常留出 1~1.5 英寸无用白边，导致内容挤在中间像缩略图。本风格要求**视觉震撼、信息饱和**：
* **横向总跨度**：`x = 0.28"` 到 `x = 13.05"`，有效内容宽度 `12.77"`（利用率达 96%）。
* **纵向总跨度**：`y = 0.88"`（紧接顶栏下方）到 `y = 7.30"`，有效内容高度 `6.42"`（利用率达 86%）。
* **间距控制**：
  * 双栏布局（左右两卡）：左卡 `w: 6.25"`，间隙 `gap: 0.27"`，右卡 `w: 6.25"`。
  * 三段式卡片（一图加两卡或三卡）：卡片间垂直间距 `0.15" ~ 0.20"`。

---

### 铁律 3：纯正科研三线表规范 (Scientific Three-Line Table)
学术界顶级期刊（IEEE TPAMI, CVPR, ICCV）通用表格范式：
* **顶线 (Top Line)**：`pt: 2.2`, 颜色 `#1E293B`（粗实线，定格顶部）。
* **栏目线 (Header Underline)**：`pt: 1.2`, 颜色 `#1E293B`（表头与数据分隔线）。
* **底线 (Bottom Line)**：`pt: 2.2`, 颜色 `#1E293B`（粗实线，收尾封底）。
* **网格与竖线**：
  * 竖线：绝对严禁（`left: null, right: null` 或 `pt: 0`）。
  * 内部行分割线：绝对严禁（`top: null, bottom: null`，除表头下划线外其余行皆无底线）。
* **斑马纹与高亮**：
  * 数据行底色保持纯净白色或极淡交替色（`#F8FAFC`）。
  * **Ours 算法行**：底色高亮（如浅蓝 `#EEF2FF` 或浅冰蓝 `#E0F2FE`），加粗强调。
* **独立展布**：三线表占据完整 `12.77"` 宽度，禁止与右侧小说明卡挤在一页，保证字体能放大至 17~18pt。

---

### 铁律 4：字号准则——以注满框图的最大字号再小一号为准 (Max-1 Sizing)
* **设计心理学**：汇报时听众通常坐在投影幕布 3~10 米外，小字号（10~14pt）会造成阅读疲劳并降低汇报权威感。
* **执行计算法则**：排版时先计算让文字填满卡片的最大字号，然后统一降低 1pt（或 0.5pt），确保文字饱满撑起版面，同时留有微小的呼吸感，不折行、不截断。
* **典型字号对照表**：
  | 元素类别 | 字体名称 | 字号范围 | 样式与属性 |
  | :--- | :--- | :--- | :--- |
  | 顶栏主章节号 | Arial Black | `34pt` | Bold, 白色 `#FFFFFF` |
  | 顶栏精炼主标题 | Microsoft YaHei | `28pt` | Bold, 白色 `#FFFFFF` |
  | 关键数据大看板 (KPI) | Arial / Arial Black | `38~42pt` | Bold, 红色 `#DC2626` 或深蓝 `#1E293B` |
  | 卡片主标题 / 分栏标题 | Microsoft YaHei | `18.5~19pt` | Bold, 深海蓝 `#1E3A8A` |
  | 表格表头文字 | Microsoft YaHei | `18~19pt` | Bold, 居中 |
  | 表格正文数据 | Calibri / Arial | `17pt` | Regular, 居中/左对齐 |
  | 表格 Ours 冠军行 | Calibri / Arial | `18pt` | Bold, 居中 |
  | 卡片正文 / 要点解析 | Microsoft YaHei | `16.5~17.5pt` | Regular, 行距 1.25~1.30, 饱满吸睛 |

---

### 铁律 5：关键成果与指标标红加粗 (Highlight in Bold Red)
* **色彩代码**：`#DC2626`（标准 Vivid Red，明艳且沉稳，非刺眼洋红）。
* **标红对象**：
  1. 刷新 SOTA 的指标（如 `41.42%`、`27.64% (断层第一)`、`56.54% (全场第一)`）。
  2. 关键突破数量（如 `587位行人`、`17个目标`、`1005个优质检测框`）。
  3. 核心技术优势定性词（如 `100%全覆盖`、`抗漏检实力顶尖`、`挽救10名盲区行人`）。
* **实现技术**：在 PptxGenJS 中必须使用富文本文本段数组 `[ { text: '前文', ... }, { text: '标红词', options: { color: 'DC2626', bold: true } } ]` 实现精准行内高亮。

---

### 铁律 6：基准对比方法必须注明发表年份 (Model Years)
* 在对比表格与实验环境介绍中，所有对比基准必须标注论文发表年份：
  * ✅ `FusionMamba (2024)`、`ITFuse (2024)`、`SFDFuse (2024)`、`MAEFuse (2024)`、`Ours (LAMF, 2026)`
  * ❌ `FusionMamba`、`ITFuse`（缺乏文献时效感与学术严密性）

---

### 铁律 7：主副标题文字极度精简 (Streamlined Headings)
* 坚决摒弃“关于...的研究”、“XX算法在XX条件下的分析实证”等行政化公文标题。
* 主标题控制在 6~12 个字以内，采用“章节号 + 核心对象 + 核心命题”结构：
  * 示例：`1.3 实验环境与基准设定`、`1.3 目标检测指标全基准对比`、`1.3 综合检测精度 (mAP) 直观对比`、`1.3 实景实证：夜市密集街景`。

---

### 铁律 8：零底注与多余杂质 (No Footnotes / Annotations)
* 严禁在页面左下角或底部添加“王纪凯研究员课题组版权所有”、“注：mAP计算阈值为0.5...”等破坏画面的蚊子字。
* 若有必要技术说明，直接将其融入卡片正文或表格说明行中，保持底部 100% 洁净，将宝贵的纵向空间全部留给大字号正文与高清大图。

---

### 铁律 9：原生矢量图表 (Native Office Charts)
* 避免使用静态截图代替柱状图。
* 柱状图、条形图等必须通过 `slide.addChart(pptx.ChartType.bar / col, data, options)` 动态生成，这样生成的 PPT 图表带有原生 Excel 数据源，用户双击即可在 Office 中修改数字或调整分类。

---

## 调色板定义 (Color Palette Tokens)

| Token 名称 | HEX 颜色码 | 适用对象 | 视觉心理学感受 |
| :--- | :--- | :--- | :--- |
| **Primary (顶栏蓝)** | `#4472C4` | 顶部通栏、主要强调色 | 经典企业科技蓝，稳健可靠 |
| **Highlight Red (突围红)** | `#DC2626` | 关键指标、突破成果、核心结论 | 鲜明视觉焦点，一眼锁定冠军数据 |
| **Header Text (深海蓝)** | `#1E3A8A` | 卡片子标题、分栏标题 | 庄重大气，建立清晰的信息层级 |
| **Body Dark (正文深灰)** | `#1E293B` | 表格文字、卡片正文、三线表线条 | 比纯黑更细腻柔和的高对比度学术色 |
| **Body Secondary (次级灰)** | `#475569` | 标签说明、辅助说明文本 | 清晰易读且不喧宾夺主 |
| **Card Fill (卡片背景)** | `#F8FAFC` | 洞察卡片背景、表格交替行 | 极淡蓝灰，轻微区分内容层次 |
| **Card Border (卡片描边)** | `#CBD5E1` | 卡片外框 | 0.75pt 精致浅灰边框 |
| **Ours Highlight (高亮底色)** | `#EEF2FF` 或 `#E0F2FE` | Ours 算法所在行背景 | 极浅亮蓝，突出自有算法 |

---

## 标准 PptxGenJS 代码实现模板 (开发者可直接复用)

```javascript
const pptxgen = require('pptxgenjs');
const pres = new pptxgen();

// 1. 设置 16:9 标准宽屏
pres.layout = 'LAYOUT_16x9'; // 13.333" x 7.50"

// 2. 通用色彩常数
const THEME = {
  BANNER_BLUE: '4472C4',
  HIGHLIGHT_RED: 'DC2626',
  TEXT_TITLE: '1E3A8A',
  TEXT_BODY: '1E293B',
  TEXT_MUTED: '475569',
  BORDER_COLOR: 'CBD5E1',
  BG_CARD: 'F8FAFC',
  BG_OURS: 'EEF2FF',
  TABLE_LINE: '1E293B'
};

// 3. 顶栏生成公共函数
function addTopBanner(slide, sectionNum, titleText) {
  // 顶部蓝色背景条
  slide.addShape(pres.ShapeType.rect, {
    x: 0.0, y: 0.0, w: 13.333, h: 0.76,
    fill: { color: THEME.BANNER_BLUE },
    line: { color: THEME.BANNER_BLUE, width: 0 }
  });

  // 章节编号 (Arial Black 34pt)
  slide.addText(sectionNum, {
    x: 0.28, y: 0.0, w: 1.20, h: 0.76,
    fontFace: 'Arial Black',
    fontSize: 34,
    color: 'FFFFFF',
    align: 'left',
    valign: 'middle'
  });

  // 精炼主标题 (微软雅黑加粗 28pt)
  slide.addText(titleText, {
    x: 1.45, y: 0.0, w: 11.50, h: 0.76,
    fontFace: 'Microsoft YaHei',
    fontSize: 28,
    bold: true,
    color: 'FFFFFF',
    align: 'left',
    valign: 'middle'
  });
}

// 4. 纯正科研三线表生成示例 (以 Slide 2 为例)
function createThreeLineTableSlide(pres) {
  const slide = pres.addSlide();
  addTopBanner(slide, '1.3', '目标检测指标全基准对比');

  const headers = [
    { text: 'Method', options: { bold: true, align: 'left' } },
    { text: 'mAP@0.5 (%)', options: { bold: true, align: 'center' } },
    { text: 'mAP50-95 (%)', options: { bold: true, align: 'center' } },
    { text: 'AP_People (%)', options: { bold: true, align: 'center' } },
    { text: 'AP_Car (%)', options: { bold: true, align: 'center' } },
    { text: 'AP_Motor (%)', options: { bold: true, align: 'center' } },
    { text: 'AP_Truck (%)', options: { bold: true, align: 'center' } },
    { text: 'AP_Bus (%)', options: { bold: true, align: 'center' } }
  ];

  // 构造行（包含发表年份和红色高亮）
  const tableRows = [
    // 表头行 (顶线 2.2pt, 底线 1.2pt, 无竖线)
    headers.map(h => ({
      text: h.text,
      options: {
        fontFace: 'Microsoft YaHei',
        fontSize: 18,
        bold: true,
        color: THEME.TEXT_BODY,
        align: h.options.align,
        valign: 'middle',
        fill: { color: 'FFFFFF' },
        border: {
          top: { style: 'solid', pt: 2.2, color: THEME.TABLE_LINE },
          bottom: { style: 'solid', pt: 1.2, color: THEME.TABLE_LINE },
          left: null,
          right: null
        }
      }
    })),
    // 对比算法常规行 (无内部横线, 无竖线)
    [
      { text: 'FusionMamba (2024)', options: { align: 'left' } },
      { text: '41.44', options: { align: 'center' } },
      { text: '26.72', options: { align: 'center' } },
      { text: '56.60', options: { align: 'center' } },
      { text: '71.10', options: { align: 'center' } },
      { text: '26.39', options: { align: 'center' } },
      { text: '15.15', options: { align: 'center' } },
      { text: '37.96', options: { align: 'center' } }
    ].map(cell => ({
      text: cell.text,
      options: {
        fontFace: 'Calibri',
        fontSize: 17,
        color: THEME.TEXT_BODY,
        align: cell.options.align,
        valign: 'middle',
        fill: { color: 'FFFFFF' },
        border: { top: null, bottom: null, left: null, right: null }
      }
    })),
    // Ours 算法冠军行 (底线 2.2pt 封底, 红色重点突出)
    [
      { text: 'Ours (LAMF, 2026)', options: { align: 'left', bold: true, color: THEME.HIGHLIGHT_RED } },
      { text: '41.42', options: { align: 'center', bold: true } },
      { text: '26.31', options: { align: 'center', bold: true } },
      { text: '56.54 (1st)', options: { align: 'center', bold: true, color: THEME.HIGHLIGHT_RED } },
      { text: '70.40', options: { align: 'center', bold: true } },
      { text: '27.64 (1st)', options: { align: 'center', bold: true, color: THEME.HIGHLIGHT_RED } },
      { text: '17.83', options: { align: 'center', bold: true } },
      { text: '34.69', options: { align: 'center', bold: true } }
    ].map(cell => ({
      text: cell.text,
      options: {
        fontFace: 'Calibri',
        fontSize: 18,
        bold: cell.options.bold || false,
        color: cell.options.color || THEME.TEXT_BODY,
        align: cell.options.align,
        valign: 'middle',
        fill: { color: THEME.BG_OURS },
        border: {
          top: null,
          bottom: { style: 'solid', pt: 2.2, color: THEME.TABLE_LINE },
          left: null,
          right: null
        }
      }
    }))
  ];

  // 满屏居中展示 (横向拉满 12.77")
  slide.addTable(tableRows, {
    x: 0.28,
    y: 1.10,
    w: 12.77,
    colW: [2.67, 1.45, 1.45, 1.44, 1.44, 1.44, 1.44, 1.44],
    rowH: [0.65, 0.55, 0.65],
    autoPage: false
  });
}

// 5. 富文本红字突出卡片示例
function addInsightCardWithRedHighlights(slide, x, y, w, h, title, runs) {
  // 卡片背景与白底
  slide.addShape(pres.ShapeType.roundRect, {
    x, y, w, h, rectRadius: 0.08,
    fill: { color: THEME.BG_CARD },
    line: { color: THEME.BORDER_COLOR, width: 0.8 }
  });

  // 卡片大标题 (18.5pt Bold)
  slide.addText(title, {
    x: x + 0.20, y: y + 0.15, w: w - 0.40, h: 0.45,
    fontFace: 'Microsoft YaHei',
    fontSize: 18.5,
    bold: true,
    color: THEME.TEXT_TITLE
  });

  // 富文本段落（以注满框图最大字号再小一号：16.5~17.5pt）
  slide.addText(runs, {
    x: x + 0.20, y: y + 0.65, w: w - 0.40, h: h - 0.80,
    fontFace: 'Microsoft YaHei',
    fontSize: 17,
    lineSpacingMultiple: 1.28,
    valign: 'top'
  });
}
```

---

## 结语：如何在日常工作中轻松调用
1. **在 Antigravity 环境中**：
   - 直接输入：“**请使用我的科研满框大字风格（academic-fullframe）生成...**”
   - 系统会自动调用技能内置模板和本规范。
2. **在 ChatGPT / Claude / DeepSeek 中**：
   - 复制顶部的【一键复制通用提示词 (Prompt)】粘贴到对话开头，即可快速调优生成代码或文字排版。
