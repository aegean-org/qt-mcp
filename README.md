# 青提MCP使用指南

## 项目简介

青提MCP，旨在通过模型上下文协议（Model Context Protocol，MCP）将青提学术数据库与不同 AI 助手衔接，支持自然语言驱动的专业学术查询。

## 功能特性

- **论文搜索**: 支持按标题、作者搜索学术论文，提供分页功能
- **PDF文本提取**: 从PDF文件中提取文本内容
- **文件夹管理**: 支持从特定文件夹检索论文
- **笔记保存**: Markdown格式笔记管理系统

## 系统要求
- 需安装[青提学术](https://www.inoteexpress.com/aegean/index.php/home/qt/index.html)，推荐 v2.5.0 及以上版本
- 适用于Linux、macOS、Windows系统

## 快速上手指南

### 下载程序解压安装

前往项目的 [Releases 页面](https://github.com/aegean-org/qt-mcp/releases) 下载最新的二进制包，例如：
- **Windows**: 下载 `qt-mcp-windows-amd64.7z`
- **macOS M芯片**: 下载 `qt-mcp-darwin-arm64.7z`
- **macOS Intel芯片**: 下载 `qt-mcp-darwin-amd64.7z`
- **Linux**: 下载 `qt-mcp-linux-amd64.7z`

将下载的压缩包解压到您选择的目录。

### MCP客户端配置

在支持的AI客户端MCP中添加以下配置：

```json
{
  "mcpServers": {
    "青提mcp": {
      "name": "青提学术",
      "type": "stdio",
      "description": "学术论文管理和研究辅助工具",
      "command": "/你的电脑目录/qt-mcp.exe", // 替换为实际路径
      "args": []
    }
  }
}
```

#### 使用示例:
-   `"帮我查找一下我的青提学术里所有关于"人工智能"的文献"`
-   `"获取青提学术“计算机”目录里的文献"`

|功能点|示意图|
| ------------ | ------------ |
|功能说明|<img width="1280" height="810" alt="image" src="https://github.com/user-attachments/assets/72964469-903b-4014-990f-5d692ebbb8de" />|
|文献检索|<img width="1280" height="810" alt="image" src="https://github.com/user-attachments/assets/2267a690-e3b7-4f0b-bfe0-a7e59cb4fa27" />|
|元数据查看|<img width="1280" height="810" alt="image" src="https://github.com/user-attachments/assets/54802719-fa4b-40ec-9062-e5ec44df0597" />|
|全文读取|<img width="1280" height="810" alt="image" src="https://github.com/user-attachments/assets/b6111983-32dd-47c5-b513-44c8f1a56e98" />|
|基于全文信息进一步提问|<img width="1280" height="810" alt="image" src="https://github.com/user-attachments/assets/9f84e2dd-f2bc-4dfc-b790-8313422c1300" />|
|创建笔记|<img width="1280" height="810" alt="image" src="https://github.com/user-attachments/assets/22f714f8-9dd7-4ee7-b1b3-151e0c8d1e1d" /><img width="1280" height="888" alt="image" src="https://github.com/user-attachments/assets/7f1065d4-1e9b-421b-ba71-8c192d309dd7" />|
|创建文献|<img width="1280" height="810" alt="image" src="https://github.com/user-attachments/assets/828d85e0-9a51-4113-b890-cf2ccde44bd2" /><img width="1280" height="898" alt="image" src="https://github.com/user-attachments/assets/5fd41b21-9cd8-4d14-af33-89baea547eb1" />|


#### 可用工具

青提MCP提供以下5个核心工具：

### 1. noteExpressWeb_search_articles
- **功能**: 按标题或作者搜索文献
- **参数**: 
  - `query`: 搜索关键词
  - `page`: 页码（可选）
  - `pageSize`: 每页数量（可选）

### 2. noteExpressWeb_get_article_pdf_content
- **功能**: 通过文献id/标题获取正文内容
- **参数**: 
  - `article_id`: 文献id

### 3. noteExpressWeb_search_articles_by_folder
- **功能**: 获取指定文件夹中的论文
- **参数**: 
  - `folder`: 文件夹名

### 4. noteExpressWeb_save_articles
- **功能**: 将对应的文献信息保存到青提学术
- **参数**:
  - `data`: 保存的内容 json格式

### 5. noteExpressWeb_save_note
- **功能**: 保存Markdown格式的研究笔记到对应文献
- **参数**: 
  - `content`: 笔记内容
  - `article id`: 文献Id
  - `note_id`: 笔记id（可选）

### 支持的 AI 客户端

使用 Stdio 协议，支持与 AI 客户端的实时通信

- **Claude Desktop**: Stdio MCP 支持
- **Cherry Studio**: Stdio MCP 支持
- **Cursor IDE**: Stdio MCP 支持

## 故障排除

### 常见问题

1. **程序无法启动**: 确保下载了正确平台的版本
2. **文件下载失败**: 检查网络连接和数据目录权限
3. **配置文件未找到**: 确认数据目录路径设置正确

### 获取帮助

如有问题或建议，请通过项目的GitHub Issues页面联系我们。
