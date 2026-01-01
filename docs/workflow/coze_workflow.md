# Coze Workflow Detailed Documentation | Coze工作流详细文档

This document provides detailed information about the Coze workflow implementation.

本文档提供Coze工作流实现的详细信息。

## Workflow Architecture | 工作流架构

```markdown
![Workflow Architecture](all_1.pn)
```

*Figure: Complete Workflow Architecture*

*图: 完整工作流架构*

## Workflow Components | 工作流组件

### 1. Input Stage | 输入阶段

**Function**: Receives and processes multimodal input
**功能**: 接收和处理多模态输入

**Input Types**:
- Text descriptions of physics problems
- Diagrams and illustrations
- Mathematical expressions

**输入类型**:

- 图表和插图(image.url)


### 2. Language Translation Node | 语言翻译节点

**Function**: Translates Chinese input to English for standardization
**功能**: 将中文输入翻译为英文以标准化

**Configuration**:
- Translation model: [Specify model]
- Target language: English
- Preserve technical terms: Yes

**配置**:
- 翻译模型: [DeepSeek-V3-0324]
- 目标语言: 英文
- 保留专业术语: 是

### 3. RAG Node | 检索增强生成节点

**Function**: Retrieves relevant knowledge from knowledge bases
**功能**: 从知识库中检索相关知识

**Knowledge Bases**:
1. **Textbook Knowledge Base**
   - Contains foundational physics textbook content
   - 包含基础物理课本内容

2. **Solved Problems Database**
   - Contains 1,800 solved problems with detailed solutions
   - 包含1800个比赛官方提供的问题及其详细解答

**Retrieval Strategy**:
- Search Strategy: Mixed (混合)
- Max Recall: Default (平台自动优化，范围1-20)
- Min Match: Default (平台自动优化，范围0.01-0.99)
- Query Rewriting: Enabled (查询改写)
- Result Reranking: Enabled (结果重排)
- Table SQL Query: Enabled (表格SQL查询)

**检索策略**:
- 搜索策略: 混合模式
- 最大召回数量: 默认值（平台自动优化，范围1-20）
- 最小匹配度: 默认值（平台自动优化，范围0.01-0.99）
- 查询改写: 已启用（优化查询语句以更准确捕捉用户意图）
- 结果重排: 已启用（根据相关性或质量对检索结果重新排序）
- 表格SQL查询: 已启用（同步将自然语言查询转为SQL语句）

### 4. Core Reasoning Model | 核心推理模型

**Function**: Performs reasoning and problem-solving
**功能**: 执行推理和问题求解

**Model Configuration**:
- Primary model: Model_Deepseek-r1
- Temperature: [Specify]
- Max tokens: [Specify]

**模型配置**:
- 主要模型: Model_Deepseek-r1
- 温度参数: [0]
- 最大token数: [2200]

### 5. Feedback Loop | 反馈循环

**Function**: Self-correction and validation
**功能**: 自我纠正和验证

**Feedback Mechanism**:
- Solution validation
- Error detection
- Iterative refinement

**反馈机制**:
- 解答验证
- 错误检测
- 迭代优化

### 6. Output Stage | 输出阶段

**Function**: Generates final solution
**功能**: 生成最终解答

**Output Format**:
- Structured solution
- Step-by-step reasoning
- Final answer

**输出格式**:
- 结构化解答
- 逐步推理过程
- 最终答案

## Data Flow | 数据流

```
Input → Translation → RAG Retrieval → Reasoning → Feedback → Output
输入 → 翻译 → RAG检索 → 推理 → 反馈 → 输出
```

## Configuration Parameters | 配置参数

### Model Parameters | 模型参数

| Parameter | Value | Description |
|-----------|-------|-------------|
| Model | Model_Deepseek-r1 | Core reasoning model |
| Temperature | [0] | Sampling temperature |
| Max Tokens | [2200] | Maximum output length |

### RAG Parameters | RAG参数

| Parameter | Value | Description |
|-----------|-------|-------------|
| 搜索策略 (Search Strategy) | 混合 (Mixed) | Mixed search strategy for retrieval |
| 最大召回数量 (Max Recall) | 默认 (Default) | Maximum number of retrieved documents (Range: 1-20) |
| 最小匹配度 (Min Match) | 默认 (Default) | Minimum similarity score threshold (Range: 0.01-0.99) |
| 表格 SQL 查询 (Table SQL Query) | 启用 (Enabled) | Synchronously convert natural language to SQL queries |
| 查询改写 (Query Rewriting) | 启用 (Enabled) | Optimize and refactor query statements to capture user intent |
| 结果重排 (Result Reranking) | 启用 (Enabled) | Rerank retrieved documents based on relevance/quality |
| 仅查看个人文档 | 启用 (Enabled) | Only search user-uploaded and developer-preset documents |
| Knowledge Base 1 | Textbook | Physics textbook content |
| Knowledge Base 2 | Solved Problems | 1800 solved problems |

**Note**: The RAG node uses Coze platform's default configuration with all optimization features enabled (query rewriting, reranking, SQL query). The max recall and min match parameters use default values, which are automatically optimized by the platform.

**注意**: RAG节点使用Coze平台的默认配置，所有优化功能均已启用（查询改写、结果重排、SQL查询）。最大召回数量和最小匹配度使用默认值，由平台自动优化。

## Performance Optimization | 性能优化

### Strategies Used | 使用的策略

1. **Caching**: Frequently accessed knowledge is cached
   - **缓存**: 频繁访问的知识被缓存

2. **Parallel Processing**: Multiple components run in parallel where possible
   - **并行处理**: 尽可能并行运行多个组件

3. **Early Stopping**: Feedback loop can terminate early if solution is validated
   - **早停**: 如果解答已验证，反馈循环可以提前终止

## Limitations | 局限性

1. **Coze Platform Dependency**: Workflow is tied to Coze platform
   - **Coze平台依赖**: 工作流依赖于Coze平台

2. **Knowledge Base Access**: Requires access to Coze knowledge bases
   - **知识库访问**: 需要访问Coze知识库

3. **Model Availability**: Depends on model availability in Coze
   - **模型可用性**: 依赖于Coze中的模型可用性

## Future Improvements | 未来改进

- [ ] Support for more input formats
- [ ] 支持更多输入格式
- [ ] Enhanced feedback mechanism
- [ ] 增强反馈机制
- [ ] Expanded knowledge bases
- [ ] 扩展知识库
- [ ] Performance monitoring
- [ ] 性能监控

---

For node-level details, see [node_descriptions.md](./node_descriptions.md).

节点级别详细信息，请参见 [node_descriptions.md](./node_descriptions.md)。


