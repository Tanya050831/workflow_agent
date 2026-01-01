# Prompts Directory | 提示词目录

This directory contains all the prompt templates used in the Coze workflow for the physics problem-solving agent. These prompts are configured for different nodes in the workflow to guide the models' behavior and output format.

本目录包含物理问题求解智能体在Coze工作流中使用的所有提示词模板。这些提示词配置在工作流的不同节点中，用于指导模型的行为和输出格式。

## Directory Structure | 目录结构

```
prompts/
├── README.md                                    # 本文件
├── baseline_prompt.png                         # 基线提示词截图
├── problem_solving_model_without_RAG.md        # 基线解题模型提示词（无RAG）
├── problem_solving_model_with_RAG.md           # 解题模型提示词（含RAG）
├── RAG_prompt.png                              # RAG提示词截图
├── feedback_model.md                           # 反馈/裁判模型提示词
├── Feedback_model.png                          # 反馈模型提示词截图
├── image_reading_model.md                      # 图像读取模型提示词
└── image_reading_prompt.png                    # 图像读取提示词截图
```

## Prompt Categories | 提示词类别

### 1. Baseline Problem Solving Model | 基线解题模型

**File**: `problem_solving_model_without_RAG.md`, `baseline_prompt.png`

The baseline prompt for the core problem-solving model without RAG enhancement. This prompt guides the model to:
- 无RAG增强的核心解题模型的基线提示词。该提示词指导模型：
- Process problem text, images, and type classification
- 处理问题文本、图像和类型分类
- Extract physical information from images
- 从图像中提取物理信息
- Output answers in specified format with LaTeX formulas
- 以指定格式输出答案（包含LaTeX公式）

**Key Variables**: `{{question}}`, `{{subject}}`, `{{image_meaning}}`, `{{vision_relevance}}`, `{{level}}`, `{{sig_figs}}`

### 2. Problem Solving Model with RAG | 带RAG的解题模型

**File**: `problem_solving_model_with_RAG.md`, `RAG_prompt.png`

Enhanced prompts that integrate Retrieval-Augmented Generation (RAG) with different knowledge bases for various difficulty levels:
- 集成检索增强生成（RAG）的增强提示词，针对不同难度级别使用不同知识库：
- **High School Level** (初高中): Uses `{{high_school}}` and `{{high_school_image}}` knowledge bases
- **竞赛级别**: Uses `{{olimpyic}}` and `{{olimpyic_image}}` knowledge bases
- **Undergraduate Level** (本科): Uses `{{UG}}` and `{{UG_image}}` knowledge bases
- **Advanced Level** (硕士/博士): Uses `{{advanced}}` and `{{advanced_image}}` knowledge bases

Each level-specific prompt adapts the solving strategy and knowledge retrieval to match the complexity of the problems.
每个级别特定的提示词会调整求解策略和知识检索，以匹配问题的复杂度。

### 3. Image Reading Model | 图像读取模型

**File**: `image_reading_model.md`, `image_reading_prompt.png`

Prompt for the multimodal model that analyzes physics problem images. This model:
- 用于分析物理问题图像的多模态模型提示词。该模型：
- Identifies physics topics and diagram types (circuit diagrams, free-body diagrams, etc.)
- 识别物理主题和图表类型（电路图、受力图等）
- Extracts physical scenarios, elements, and relationships
- 提取物理场景、元素和关系
- Connects image content to physical laws and principles
- 将图像内容与物理定律和原理关联

**Key Variables**: `{{subject}}`, `{{image}}`, `{{img_category}}`, `{{vision_relevance}}`, `{{caption}}`

### 4. Feedback/Verification Model | 反馈/验证模型

**File**: `feedback_model.md`, `Feedback_model.png`

Prompt for the verification model that validates solutions. This model:
- 用于验证解答的验证模型提示词。该模型：
- Checks solutions for logical errors, calculation mistakes, and conceptual mistakes
- 检查解答中的逻辑错误、计算错误和概念错误
- Returns "TRUE" for correct solutions or "FALSE" with detailed error explanations
- 对于正确解答返回"TRUE"，对于错误解答返回"FALSE"及详细错误说明
- Enables self-correcting feedback loops
- 支持自我纠正反馈循环

**Key Variables**: `{{question}}`, `{{meaning_combine}}`, `{{String1}}`

## Usage | 使用方法

These prompts are configured in the Coze workflow nodes. To modify the prompts:

这些提示词配置在Coze工作流节点中。要修改提示词：

1. **Edit the Markdown files** for text-based prompts
   - **编辑Markdown文件**以修改基于文本的提示词
2. **Update the workflow nodes** in Coze platform with the modified prompts
   - **在Coze平台更新工作流节点**中的提示词
3. **For visual prompts**, refer to the PNG screenshots for the exact configuration
   - **对于可视化提示词**，请参考PNG截图了解确切配置

## Prompt Design Principles | 提示词设计原则

1. **Structured Input**: Clear variable usage for different information sources
   - **结构化输入**: 清晰使用变量获取不同信息源
2. **Level Adaptation**: Different prompts for different difficulty levels
   - **难度适配**: 针对不同难度级别使用不同提示词
3. **Format Consistency**: Standardized output format (`<answer>...</answer>` with LaTeX)
   - **格式一致性**: 标准化输出格式（使用LaTeX的`<answer>...</answer>`标签）
4. **Context Integration**: Seamless combination of text, images, and knowledge bases
   - **上下文整合**: 无缝整合文本、图像和知识库

## Related Documentation | 相关文档

- [Workflow Documentation](../workflows/README.md) - Coze workflow overview
- [Workflow Documentation](../workflows/README.md) - Coze工作流概览
- [Main README](../README.md) - Project overview and methodology
- [Main README](../README.md) - 项目概览和方法论
