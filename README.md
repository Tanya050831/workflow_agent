# AI Agent for Complex Physics Problem Solving

# 复杂物理问题求解的AI智能体

## Abstract | 摘要

Scientific reasoning represents one of the most challenging aspects of education, requiring students to integrate multiple forms of information and apply complex problem-solving strategies. This project develops an innovative agent-based framework to solve complex illustrated physics problems, leveraging platforms like Coze and Hiagent to create a specialized agent that mimics human problem-solving by interpreting multimodal information. This approach demonstrates a viable pathway for creating sophisticated AI tutors for advanced scientific education.

科学推理是教育中最具挑战性的方面之一，要求学生整合多种形式的信息并应用复杂的问题解决策略。本项目开发了一个创新的基于智能体的框架来解决复杂的图示物理问题，利用Coze和Hiagent等平台创建一个专门的智能体，通过解释多模态信息来模拟人类的问题解决过程。这种方法为创建先进的科学教育AI导师提供了一条可行的途径。

## Introduction | 简介

### Dataset | 数据集

We developed an agent to solve a diverse dataset of **2,000 physics problems**. This dataset includes:

我们开发了一个智能体来解决包含**2000个物理问题**的多样化数据集。该数据集包括：

- **Languages**: Questions in both Chinese and English
- **Languages | 语言**: 中英文问题
- **Categories**: Eight distinct categories (CM, OPT, ACG, EM, QMIT, AMONP, TSM)
- **Categories | 类别**: 八个不同类别（CM, OPT, ACG, EM, QMIT, AMONP, TSM）
- **Difficulty Levels**: Seven distinct difficulty levels, ranging from middle school to doctoral studies
- **Difficulty Levels | 难度级别**: 七个不同的难度级别，从中学到博士研究

### Methodology | 方法论

We adopted a controlled experimental approach to enhance the workflow's performance. We isolated and evaluated several key components as single variables:

我们采用受控实验方法来提升工作流的性能。我们将几个关键组件作为单一变量进行隔离和评估：

1. **Model Architecture | 模型架构**
   - **Unified Multimodal**: Using a single multimodal model (Model_Only_MultiModal) for both diagram interpretation and reasoning
   - **统一多模态**: 使用单一多模态模型（Model_Only_MultiModal）进行图表解释和推理
   - **Core Engine Swap**: Replacing the baseline reasoning model with a more powerful one (Model_Deepseek-r1)
   - **核心引擎替换**: 用更强大的模型（Model_Deepseek-r1）替换基线推理模型

2. **Language | 语言**
   - Applying a Chinese-to-English translation pre-processing step to standardize the input
   - 应用中英文翻译预处理步骤以标准化输入

3. **RAG (Retrieval-Augmented Generation) | 检索增强生成**
   - **Textbook RAG**: Using only foundational textbook knowledge
   - **教科书RAG**: 仅使用基础教科书知识
   - **Enhanced RAG**: Augmenting textbooks with a database of 1,800 solved problems with detailed solutions
   - **增强RAG**: 用包含1800个已解决问题及详细解答的数据库增强教科书知识

4. **Feedback | 反馈**
   - Implementing a self-correcting feedback loop for the agent
   - 为智能体实现自我纠正反馈循环

## Problem-Solving Methodology | 问题解决方法论

### Architecture | 架构

![Problem-Solving Methodology](images/methodology.png)

*Figure 1: Problem-Solving Methodology Architecture*

*图1: 问题解决方法论架构*

Our system consists of:

我们的系统包括：

- **Core Agent**: Central reasoning component (represented by a brain within a chip)
- **核心智能体**: 中央推理组件（以芯片中的大脑图标表示）
- **Input Stage**: Processes multimodal input (text and diagrams)
- **输入阶段**: 处理多模态输入（文本和图表）
- **Output Stage**: Generates solutions
- **输出阶段**: 生成解决方案
- **Supporting Components**:
  - **支持组件**:
  - Retrieval-Augmented Generation (RAG)
  - 检索增强生成（RAG）
  - Diagram Interpretation
  - 图表解释
  - Core Model
  - 核心模型

