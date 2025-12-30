# Dataset Overview | 数据集概览

This document provides an overview of the physics problem dataset used in this project.

本文档提供本项目使用的物理问题数据集概览。

## Dataset Statistics | 数据集统计

- **Total Problems**: 2,000
- **总问题数**: 2,000

- **Languages**: Chinese and English
- **语言**: 中文和英文

- **Categories**: 8 distinct categories
- **类别**: 8个不同类别

- **Difficulty Levels**: 7 levels (from middle school to doctoral studies)
- **难度级别**: 7个级别（从中学到博士研究）

## Categories | 类别

| Category Code | Full Name | Description |
|--------------|-----------|-------------|
| CM | Classical Mechanics | 经典力学 |
| OPT | Optics | 光学 |
| ACG | [TBD] | [待补充] |
| EM | Electromagnetism | 电磁学 |
| QMIT | Quantum Mechanics | 量子力学 |
| AMONP | [TBD] | [待补充] |
| TSM | [TBD] | [待补充] |

## Difficulty Levels | 难度级别

1. **Middle School** | 中学
2. **High School** | 高中
3. **Undergraduate** | 本科
4. **Graduate** | 研究生
5. **Doctoral** | 博士

## Data Format | 数据格式

### Problem Structure | 问题结构

```json
{
  "problem_id": "string",
  "language": "chinese" | "english",
  "category": "CM" | "OPT" | "ACG" | "EM" | "QMIT" | "AMONP" | "TSM",
  "difficulty": 1-7,
  "text": "string",
  "diagram": "base64_encoded_image" | "image_url",
  "solution": {
    "steps": ["string"],
    "final_answer": "string"
  }
}
```

## Dataset Splits | 数据集划分

- **Development Set**: 200 problems
  - **开发集**: 200个问题
- **Test Set**: 1,800 problems
  - **测试集**: 1,800个问题

## Access | 访问

The dataset is stored in the Coze knowledge base. For access:

数据集存储在Coze知识库中。访问方式：

- See [../../resources/links.md](../../resources/links.md) for access links
- 参见 [../../resources/links.md](../../resources/links.md) 获取访问链接

## Sample Problems | 示例问题

Sample problems are available in the [sample_problems/](./sample_problems/) directory.

示例问题可在 [sample_problems/](./sample_problems/) 目录中查看。

---

For data format details, see [data_format.md](./data_format.md).

数据格式详细信息，请参见 [data_format.md](./data_format.md)。

