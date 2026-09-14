# 科研全流程精选开源 Agent Skills 推荐指南
> **面向深度学习与科研工作者**：模型改进 · 论文写作 · 汇报展示 · 学术制图

---

## 目录

1. [背景与科研 Skills 生态概览](#1-背景与科研-skills-生态概览)
2. [第一板块：模型改进与前沿复现类 Skills](#2-第一板块模型改进与前沿复现类-skills)
3. [第二板块：学术论文写作、润色与审稿类 Skills](#3-第二板块学术论文写作润色与审稿类-skills)
4. [第三板块：企业与学术汇报 PPT 类 Skills](#4-第三板块企业与学术汇报-ppt-类-skills)
5. [第四板块：模型架构图、学术配图与图像生成类 Skills](#5-第四板块模型架构图学术配图与图像生成类-skills)
6. [全局安装与工程部署指南](#6-全局安装与工程部署指南)
7. [端到端科研工作流协同实战](#7-端到端科研工作流协同实战)

---

## 1. 背景与科研 Skills 生态概览

在 AI 辅助科研（AI for Science / AI-assisted Research）中，通用大模型往往缺乏对**学术界严格规范（LaTeX 语法、审稿人挑刺逻辑、顶会制图色彩哲学、学术论述结构）**的针对性约束。

通过引入开源社区专门提炼沉淀的 **Agent Skills（专家指令与工具流包）**，可以让您的 AI 助手瞬间具备顶级科研实验室的思维框架：

```
                ┌──────────────────────────────────────────────┐
                │             科研全流程 Agent Skills 矩阵      │
                └──────────────────────┬───────────────────────┘
                                       │
         ┌──────────────────┬──────────┴──────────┬──────────────────┐
         ▼                  ▼                     ▼                  ▼
  【1. 模型改进】       【2. 论文写作】       【3. 汇报展示】     【4. 学术配图】
  • 顶会论文转代码      • CV/ML写作框架      • PPT Master        • 模型架构总览图
  • Baseline 复现       • 学术降AI痕迹        • 汇报逻辑蓝图      • 顶会Python制图
  • 消融实验设计        • 审稿人压力测试      • 原生可编辑 PPTX    • 矢量图表生成
```

---

## 2. 第一板块：模型改进与前沿复现类 Skills

在深度学习研究中，模型改进通常面临两大痛点：**最新 arXiv 论文开源代码繁杂不易抽取关键 Block**、**自身模型的创新动机（Motivation）与消融实验（Ablation Study）设计不够严谨**。

### 推荐 1：`paper2code` —— 论文核心模块一键转 PyTorch 代码
* **GitHub 仓库**：[PrathamLearnsToCode/paper2code](https://github.com/PrathamLearnsToCode/paper2code)
* **社区热度**：⭐ 1,500+ Stars
* **核心功能**：
  * 输入任意 arXiv 论文链接或 PDF，自动提取论文中提出的网络架构公式（Architecture Equations）。
  * 按照模块化封装（如 `nn.Module`）直接生成开箱即用的 PyTorch 前向传播与多模态特征融合核心代码。
  * 自动补全张量维度注释（Tensor Shape Comments），方便您直接将新出的 Attention / Mamba / 门控融合结构移至自己的项目中。
* **适用场景**：
  * 想把其他前沿论文中的新模块（如最新的 SSM、局部增强机制）移植到自己的模型中作为对比或改进点。

### 推荐 2：`PaperSpine` —— 模型创新动机与论文脊梁构建 Skill
* **GitHub 仓库**：[WUBING2023/PaperSpine](https://github.com/WUBING2023/PaperSpine)
* **社区热度**：⭐ 5,200+ Stars
* **核心功能**：
  * 专门提取顶会论文的 **Central Argument（核心论据）** 与 **Motivation（模型改进逻辑链）**。
  * 辅助设计基准对比（Baseline Selection）与递进式消融实验（Component-wise Ablation Matrix）。
  * 避免盲目刷榜，帮助您梳理出“因为观察到了什么理论缺陷，所以提出了何种针对性架构改进”的严谨故事线。
* **适用场景**：
  * 模型实验做完了，但不知道如何将改进点包装成具备足够理论支撑和审稿人说服力的核心创新点。

### 推荐 3：`paper-search-mcp` —— 跨文献库检索与代码定位工具
* **GitHub 仓库**：[openags/paper-search-mcp](https://github.com/openags/paper-search-mcp)
* **社区热度**：⭐ 2,600+ Stars
* **核心功能**：
  * 跨 arXiv、PapersWithCode、PubMed 等平台秒级检索同赛道最新 SOTA 方法。
  * 自动定位其官方开源代码与 Benchmark 评估数据，便于直接拉入下游做公正横向评测。

---

## 3. 第二板块：学术论文写作、润色与审稿类 Skills

论文写作阶段，审稿人最常诟病的几点是：**Introduction 缺乏冲突与吸引力**、**AI 润色痕迹过重（泛滥使用 delve, crucial, testament 等空洞词）**、**LaTeX 编译与引用冲突**。

### 推荐 1：`Research-Paper-Writing-Skills` —— 顶会大牛方法论萃取
* **GitHub 仓库**：[Master-cai/Research-Paper-Writing-Skills](https://github.com/Master-cai/Research-Paper-Writing-Skills)
* **社区热度**：⭐ 6,700+ Stars（国内顶流）
* **核心功能**：
  * 改编自浙江大学知名学者团队的公开科研笔记，针对 CVPR / ICCV / ECCV / NeurIPS 等顶会论文写作量身定制。
  * 涵盖 Abstract（摘要四要素）、Introduction（引言争鸣叙事法）、Method（公式与符号规范化定义）、Experiments（实验对比话术与分析段落）。
  * 内置高质量 Rebuttal（审稿意见防御与正面答辩）模板与应答策略。
* **适用场景**：
  * 计算机视觉、多模态与机器学习领域英文学术论文的全篇起草、段落扩写与逻辑修补。

### 推荐 2：`academic-writing-skills` —— 论文后处理、校验与盲审工具包
* **GitHub 仓库**：[bahayonghang/academic-writing-skills](https://github.com/bahayonghang/academic-writing-skills)
* **社区热度**：⭐ 450+ Stars
* **核心功能**：
  * 包含 5 个专门面向 LaTeX / Typst 论文的子技能：
    1. **Format Validation**：LaTeX 格式合规性检查（Overfull hbox、标签未引用等）。
    2. **Academic Grammar & Style**：消除口语化表达，替换为地道学术书面语。
    3. **De-AI Editing**：**深度去除 AI 腔调**，破除呆板的长定语从句，恢复人类学术作者的精炼节奏。
    4. **Reference Checker**：BibTeX 交叉引用与规范化核查。
    5. **Reviewer Audit**：模拟严肃审稿人进行全篇挑刺。
* **适用场景**：
  * 论文初稿完成后的“最后一公里”精修、降重、去 AI 痕迹与格式排版体检。

### 推荐 3：`paperjury` —— 投递前的审稿人压力测试 Skill
* **GitHub 仓库**：[Spark-To-Paper-Skills/paperjury](https://github.com/Spark-To-Paper-Skills/paperjury)
* **社区热度**：⭐ 1,100+ Stars
* **核心功能**：
  * 模拟 3 位学术脾气不同的审稿人（严苛型、注重实验型、注重理论型）进行 pre-submission 压力测试。
  * 输出详细的 Weaknesses 清单并预测 Reject 风险点，同时直接给出“该加什么实验”、“该怎么在文中打补丁”的具体修改建议。

### 推荐 4：`sepia` —— 基于顶刊风格自适应的学术润色 Skill
* **GitHub 仓库**：[Nanako0129/sepia](https://github.com/Nanako0129/sepia)
* **社区热度**：⭐ 2,500+ Stars
* **核心功能**：
  * 基于 StoryScope（arXiv:2604.03136）自然语言学术叙事修复理论。
  * 根据您目标投递的期刊/会议（如 IEEE TPAMI、TIP、CVPR）自动匹配对应领域的词汇密度和句式风格。

---

## 4. 第三板块：企业与学术汇报 PPT 类 Skills

用于向企业领导汇报落地成果、或在学术会议/组会中展示科研进展，要求**可编辑原生格式**、**图表驱动**、**杜绝廉价企业花哨模板**。

### 推荐 1：`ppt-master` —— 专业级 PPT 生成与设计技能（当前已装好）
* **GitHub 仓库**：[Categorytyy/ppt-master](https://github.com/Categorytyy/ppt-master)
* **核心优势**：
  * **设计理论落地**：融合 CRAP（对比/重复/对齐/接近）四大设计原理与场景信息密度法则。
  * **PptxGenJS 原生代码生成**：生成的 `.pptx` 包含原生矢量卡片、原生可编辑图表与表格，拒绝“死板不可编辑截图”。
  * **多场景自适应**：支持严谨学术答辩风、企业战略汇报风、技术分享风。
* **使用状态**：已为您安装在全局目录，随时支持调用。

### 推荐 2：`ppt-master-plus` —— 增强版 PPT 智能排版与模版注入 Skill
* **GitHub 仓库**：[gnuhpc/ppt-master-plus](https://github.com/gnuhpc/ppt-master-plus)
* **社区热度**：⭐ 47+ Stars（高潜力演进版）
* **核心功能**：
  * 支持直接将已有的 `.pptx` 作为 Brand/Template 输入，在保留原有模板母版版式的前提下，将新的实验数据和成果自动“灌入”对应版块。
  * 增强了对复杂多栏对比、排版自适应与原生图形渲染。

### 推荐 3：`notebooklm-ppt-architect` —— 实验数据长文转汇报蓝图
* **GitHub 仓库**：[encoreshao/notebooklm-ppt-architect](https://github.com/encoreshao/notebooklm-ppt-architect)
* **社区热度**：⭐ 5 Stars
* **核心功能**：
  * 擅长将厚重冗长的实验日志、数据 CSV 和技术文档提炼为“业务价值明确、故事线清晰”的高管/评委汇报大纲。

---

## 5. 第四板块：模型架构图、学术配图与图像生成类 Skills

顶级学术论文的成败，“配图质量”往往决定第一印象。需要掌握**模型架构图（Figure 1/2）**、**实验趋势折线图/柱状图**以及**概念示意图**的高清排版。

### 推荐 1：`paper-framework-figure-studio-pro` —— 顶会模型架构总览图工坊
* **GitHub 仓库**：[c-narcissus/paper-framework-figure-studio-pro](https://github.com/c-narcissus/paper-framework-figure-studio-pro)
* **社区热度**：⭐ 2,100+ Stars
* **核心功能**：
  * 专攻 CVPR / NeurIPS / IEEE 级别的 **Method Overview / Framework Diagram（模型系统总览图）**。
  * 引导式多轮对话：从 Encoder-Decoder 拓扑、特征流向（Feature Dimensions）、交互注意力机制，逐步输出高质量 SVG / TikZ 矢量代码。
  * 严格遵循顶会配色系统（柔和低饱和度莫兰迪色系 / 经典学术蓝灰体系），拒绝刺眼大红大绿。
* **适用场景**：
  * 绘制论文正文必须的核心算法结构图、多模态融合流动管线图。

### 推荐 2：`figures4papers` —— 顶会高水准 Python 科研制图脚本库
* **GitHub 仓库**：[ChenLiu-1996/figures4papers](https://github.com/ChenLiu-1996/figures4papers)
* **社区热度**：⭐ 5,000+ Stars
* **核心功能**：
  * 耶鲁大学博士开源的顶级会议科研绘图代码库。
  * 提供了各种用于论文的复杂图表模板：包含置信度分布散点图、消融对比雷达图、多模态多指标柱状图、特征热力图覆盖。
  * 默认适配单栏/双栏 LaTeX 尺寸（IEEE / ACM / NeurIPS 页面宽度），字体与 LaTeX 无缝对齐。

### 推荐 3：`academic-figure-generator` —— 论文配图提示词与生成平台
* **GitHub 仓库**：[LigphiDonk/academic-figure-generator](https://github.com/LigphiDonk/academic-figure-generator)
* **社区热度**：⭐ 2,300+ Stars
* **核心功能**：
  * 自动分析论文方法论，生成匹配 Midjourney / FLUX / DALL-E 的高精度科研示意图 Prompt。
  * 提供通用的矢量插图与图形资产拼接支持。

---

## 6. 全局安装与工程部署指南

在当前 Antigravity / Gemini CLI 体系中，技能的安装极度简单，推荐采用**全局部署法**，一次安装后对您电脑上的所有项目永久生效。

### 步骤 1：确认全局配置目录
全局配置根路径固定为：
```
C:\Users\24538\.gemini\config\skills\
```

### 步骤 2：下载并解压目标 Skill
例如想安装顶会写作技能 `Research-Paper-Writing-Skills`：
1. 打开终端（PowerShell），直接克隆到全局目录：
   ```powershell
   git clone https://github.com/Master-cai/Research-Paper-Writing-Skills.git "C:\Users\24538\.gemini\config\skills\paper-writing"
   ```
2. 只要该文件夹根目录下包含 `SKILL.md`，AI 助手在每次启动新任务时就会**自动识别并加载该技能**。

### 步骤 3：依赖安装（若技能包含脚本）
如果技能内部包含 `package.json`（如 `ppt-master`），只需在子目录执行 `npm install` 即可：
```powershell
cd "C:\Users\24538\.gemini\config\skills\<技能目录>\assets"
npm install
```

---

## 7. 端到端科研工作流协同实战

当您把上述推荐的优质 Skills 部署后，可以形成一套行云流水的科研全周期协作闭环：

| 阶段 | 协同调用 Skill | 具体指令示例 |
| :--- | :--- | :--- |
| **阶段 1：模型设计与改进** | `paper2code` + `PaperSpine` | *“帮我研读这篇 Mamba 融合新论文，提炼其核心公式，并结合我的模型设计消融实验。”* |
| **阶段 2：高质量实验绘图** | `figures4papers` + `paper-framework-figure-studio-pro` | *“根据本项目的 downstream detection CSV 数据，绘制符合 IEEE 双栏标准的 AP50 对比柱状图，并设计方法总览图。”* |
| **阶段 3：论文撰写与精修** | `Research-Paper-Writing-Skills` + `academic-writing-skills` | *“按照 CVPR 标准起草 Method 与 Experiment 章节，随后进行去 AI 痕迹润色并检查 LaTeX 格式。”* |
| **阶段 4：答辩与企业汇报** | `ppt-master` (已装) | *“基于当前检测实测结果与图表，生成一份以直观图表为主、符合学术规范的可编辑 PPT 演示文稿。”* |

---
*本文档已整理保存在您的工作区：`c:\WorkSpace\downstream_detection_results\科研全流程开源Skills推荐指南.md`，方便您随时查阅与挑选安装。*
