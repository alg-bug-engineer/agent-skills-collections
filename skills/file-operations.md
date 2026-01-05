# 文件操作技能

文件操作技能允许 Agent 读取、写入和管理各种格式的文件。

## 📖 概述

文件操作技能使 AI Agent 能够：
- 读取各种格式的文件
- 创建和编辑文件
- 管理文件和目录
- 处理文档、图像等文件类型

## 🛠️ 主要工具和库

### 1. LangChain 文件工具

```python
from langchain_community.tools import ReadFileTool, WriteFileTool, ListDirectoryTool

# 读取文件
read_tool = ReadFileTool()

# 写入文件
write_tool = WriteFileTool()

# 列出目录
list_tool = ListDirectoryTool()

# 使用
content = read_tool.run("example.txt")
write_tool.run("output.txt", "Hello, World!")
files = list_tool.run(".")
```

### 2. PDF 处理

```python
from PyPDF2 import PdfReader, PdfWriter

def read_pdf(file_path: str) -> str:
    """读取 PDF 文件内容"""
    reader = PdfReader(file_path)
    text = ""
    for page in reader.pages:
        text += page.extract_text()
    return text

def write_pdf(file_path: str, content: str):
    """写入 PDF 文件"""
    writer = PdfWriter()
    # 添加内容到 PDF
    # ...
    with open(file_path, 'wb') as f:
        writer.write(f)
```

### 3. Word 文档处理

```python
from docx import Document

def read_docx(file_path: str) -> str:
    """读取 Word 文档内容"""
    doc = Document(file_path)
    text = []
    for paragraph in doc.paragraphs:
        text.append(paragraph.text)
    return '\n'.join(text)

def write_docx(file_path: str, content: str):
    """写入 Word 文档"""
    doc = Document()
    doc.add_paragraph(content)
    doc.save(file_path)
```

### 4. Excel 文件处理

```python
from openpyxl import Workbook, load_workbook

def read_excel(file_path: str) -> dict:
    """读取 Excel 文件"""
    wb = load_workbook(file_path)
    ws = wb.active
    data = []
    for row in ws.iter_rows(values_only=True):
        data.append(row)
    return data

def write_excel(file_path: str, data: list):
    """写入 Excel 文件"""
    wb = Workbook()
    ws = wb.active
    for row in data:
        ws.append(row)
    wb.save(file_path)
```

## 📊 应用示例

### 1. 文档分析

```python
from langchain.agents import initialize_agent, AgentType, Tool
from langchain_community.tools import ReadFileTool

read_tool = ReadFileTool()

tools = [Tool(
    name="Read File",
    func=read_tool.run,
    description="Read content from a file"
)]

agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION
)

result = agent.run("Analyze the content of report.txt")
```

### 2. 报告生成

```python
def generate_report(data: dict, output_path: str):
    """生成报告文件"""
    content = f"""
    Report Generated: {datetime.now()}
    
    Summary:
    - Total items: {data['total']}
    - Success: {data['success']}
    - Failed: {data['failed']}
    """
    
    with open(output_path, 'w') as f:
        f.write(content)
```

### 3. 文件批量处理

```python
import os
from pathlib import Path

def process_files(directory: str, extension: str):
    """批量处理文件"""
    files = Path(directory).glob(f"*.{extension}")
    
    for file in files:
        # 处理每个文件
        content = read_file(file)
        processed = process_content(content)
        write_file(file.with_suffix('.processed'), processed)
```

## 🎯 最佳实践

1. **文件路径验证**: 验证文件路径的安全性
2. **错误处理**: 妥善处理文件操作错误
3. **权限检查**: 检查文件读写权限
4. **资源清理**: 及时关闭文件句柄
5. **备份重要文件**: 在修改前备份重要文件

## 🔗 相关资源

- [LangChain 文件工具](https://python.langchain.com/docs/integrations/tools/file_system)
- [PyPDF2 文档](https://pypdf2.readthedocs.io/)
- [python-docx 文档](https://python-docx.readthedocs.io/)
- [openpyxl 文档](https://openpyxl.readthedocs.io/)

---

**更新日期**: 2026-01-04
**版本**: v0.1

