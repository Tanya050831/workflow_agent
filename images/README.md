# Images Directory | 图片目录

This directory contains images used in the README.md file.

此目录包含README.md文件中使用的图片。

## Image Files | 图片文件

### Documentation Images | 文档图片

- `methodology.png` - Problem-Solving Methodology Architecture
- `results_table.png` - Performance Comparison Results Table
- `analysis_sankey.png` - Performance Analysis Sankey Diagram
- `icml_challenge.png` - ICML 2025 SeePhys Challenge Slide

### Workflow Diagrams | 工作流图表

For detailed workflow diagrams and descriptions, see **[workflows.md](workflows.md)**.

详细的工作流图表和说明，请参见 **[workflows.md](workflows.md)**。

- `baseline_workflow.png` - Baseline workflow (all experimental variables baseline)
- `model_only_multimodal_workflow.png` - Model_Only_MultiModal configuration
- `model_deepseek_r1_workflow.png` - Model_Deepseek-r1 configuration
- `language_translation_workflow.png` - Chinese to English translation configuration
- `rag_without_1800_workflow.png` - RAG without 1800 problems configuration
- `rag_with_1800_workflow.png` - RAG with 1800 problems configuration
- `feedback_workflow.png` - Feedback loop configuration
- `integrated_method_workflow.png` - Integrated method (all components combined)

## Usage | 使用方法

To add images to README.md, use the following format:

在README.md中添加图片，请使用以下格式：

```markdown
![Image Description](images/filename.png)
```

Or with HTML for size control:

或使用HTML控制大小：

```html
<img src="images/filename.png" alt="Image Description" width="500">
```

## Tips | 提示

1. **Supported formats**: PNG, JPG, JPEG, GIF, SVG
   - **支持的格式**: PNG, JPG, JPEG, GIF, SVG

2. **File naming**: Use lowercase with underscores (e.g., `methodology_diagram.png`)
   - **文件命名**: 使用小写字母和下划线（例如：`methodology_diagram.png`）

3. **GitHub**: Images will be automatically displayed when the repository is viewed on GitHub
   - **GitHub**: 在GitHub上查看仓库时，图片会自动显示

4. **Relative paths**: Always use relative paths from the repository root
   - **相对路径**: 始终使用从仓库根目录的相对路径
