# 学术满框大字三线表风格规范 (Academic-FullFrame Style)

> **风格代号**：`academic-fullframe` 或 `科研满框大字风格`  
> **适用场景**：科研成果汇报、企业技术攻关与专利汇报、学位论文答辩、SOTA模型横评  
> **核心原则**：全屏铺满无虚白，大字吸睛少折行；纯正三线拒网格，文献年份标括号；关键突围标亮红，精炼标题弃底注。

---

## 1. 核心视觉特征与设计硬约束

| 维度 | 规范要求 | 典型参数 |
| :--- | :--- | :--- |
| **画布比例** | 16:9 现代全高清宽屏 | `13.333" × 7.50"` (`LAYOUT_16x9`) |
| **顶栏母版** | 企业科技蓝背景条 + 白色大章节号 + 白色精炼主标题 | `y: 0.0, h: 0.76"`, 填充 `#4472C4`；序号 `Arial Black 34pt`；标题 `微软雅黑 28pt Bold` |
| **有效内容区** | 极度铺满画布，周边不留大片空白 (Zero Margin Waste) | `x: 0.28", w: 12.77", y: 0.88", h: 6.42"`（垂直利用率 86%，横向 96%） |
| **科研三线表** | 顶线 2.2pt、栏目线 1.2pt、底线 2.2pt；**严禁竖线，严禁内部网格线** | 线条颜色 `#1E293B`；整表横向拉满 `12.77"`，居中展布 |
| **对比方法年份** | 所有基准对比模型必须注明发表年份 | 例：`FusionMamba (2024)`、`ITFuse (2024)`、`Ours (LAMF, 2026)` |
| **字号原则** | **以注满框图的最大字号再小一号为准 (Max-1 Sizing)** | 表头 `18~19pt Bold`；数据 `17pt`；卡片标题 `18.5~19pt Bold`；正文 `16.5~17.5pt` |
| **核心重点标红** | 关键突破数字（AP、数量、召回率）与定性词汇全标红 | 醒目鲜红 `#DC2626` 加粗突出 |
| **底注控制** | **零底注与注解杂质** | 严禁左下角课题组标注或底部“注：...”微小文字，画面极致纯净 |
| **图表规范** | 原生矢量 Office 图表，内置数据可编辑 | `slide.addChart(pptx.ChartType.bar / col, data, options)` |

---

## 2. 配色系统 (Color Tokens)

```javascript
const THEME = {
  BANNER_BLUE: '4472C4',    // 顶栏主蓝
  HIGHLIGHT_RED: 'DC2626',  // 突围红色高亮 (突破指标/核心结论)
  TEXT_TITLE: '1E3A8A',     // 卡片标题深海蓝
  TEXT_BODY: '1E293B',      // 正文/数据深灰 (比纯黑更护眼柔和)
  TEXT_MUTED: '475569',     // 次要说明灰色
  BORDER_CARD: 'CBD5E1',    // 卡片描边浅灰
  BG_CARD: 'F8FAFC',        // 洞察卡片背景
  BG_OURS: 'EEF2FF',        // Ours 算法行高亮底色
  TABLE_LINE: '1E293B'      // 三线表深色边线
};
```

---

## 3. 版式与字号速查表

```
┌────────────────────────────────────────────────────────────────────────┐
│  1.3  实验环境与基准设定                                  (h: 0.76")   │ ← 顶栏蓝条 #4472C4
└────────────────────────────────────────────────────────────────────────┘
  x: 0.28", y: 0.88", w: 12.77", h: 6.42"
  ┌────────────────────────────────────────────────────────────────────┐
  │  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │ ← 顶线 2.2pt #1E293B
  │  表头项 (18~19pt YaHei Bold, 居中)                                 │
  │  ────────────────────────────────────────────────────────────────  │ ← 栏目线 1.2pt #1E293B
  │  对比算法行 (17pt Calibri/Arial, 无内部横线, 无竖线)               │
  │  对比算法行 (17pt Calibri/Arial, 标注发表年份如 2024)              │
  │  Ours 算法冠军行 (18pt Bold, 底色 #EEF2FF, 核心指标标红 #DC2626)   │
  │  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │ ← 底线 2.2pt #1E293B
  └────────────────────────────────────────────────────────────────────┘
  (底端拉满至 y: 7.30"，无任何底部注解或版权小字)
```

---

## 4. PptxGenJS 标准实现代码

### 4.1 顶栏绘制
```javascript
function addTopBanner(slide, sectionNum, titleText) {
  slide.addShape(pres.ShapeType.rect, {
    x: 0.0, y: 0.0, w: 13.333, h: 0.76,
    fill: { color: THEME.BANNER_BLUE },
    line: { color: THEME.BANNER_BLUE, width: 0 }
  });
  slide.addText(sectionNum, {
    x: 0.28, y: 0.0, w: 1.20, h: 0.76,
    fontFace: 'Arial Black', fontSize: 34, color: 'FFFFFF',
    align: 'left', valign: 'middle'
  });
  slide.addText(titleText, {
    x: 1.45, y: 0.0, w: 11.50, h: 0.76,
    fontFace: 'Microsoft YaHei', fontSize: 28, bold: true, color: 'FFFFFF',
    align: 'left', valign: 'middle'
  });
}
```

### 4.2 科研三线表参数构建
```javascript
// 表头单元格
const headerCell = (text, align = 'center') => ({
  text,
  options: {
    fontFace: 'Microsoft YaHei', fontSize: 18, bold: true, color: THEME.TEXT_BODY,
    align, valign: 'middle', fill: { color: 'FFFFFF' },
    border: {
      top: { style: 'solid', pt: 2.2, color: THEME.TABLE_LINE },
      bottom: { style: 'solid', pt: 1.2, color: THEME.TABLE_LINE },
      left: null, right: null
    }
  }
});

// 常规数据单元格 (无上下横线，无竖线)
const dataCell = (text, align = 'center') => ({
  text,
  options: {
    fontFace: 'Calibri', fontSize: 17, color: THEME.TEXT_BODY,
    align, valign: 'middle', fill: { color: 'FFFFFF' },
    border: { top: null, bottom: null, left: null, right: null }
  }
});

// Ours 封底单元格
const oursCell = (text, align = 'center', isRed = false) => ({
  text,
  options: {
    fontFace: 'Calibri', fontSize: 18, bold: true,
    color: isRed ? THEME.HIGHLIGHT_RED : THEME.TEXT_BODY,
    align, valign: 'middle', fill: { color: THEME.BG_OURS },
    border: {
      top: null,
      bottom: { style: 'solid', pt: 2.2, color: THEME.TABLE_LINE },
      left: null, right: null
    }
  }
});
```

---

## 5. 触发与调用方式
在与任何 AI 对话或在任务需求中，只要用户指明：
- “**使用科研满框大字风格**”
- “**使用企业学术三线表模板 (academic-fullframe)**”
- “**按照我原有的企业学术复刻版风格生成**”
即可立即全自动套用此规范。