### Experimental Design | 实验设计

We conducted a rigorous ablation study, isolating one variable at a time to measure the impact of each component. Each configuration was evaluated based on its accuracy on our 200-problem development set.

我们进行了严格的消融研究，每次隔离一个变量以测量每个组件的影响。每个配置都基于我们在200个问题的开发集上的准确率进行评估。

## Results | 结果

### Performance Comparison | 性能对比

![Results Table](images/results_table.png)

*Figure 2: Performance Comparison Results*

*图2: 性能对比结果*

| Method / Component | Percent | 方法/组件 | 百分比 |
|-------------------|---------|----------|--------|
| Baseline | 0.350 | 基线 | 0.350 |
| Model: Model_Only_MultiModal | 0.290 | 模型: Model_Only_MultiModal | 0.290 |
| Model: Model_Deepseek-r1 | 0.400 | 模型: Model_Deepseek-r1 | 0.400 |
| Language: Language_Chi_translate_to_Eng | **0.395** | 语言: 中文翻译为英文 | **0.395** |
| RAG: RAG_without1800 | 0.375 | RAG: 无1800题RAG | 0.375 |
| RAG: RAG_with1800 | 0.380 | RAG: 有1800题RAG | 0.380 |
| Feedback: Feedback_Use | 0.350 | 反馈: 使用反馈 | 0.350 |
| **Integrated Method** | **0.450** | **集成方法** | **0.450** |

### Key Findings | 关键发现

1. **Overall Accuracy Boost**: The Integrated Method boosts overall accuracy from **35.0%** (70/200) to **45.0%** (90/200)
   - **整体准确率提升**: 集成方法将整体准确率从**35.0%**（70/200）提升到**45.0%**（90/200）

2. **Primary Gain**: The integrated method successfully corrected **35 problems** that the baseline failed
   - **主要收益**: 集成方法成功纠正了基线失败的**35个问题**

3. **Performance Trade-off**: The new method introduced errors on **15 problems** that the baseline had previously answered correctly
   - **性能权衡**: 新方法在基线先前正确回答的**15个问题**上引入了错误

4. **Net Improvement**: The net gain is **20 correct answers** (35 improvements - 15 regressions)
   - **净改进**: 净收益为**20个正确答案**（35个改进 - 15个回归）

5. **Future Challenges**: **95 problems** remained incorrect for both methods, indicating difficult cases for future research
   - **未来挑战**: **95个问题**在两种方法中都保持错误，表明这些是未来研究的困难案例

![Analysis Sankey Diagram](images/analysis_sankey.png)

*Figure 3: Performance Analysis - Baseline vs Integrated Method*

*图3: 性能分析 - 基线方法 vs 集成方法*

### Component Analysis | 组件分析

- **Component Synergy is Crucial**: The integrated method, combining effective components, achieved 45.0% accuracy, outperforming the 35.0% baseline
  - **组件协同至关重要**: 集成方法结合有效组件，达到45.0%的准确率，优于35.0%的基线

- **Core Model and Language Matter Most**: Selecting a powerful foundation model (Model_Deepseek-r1) and a strategic language translation approach were the most impactful individual improvements
  - **核心模型和语言最重要**: 选择强大的基础模型（Model_Deepseek-r1）和策略性语言翻译方法是最具影响力的单项改进

- **RAG Provides Consistent Gains**: The integration of Retrieval-Augmented Generation (RAG) consistently enhanced performance, confirming the value of external knowledge retrieval
  - **RAG提供一致收益**: 检索增强生成（RAG）的集成持续提升性能，证实了外部知识检索的价值

- **Feedback Mechanism**: The initial feedback mechanism did not yield improvements in this iteration
  - **反馈机制**: 初始反馈机制在此次迭代中未产生改进

## ICML 2025 SeePhys Challenge | ICML 2025 SeePhys挑战赛

### The Challenge | 挑战赛介绍

