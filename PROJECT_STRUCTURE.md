# 项目结构建议 | Project Structure Recommendations

## 推荐的GitHub仓库结构 | Recommended GitHub Repository Structure

```
your-repo/
├── README.md                    # 主README（已有）
├── images/                      # 图片资源（已有）
│   ├── methodology.png
│   ├── results_table.png
│   ├── analysis_sankey.png
│   └── ...
├── docs/                        # 📚 文档目录（建议新增）
│   ├── workflow/                # 工作流文档
│   │   ├── coze_workflow.md     # Coze工作流详细说明
│   │   ├── workflow_diagram.png # 工作流架构图
│   │   └── node_descriptions.md # 节点功能说明
│   ├── dataset/                 # 数据集文档
│   │   ├── dataset_overview.md  # 数据集概览
│   │   ├── data_format.md       # 数据格式说明
│   │   └── sample_problems/     # 示例问题
│   │       ├── sample_1.md
│   │       └── sample_2.md
│   └── feishu_docs/             # 飞书文档转换
│       └── (转换后的Markdown文件)
│
├── workflows/                   # 🔧 Coze工作流相关（建议新增）
│   ├── coze_export/             # Coze工作流导出文件
│   │   ├── workflow_config.json # 工作流配置JSON（如果可导出）
│   │   └── agent_config.json    # Agent配置
│   ├── screenshots/             # 工作流截图
│   │   ├── workflow_overview.png
│   │   ├── node_rag.png
│   │   ├── node_translation.png
│   │   └── node_feedback.png
│   └── README.md                # 工作流使用说明
│
├── scripts/                     # 🐍 辅助脚本（建议新增）
│   ├── data_processing/         # 数据处理脚本
│   │   └── export_from_coze.py  # 从Coze导出数据
│   ├── evaluation/              # 评估脚本
│   │   └── evaluate_results.py
│   └── utils/                   # 工具脚本
│       └── format_converter.py  # 格式转换工具
│
├── examples/                    # 📖 使用示例（建议新增）
│   ├── example_usage.md         # 使用示例说明
│   ├── api_examples/            # API调用示例
│   └── problem_examples/        # 问题解决示例
│
├── resources/                   # 📦 资源文件（建议新增）
│   ├── links.md                 # 外部资源链接
│   │   ├── Coze空间链接
│   │   ├── 飞书文档链接
│   │   └── 数据集链接
│   └── references/              # 参考文献
│       └── papers.md
│
└── .github/                     # GitHub配置（可选）
    └── workflows/               # GitHub Actions（如果需要CI/CD）
```

## 详细说明 | Detailed Explanations

### 1. 📚 docs/ 目录 - 文档目录

**目的**: 存放所有项目文档，便于查阅和维护

**建议内容**:
- **workflow/**: Coze工作流的详细文档
  - 工作流架构说明
  - 每个节点的功能描述
  - 数据流转过程
  - 配置参数说明
  
- **dataset/**: 数据集相关文档
  - 数据集统计信息
  - 数据格式规范
  - 示例问题展示
  - 数据来源说明

- **feishu_docs/**: 从飞书文档转换的Markdown文件
  - 保持原有结构
  - 添加目录索引

### 2. 🔧 workflows/ 目录 - Coze工作流

**目的**: 展示和说明Coze工作流的实现

**建议内容**:
- **coze_export/**: 工作流配置文件（如果Coze支持导出）
  - JSON格式的工作流配置
  - Agent配置参数
  - 节点连接关系

- **screenshots/**: 工作流可视化截图
  - 完整工作流概览
  - 关键节点特写
  - 数据流示意图

- **README.md**: 工作流使用指南
  - 如何访问Coze工作流
  - 如何配置和运行
  - 常见问题解答

### 3. 🐍 scripts/ 目录 - 辅助脚本

**目的**: 提供数据处理和工具脚本

**建议内容**:
- 数据导出脚本（从Coze导出数据）
- 格式转换工具（飞书文档转Markdown）
- 评估和分析脚本
- 数据预处理工具

### 4. 📖 examples/ 目录 - 使用示例

**目的**: 展示如何使用系统解决问题

**建议内容**:
- 典型问题解决流程
- API调用示例
- 输入输出示例
- 最佳实践

### 5. 📦 resources/ 目录 - 资源链接

**目的**: 集中管理外部资源链接

**建议内容**:
- **links.md**: 包含所有外部链接
  - Coze空间访问链接
  - 飞书文档链接
  - 数据集下载链接
  - 相关资源链接

## 关于Coze工作流的展示方式

### 方案A: 截图 + 链接（推荐）⭐
- ✅ 优点: 直观、易于理解、无需导出配置
- ✅ 实现: 截图展示工作流，README中提供Coze链接
- 📝 建议: 在 `workflows/screenshots/` 存放截图，在 `resources/links.md` 存放链接

### 方案B: 导出配置 + 说明
- ✅ 优点: 可复现、技术细节完整
- ⚠️ 限制: 需要Coze支持导出功能
- 📝 建议: 如果支持，导出JSON配置到 `workflows/coze_export/`

### 方案C: 混合方案（最佳）⭐⭐⭐
- ✅ 截图展示整体架构
- ✅ 关键节点详细说明
- ✅ 提供Coze访问链接
- ✅ 如有配置，一并提供

## 关于数据集的展示

### 建议做法:
1. **数据集说明文档** (`docs/dataset/dataset_overview.md`)
   - 数据集统计信息
   - 类别分布
   - 难度分布
   - 数据格式说明

2. **示例问题** (`docs/dataset/sample_problems/`)
   - 每个类别提供1-2个示例
   - 展示问题格式
   - 展示解答格式

3. **数据集链接** (`resources/links.md`)
   - 指向Coze空间的数据集
   - 说明如何访问
   - 如有公开版本，提供下载链接

4. **数据格式文档** (`docs/dataset/data_format.md`)
   - JSON Schema
   - 字段说明
   - 示例数据

## 关于飞书文档的迁移

### 建议步骤:
1. **导出飞书文档**
   - 使用飞书导出功能（支持Markdown格式）
   - 或手动复制转换为Markdown

2. **整理到 `docs/feishu_docs/`**
   - 保持原有文档结构
   - 添加目录索引文件

3. **更新README**
   - 在README中添加文档索引
   - 链接到具体文档

## 实施优先级

### 第一阶段（必须）:
- [ ] 创建 `docs/workflow/` 并添加工作流说明
- [ ] 创建 `workflows/screenshots/` 并添加工作流截图
- [ ] 创建 `resources/links.md` 并添加Coze和飞书链接
- [ ] 创建 `docs/dataset/` 并添加数据集说明

### 第二阶段（重要）:
- [ ] 创建 `examples/` 并添加使用示例
- [ ] 创建 `docs/feishu_docs/` 并迁移飞书文档
- [ ] 添加工作流详细节点说明

### 第三阶段（可选）:
- [ ] 创建 `scripts/` 并添加辅助脚本
- [ ] 导出Coze工作流配置（如果支持）
- [ ] 添加GitHub Actions自动化

## 下一步行动

1. **立即可以做的**:
   - 创建目录结构
   - 添加Coze工作流截图
   - 创建链接文档

2. **需要准备的内容**:
   - 工作流截图
   - Coze空间访问链接
   - 飞书文档导出

3. **我可以帮你**:
   - 创建目录结构
   - 编写文档模板
   - 更新README添加索引


