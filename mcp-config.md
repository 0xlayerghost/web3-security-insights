# MCP 配置汇总

## 前置条件

- 安装 [Node.js](https://nodejs.org)（npx 依赖）
- 安装 [Python](https://python.org)（slither 依赖，可选）

---

## Claude Code 配置

文件路径：`~/.claude/mcp.json`

### Windows

```json
{
  "mcpServers": {
    "fetch": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@tokenizin/mcp-npx-fetch"]
    },
    "playwright": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@playwright/mcp"]
    },
    "sequential-thinking": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "OpenZeppelinContracts": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@openzeppelin/contracts-mcp"]
    }
  }
}
```

### Mac / Linux

```json
{
  "mcpServers": {
    "fetch": {
      "command": "npx",
      "args": ["-y", "@tokenizin/mcp-npx-fetch"]
    },
    "playwright": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp"]
    },
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "OpenZeppelinContracts": {
      "command": "npx",
      "args": ["-y", "@openzeppelin/contracts-mcp"]
    }
  }
}
```

---

## Cherry Studio 配置

每次只能导入一个，逐个粘贴到「从 JSON 导入」输入框。

### fetch（网页内容抓取）

```json
{
  "mcpServers": {
    "fetch": {
      "command": "npx",
      "args": ["-y", "@tokenizin/mcp-npx-fetch"]
    }
  }
}
```

### playwright（浏览器自动化）

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp"]
    }
  }
}
```

### sequential-thinking（链式推理）

```json
{
  "mcpServers": {
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    }
  }
}
```

### OpenZeppelinContracts（智能合约查询）

```json
{
  "mcpServers": {
    "OpenZeppelinContracts": {
      "command": "npx",
      "args": ["-y", "@openzeppelin/contracts-mcp"]
    }
  }
}
```

---

## 推荐补充：搜索类 MCP

### Tavily（推荐，专为 AI 设计）

注册地址：https://tavily.com，免费 1000 次/月

```json
{
  "mcpServers": {
    "tavily": {
      "command": "npx",
      "args": ["-y", "tavily-mcp"],
      "env": {
        "TAVILY_API_KEY": "tvly-xxxxxxxxxxxxxxxx"
      }
    }
  }
}
```

### Brave Search（免费 2000 次/月）

申请地址：https://brave.com/search/api/

```json
{
  "mcpServers": {
    "brave-search": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "BSAxxxxxxxxxxxxxxxxxxx"
      }
    }
  }
}
```

### DuckDuckGo（无需 API Key）

```json
{
  "mcpServers": {
    "duckduckgo": {
      "command": "npx",
      "args": ["-y", "duckduckgo-mcp-server"]
    }
  }
}
```

---

## MCP 说明

| 名称 | 功能 |
|------|------|
| fetch | 抓取指定 URL 网页内容 |
| playwright | 浏览器自动化，可截图、点击、填表 |
| sequential-thinking | 结构化链式推理，复杂问题分步思考 |
| OpenZeppelinContracts | 查询 OZ 合约库文档与源码 |
| tavily | 主动网络搜索（AI 友好） |
| brave-search | Brave 搜索引擎接口 |
| duckduckgo | DuckDuckGo 搜索，无需注册 |