**ICML 2025 Challenge Track 2: Physics Reasoning with Diagrams and Expressions (SeePhys)**

**ICML 2025挑战赛道2: 带图表和表达式的物理推理（SeePhys）**

- **Host**: The International Conference on Machine Learning (ICML), a top-tier conference in AI
- **主办方**: 国际机器学习会议（ICML），AI领域的顶级会议
- **Task**: Tests a model's ability to solve complex physics problems by integrating textual descriptions with corresponding diagrams
- **任务**: 测试模型通过整合文本描述和相应图表来解决复杂物理问题的能力
- **Scope**: Features a comprehensive set of 2,000 problems, with topics ranging from middle school classical mechanics to PhD-level modern physics
- **范围**: 包含2000个问题的综合集合，主题从中学经典力学到博士级别的现代物理

### Our Achievement | 我们的成就

- **Ranked 11th out of 130 International Participants**
  - **在130个国际参赛团队中排名第11**
  - Placing our team in the **top 8.5%** of all competing teams
  - 将我们的团队置于所有参赛团队的**前8.5%**

- **Achieved 42.50% Accuracy**
  - **达到42.50%的准确率**
  - On the complete and challenging test set of 2000 multimodal problems
  - 在包含2000个多模态问题的完整且具有挑战性的测试集上

- **Validation**: This outstanding result validates the effectiveness of our approach in advanced scientific reasoning and establishes a strong performance benchmark
  - **验证**: 这一出色结果验证了我们在高级科学推理方面方法的有效性，并建立了强大的性能基准

## Conclusion | 结论

In this work, we developed and systematically evaluated an agent-based framework for solving complex, illustrated physics problems. Our analysis, conducted on a 200-problem development set, reveals several key insights:

在这项工作中，我们开发并系统评估了一个基于智能体的框架，用于解决复杂的图示物理问题。我们在200个问题的开发集上进行的分析揭示了几个关键见解：

1. **Component Synergy is Crucial**: An integrated method combining effective components achieved 45.0% accuracy, demonstrating the superiority of a holistic approach over single enhancements.
   - **组件协同至关重要**: 结合有效组件的集成方法达到45.0%的准确率，证明了整体方法优于单一增强。

2. **Core Model and Language Matter Most**: Selecting a powerful foundation model and a strategic language translation approach were the most impactful individual improvements.
   - **核心模型和语言最重要**: 选择强大的基础模型和策略性语言翻译方法是最具影响力的单项改进。

3. **RAG Provides Consistent Gains**: The integration of Retrieval-Augmented Generation consistently enhanced performance, confirming the value of external knowledge retrieval.
   - **RAG提供一致收益**: 检索增强生成的集成持续提升性能，证实了外部知识检索的价值。

The strategic integration of these successful components allowed us to build a highly effective system. This result validates our agent-based methodology as a powerful and promising direction for tackling sophisticated multimodal scientific reasoning tasks.

这些成功组件的策略性集成使我们能够构建一个高效的系统。这一结果验证了我们的基于智能体的方法论是解决复杂多模态科学推理任务的有力且有前景的方向。

## Images | 图片说明

All images used in this README are stored in the `images/` directory. To add new images:

本README中使用的所有图片都存储在 `images/` 目录中。添加新图片的方法：

1. **Place your image file** in the `images/` folder
   - **将图片文件**放入 `images/` 文件夹

2. **Use Markdown syntax** in README.md:
   - **在README.md中使用Markdown语法**:
   ```markdown
   ![Image Description](images/filename.png)
   ```

3. **For size control**, use HTML:
   - **控制大小**，使用HTML:
   ```html
   <img src="images/filename.png" alt="Image Description" width="500">
   ```

4. **For GitHub**, use relative paths (images/filename.png) or raw GitHub URLs
   - **对于GitHub**，使用相对路径（images/filename.png）或GitHub raw链接

### Workflow Diagrams | 工作流图表

For detailed workflow diagrams of all experimental configurations, see:

所有实验配置的详细工作流图表，请参见：

