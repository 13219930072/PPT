# 用户专属 PPT 设计规范与默认风格指令 (User PPT Style Rule)

> **触发条件**：当用户在当前工作区提出生成 PPT、制作幻灯片、排版演示文稿、生成 PptxGenJS 代码或调整现存 PPT 时，必须强制遵守本规则。

---

## 默认核心风格：企业学术满框大字三线表风格 (`academic-fullframe`)

除非用户在提示词中明确指定了其他完全不同的风格（如“乔布斯极简发布会”、“活力橙活动海报”等），否则**默认全部采用此专属风格**。

### 9 大核心设计铁律

1. **画布母版与比例**：
   - 必须为 16:9 现代宽屏（`13.333" × 7.50"`，即 `LAYOUT_16x9`）。
   - 顶部通栏：企业科技蓝背景条（`y: 0.0, h: 0.76"`, fill: `4472C4`）。
   - 顶栏文字：左侧大章节号（`Arial Black 34pt`, 白色），右侧精简主标题（`微软雅黑 28pt Bold`, 白色）。

2. **满屏排布，边框不留虚白 (Zero Margin Waste)**：
   - 严禁边缘大片空白！
   - 横向：左边距 `x: 0.28"`，右边缘至 `13.05"`，有效内容宽度 `12.77"`（利用率 96%）。
   - 纵向：紧贴顶栏下方 `y: 0.88"`，底端拉满至 `y: 7.30"`，有效内容高度 `6.42"`（利用率 86%）。

3. **纯正科研三线表 (Scientific Three-Line Table)**：
   - 顶线：`2.2pt` 粗深灰实线（`#1E293B`）。
   - 栏目线：`1.2pt` 深灰实线（`#1E293B`）。
   - 底线：`2.2pt` 粗深灰实线（`#1E293B`）。
   - **严禁竖线**（全部为 null），**严禁内部横向网格线**（全部为 null）。
   - 纯学术三线表必须全屏拉满 `12.77"` 宽度展示，严禁与左右狭窄的文字卡强行挤在一页。

4. **字号准则——以注满框图的最大字号再小一号为准 (Max-1 Sizing)**：
   - 严禁低于 `15pt` 的微小文字！
   - 表头文字：`18~19pt Bold`；数据正文：`17pt Regular`；Ours 行：`18pt Bold`。
   - 卡片大标题/分栏标题：`18.5~19pt Bold`。
   - 卡片说明/分析正文：`16.5~17.5pt Regular`，行距 `lineSpacingMultiple: 1.25~1.30`，饱满大气。
   - 核心突破数字看板（KPI Callout）：`38~42pt Bold`。

5. **核心成果与指标标红加粗 (Highlight in Bold Red)**：
   - 关键突破数据（mAP、检出量、提升百分比、Recall、F1等）与硬核结论词汇（如“全场第一”、“断层第一”、“100%全覆盖”、“抗漏检实力顶尖”）必须标为醒目红色加粗（`#DC2626` / `DC2626`）。

6. **对比基准方法必须注明发表年份 (Model Years)**：
   - 所有横向评测基准算法，名称后必须加括号标注其论文发表年份（如 `FusionMamba (2024)`、`ITFuse (2024)`、`SFDFuse (2024)`、`MAEFuse (2024)`、`Ours (LAMF, 2026)`）。

7. **主副标题文字极度精炼 (Streamlined Headings)**：
   - 主标题控制在 6~12 字内，拒绝公文套话，直切主题（如“1.3 实验环境与基准设定”、“1.3 实景实证：夜市密集街景”）。

8. **零底注与注解杂质 (No Footnotes / Annotations)**：
   - 页面左下角与底部严禁放置课题组署名、版权小字或“注：...”等注解，保持画面极致干净。

9. **原生矢量图表 (Native Office Charts)**：
   - 柱状图、对比图等必须调用 `slide.addChart` 原生 Office 图表对象，便于双击在 Excel 中修改数据。

---

## 关键代码参考文件
- 完整风格规范与 AI 提示词模板：[我的PPT定制风格规范与AI提示词模板.md](file:///c:/WorkSpace/downstream_detection_results/我的PPT定制风格规范与AI提示词模板.md)
- 技能内置风格参考：[academic-fullframe-style.md](file:///c:/WorkSpace/downstream_detection_results/.agents/skills/ppt-master/references/academic-fullframe-style.md)
- 现有完美生成范本：[LAMF_科研汇报_V3_企业模板复刻版.pptx](file:///c:/WorkSpace/downstream_detection_results/生成的PPT与汇报材料/LAMF_科研汇报_V3_企业模板复刻版.pptx)
