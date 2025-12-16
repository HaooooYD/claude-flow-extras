# Claude Flow Extras

[English](#english) | [中文](#chinese)

---

<a name="english"></a>
## 📚 English Documentation

### About

**Claude Flow Extras** is a curated collection of extended skills for [Claude Flow](https://github.com/ruvnet/claude-flow), designed to enhance your AI-assisted development workflow. Each skill is independently maintained with its own prerequisites, installation steps, and configuration requirements.

### Repository Structure

```
claude-flow-extras/
├── academic-researcher/     # Academic paper search skill
├── [future-skill]/          # More skills coming soon
└── README.md
```

### How to Use

Each skill is self-contained in its own directory. To install a skill:

1. Navigate to the skill directory you want to use
2. Read the skill's prerequisites and configuration requirements
3. Copy the entire skill folder to your Claude Code skills directory:
   ```bash
   cp -r <skill-name> ~/.claude/skills/
   ```
4. Follow the skill-specific installation and configuration instructions below

### Available Skills

---

## 📦 Skill: academic-researcher

**Academic paper search across 14+ scholarly platforms including arXiv, PubMed, Google Scholar, Web of Science, Semantic Scholar, Sci-Hub, and more.**

### Prerequisites

- **Node.js**: 18.0.0 or higher
- **Claude Code**: Latest version with MCP support
- **Global Package**: `paper-search-mcp-nodejs` v0.2.5+

### Installation

**Step 1: Install the global npm package**
```bash
npm install -g paper-search-mcp-nodejs
```

**Step 2: Add MCP server to Claude Code**
```bash
claude mcp add paper-search npx paper-search-mcp-nodejs
```

**Step 3: Copy skill to your Claude Code directory**
```bash
cp -r academic-researcher ~/.claude/skills/
```

**Step 4: Verify installation**
```bash
# Check package version
npx paper-search-mcp-nodejs --version

# List MCP servers
claude mcp list
```

### Configuration

Create a `.env` file in your working directory for optional API keys:

```bash
# Optional: Premium platform API keys
WOS_API_KEY=your_web_of_science_key          # Web of Science
PUBMED_API_KEY=your_pubmed_key               # PubMed/NCBI
SCIENCEDIRECT_API_KEY=your_elsevier_key      # ScienceDirect
SPRINGER_API_KEY=your_springer_key           # Springer Nature
WILEY_API_KEY=your_wiley_key                 # Wiley Online Library
SCOPUS_API_KEY=your_scopus_key               # Scopus

# Optional: Sci-Hub mirror override
SCIHUB_MIRROR=https://sci-hub.se
```

**Configuration Parameters:**

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `WOS_API_KEY` | No | - | Web of Science API key for advanced search |
| `PUBMED_API_KEY` | No | - | PubMed E-utilities API key (increases rate limit) |
| `SCIENCEDIRECT_API_KEY` | No | - | Elsevier API key for full-text access |
| `SPRINGER_API_KEY` | No | - | Springer Nature API key |
| `WILEY_API_KEY` | No | - | Wiley TDM API key |
| `SCOPUS_API_KEY` | No | - | Scopus API key (same as Elsevier) |
| `SCIHUB_MIRROR` | No | Auto-detect | Override default Sci-Hub mirror |

**Note:** Open-access platforms (arXiv, Crossref, bioRxiv, medRxiv, IACR) do not require API keys.

### Usage

**Basic Usage:**
```bash
# Activate skill in Claude Code
/skill academic-researcher

# Example queries
"Search arXiv for recent quantum computing papers"
"Find PubMed articles about CRISPR published in 2024"
"Get paper recommendations based on this DOI: 10.1038/nature12373"
```

**Supported Platforms:**
- ✅ arXiv (preprints)
- ✅ PubMed/MEDLINE (biomedical)
- ✅ Google Scholar (citations)
- ✅ Semantic Scholar (citation graphs)
- ✅ Web of Science (premium)
- ✅ Scopus (premium)
- ✅ ScienceDirect (premium)
- ✅ Springer Nature
- ✅ Wiley Online Library
- ✅ Crossref (DOI metadata)
- ✅ bioRxiv (biology preprints)
- ✅ medRxiv (medical preprints)
- ✅ IACR ePrint (cryptography)
- ⚠️ Sci-Hub (PDF access, legal caution)

### MCP Dependencies

This skill requires the following MCP server:

**Primary Dependency:**
- **Package:** `paper-search-mcp-nodejs`
- **Version:** v0.2.5+
- **Repository:** [paper-search-mcp-nodejs](https://github.com/your-repo/paper-search-mcp-nodejs)
- **Installation:** `npm install -g paper-search-mcp-nodejs`
- **MCP Command:** `claude mcp add paper-search npx paper-search-mcp-nodejs`

**MCP Tools Provided (17 total):**
- `search_papers` - Universal search across all platforms
- `search_arxiv` - arXiv-specific search
- `search_pubmed` - PubMed-specific search
- `search_google_scholar` - Google Scholar search
- `search_semantic_scholar` - Semantic Scholar search
- `search_wos` - Web of Science search
- `search_sciencedirect` - ScienceDirect search
- `search_springer` - Springer Nature search
- `search_wiley` - Wiley search
- `search_scopus` - Scopus search
- `search_crossref` - Crossref search
- `search_biorxiv` - bioRxiv search
- `search_medrxiv` - medRxiv search
- `search_iacr` - IACR ePrint search
- `fetch_paper` - Retrieve paper by DOI/ID
- `fetch_scihub_pdf` - Download PDF via Sci-Hub
- `get_paper_recommendations` - Citation-based recommendations

**Legal Notice:**
⚠️ Sci-Hub functionality may violate copyright laws in many jurisdictions. Use responsibly and only for legally permitted purposes (fair use, educational, with institutional access).

---

## 🔮 Coming Soon

More skills are in development! Future additions may include:
- 🧬 **bioinformatics-tools** - Genomic data analysis
- 📊 **data-viz-generator** - Automated visualization
- 🤖 **ml-model-evaluator** - Model performance analysis
- 📝 **latex-formatter** - Academic document formatting

Stay tuned and feel free to contribute your own skills!

---

## 🤝 Contributing

We welcome contributions! To add a new skill:

1. Fork this repository
2. Create a new directory for your skill
3. Include a `SKILL.md` file following the format of existing skills
4. Ensure your skill has clear prerequisites, installation steps, and configuration
5. Submit a pull request with a description of your skill

---

## 📄 License

MIT License - See [LICENSE](LICENSE) file for details

---

<a name="chinese"></a>
## 📚 中文文档

### 关于本项目

**Claude Flow Extras** 是为 [Claude Flow](https://github.com/ruvnet/claude-flow) 精心策划的扩展技能集合，旨在增强您的 AI 辅助开发工作流。每个技能都独立维护，具有自己的前置依赖、安装步骤和配置要求。

### 仓库结构

```
claude-flow-extras/
├── academic-researcher/     # 学术论文搜索技能
├── [未来技能]/               # 更多技能即将推出
└── README.md
```

### 使用方法

每个技能都包含在独立的目录中。安装技能的步骤：

1. 导航到您想使用的技能目录
2. 阅读技能的前置依赖和配置要求
3. 将整个技能文件夹复制到您的 Claude Code 技能目录：
   ```bash
   cp -r <技能名称> ~/.claude/skills/
   ```
4. 按照下面的技能特定安装和配置说明操作

### 可用技能

---

## 📦 技能：academic-researcher

**跨 14+ 个学术平台进行论文搜索，包括 arXiv、PubMed、Google Scholar、Web of Science、Semantic Scholar、Sci-Hub 等。**

### 前置依赖

- **Node.js**: 18.0.0 或更高版本
- **Claude Code**: 支持 MCP 的最新版本
- **全局包**: `paper-search-mcp-nodejs` v0.2.5+

### 安装步骤

**步骤 1: 安装全局 npm 包**
```bash
npm install -g paper-search-mcp-nodejs
```

**步骤 2: 将 MCP 服务器添加到 Claude Code**
```bash
claude mcp add paper-search npx paper-search-mcp-nodejs
```

**步骤 3: 复制技能到您的 Claude Code 目录**
```bash
cp -r academic-researcher ~/.claude/skills/
```

**步骤 4: 验证安装**
```bash
# 检查包版本
npx paper-search-mcp-nodejs --version

# 列出 MCP 服务器
claude mcp list
```

### 配置说明

在工作目录中创建 `.env` 文件以配置可选的 API 密钥：

```bash
# 可选：高级平台 API 密钥
WOS_API_KEY=your_web_of_science_key          # Web of Science
PUBMED_API_KEY=your_pubmed_key               # PubMed/NCBI
SCIENCEDIRECT_API_KEY=your_elsevier_key      # ScienceDirect
SPRINGER_API_KEY=your_springer_key           # Springer Nature
WILEY_API_KEY=your_wiley_key                 # Wiley Online Library
SCOPUS_API_KEY=your_scopus_key               # Scopus

# 可选：Sci-Hub 镜像覆盖
SCIHUB_MIRROR=https://sci-hub.se
```

**配置参数说明：**

| 参数 | 必需 | 默认值 | 说明 |
|------|------|--------|------|
| `WOS_API_KEY` | 否 | - | Web of Science API 密钥，用于高级搜索 |
| `PUBMED_API_KEY` | 否 | - | PubMed E-utilities API 密钥（提高速率限制） |
| `SCIENCEDIRECT_API_KEY` | 否 | - | Elsevier API 密钥，用于全文访问 |
| `SPRINGER_API_KEY` | 否 | - | Springer Nature API 密钥 |
| `WILEY_API_KEY` | 否 | - | Wiley TDM API 密钥 |
| `SCOPUS_API_KEY` | 否 | - | Scopus API 密钥（与 Elsevier 相同） |
| `SCIHUB_MIRROR` | 否 | 自动检测 | 覆盖默认 Sci-Hub 镜像 |

**注意：** 开放访问平台（arXiv、Crossref、bioRxiv、medRxiv、IACR）不需要 API 密钥。

### 使用方法

**基本用法：**
```bash
# 在 Claude Code 中激活技能
/skill academic-researcher

# 示例查询
"在 arXiv 上搜索最近的量子计算论文"
"查找 2024 年发表的关于 CRISPR 的 PubMed 文章"
"根据此 DOI 获取论文推荐：10.1038/nature12373"
```

**支持的平台：**
- ✅ arXiv（预印本）
- ✅ PubMed/MEDLINE（生物医学）
- ✅ Google Scholar（引用）
- ✅ Semantic Scholar（引用图）
- ✅ Web of Science（高级）
- ✅ Scopus（高级）
- ✅ ScienceDirect（高级）
- ✅ Springer Nature
- ✅ Wiley Online Library
- ✅ Crossref（DOI 元数据）
- ✅ bioRxiv（生物学预印本）
- ✅ medRxiv（医学预印本）
- ✅ IACR ePrint（密码学）
- ⚠️ Sci-Hub（PDF 访问，法律警告）

### MCP 依赖

该技能需要以下 MCP 服务器：

**主要依赖：**
- **包名:** `paper-search-mcp-nodejs`
- **版本:** v0.2.5+
- **仓库:** [paper-search-mcp-nodejs](https://github.com/your-repo/paper-search-mcp-nodejs)
- **安装:** `npm install -g paper-search-mcp-nodejs`
- **MCP 命令:** `claude mcp add paper-search npx paper-search-mcp-nodejs`

**提供的 MCP 工具（共 17 个）：**
- `search_papers` - 跨所有平台的通用搜索
- `search_arxiv` - arXiv 专用搜索
- `search_pubmed` - PubMed 专用搜索
- `search_google_scholar` - Google Scholar 搜索
- `search_semantic_scholar` - Semantic Scholar 搜索
- `search_wos` - Web of Science 搜索
- `search_sciencedirect` - ScienceDirect 搜索
- `search_springer` - Springer Nature 搜索
- `search_wiley` - Wiley 搜索
- `search_scopus` - Scopus 搜索
- `search_crossref` - Crossref 搜索
- `search_biorxiv` - bioRxiv 搜索
- `search_medrxiv` - medRxiv 搜索
- `search_iacr` - IACR ePrint 搜索
- `fetch_paper` - 通过 DOI/ID 检索论文
- `fetch_scihub_pdf` - 通过 Sci-Hub 下载 PDF
- `get_paper_recommendations` - 基于引用的推荐

**法律声明：**
⚠️ Sci-Hub 功能在许多司法管辖区可能违反版权法。请负责任地使用，仅用于法律允许的目的（合理使用、教育、具有机构访问权限）。

---

## 🔮 即将推出

更多技能正在开发中！未来可能添加：
- 🧬 **bioinformatics-tools** - 基因组数据分析
- 📊 **data-viz-generator** - 自动化可视化
- 🤖 **ml-model-evaluator** - 模型性能分析
- 📝 **latex-formatter** - 学术文档格式化

敬请期待，欢迎贡献您自己的技能！

---

## 🤝 贡献

我们欢迎贡献！添加新技能的步骤：

1. Fork 此仓库
2. 为您的技能创建新目录
3. 按照现有技能的格式包含 `SKILL.md` 文件
4. 确保您的技能有清晰的前置依赖、安装步骤和配置说明
5. 提交包含技能描述的 pull request

---

## 📄 许可证

MIT 许可证 - 详见 [LICENSE](LICENSE) 文件