- **[images/workflows.md](images/workflows.md)** - Complete workflow documentation with diagrams
- **[images/workflows.md](images/workflows.md)** - 包含图表的完整工作流文档

**Available Workflows | 可用工作流**:
- Baseline Workflow | 基线工作流 (35.0% accuracy)
- Model Configurations | 模型配置
- Language Translation | 语言翻译
- RAG Configurations | RAG配置
- Feedback Loop | 反馈循环
- Integrated Method | 集成方法 (45.0% accuracy)

## Project Structure | 项目结构

This repository is organized as follows:

本仓库组织结构如下：

```
├── README.md                    # Main documentation (this file)
├── PROJECT_STRUCTURE.md         # Project structure recommendations
├── images/                      # Images and diagrams
├── docs/                        # Documentation
│   ├── workflow/               # Workflow documentation
│   ├── dataset/                # Dataset documentation
│   └── feishu_docs/            # Feishu documents (converted)
├── workflows/                  # Coze workflow resources
│   ├── coze_export/           # Exported workflow configs
│   └── screenshots/           # Workflow screenshots
├── resources/                  # External resources
│   ├── links.md               # External links (Coze, Feishu, etc.)
│   └── references/           # References
├── scripts/                    # Utility scripts
├── examples/                   # Usage examples
└── ...
```

### Quick Links | 快速链接

- **📚 Documentation**: [docs/](docs/)
  - Workflow: [docs/workflow/](docs/workflow/)
  - Dataset: [docs/dataset/](docs/dataset/)
  
- **🔧 Workflows**: [workflows/](workflows/)
  - Coze workflow: [workflows/README.md](workflows/README.md)
  
- **🔗 Resources**: [resources/](resources/)
  - External links: [resources/links.md](resources/links.md)
  
- **📖 Examples**: [examples/](examples/)

## Accessing Coze Resources | 访问Coze资源

The project uses Coze platform for workflow implementation and data storage:

本项目使用Coze平台进行工作流实现和数据存储：

- **Coze Workflow**: See [resources/links.md](resources/links.md) for access links
  - **Coze工作流**: 参见 [resources/links.md](resources/links.md) 获取访问链接
- **Knowledge Bases**: Physics textbook content and solved problems database
  - **知识库**: 物理课本内容和已解决问题数据库
- **Workflow Documentation**: Detailed documentation in [workflows/](workflows/) and [docs/workflow/](docs/workflow/)
  - **工作流文档**: 详细文档在 [workflows/](workflows/) 和 [docs/workflow/](docs/workflow/)

## Future Work | 未来工作

- [x] Project structure setup
- [x] 项目结构设置
- [x] Documentation framework
- [x] 文档框架
- [ ] Add Coze workflow screenshots
- [ ] 添加Coze工作流截图
- [ ] Migrate Feishu documents
- [ ] 迁移飞书文档
- [ ] Add usage examples
- [ ] 添加使用示例
- [ ] Further improvements on the 95 consistently incorrect problems
- [ ] 对95个持续错误问题的进一步改进

## Local Development | 本地开发

This project can be developed locally in Cursor. For local workflow guide, see:

本项目可以在Cursor中本地开发。本地工作流指南，请参见：

- **[LOCAL_WORKFLOW.md](LOCAL_WORKFLOW.md)** - Complete guide for local development and GitHub push
- **[LOCAL_WORKFLOW.md](LOCAL_WORKFLOW.md)** - 本地开发和GitHub推送完整指南

**Quick Start | 快速开始**:
1. Edit and complete content locally in Cursor
   - 在Cursor中本地编辑和完善内容
2. When ready, push to GitHub (we can help with Git operations)
   - 准备好后，推送到GitHub（我们可以帮助处理Git操作）

---

**Note**: For detailed project structure recommendations, see [PROJECT_STRUCTURE.md](PROJECT_STRUCTURE.md).

**注意**: 详细的项目结构建议，请参见 [PROJECT_STRUCTURE.md](PROJECT_STRUCTURE.md)。

