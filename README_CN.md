# RAGShield Rules

[English](README.md)

RAG 系统安全检测规则库，包含注入检测、越狱检测、隐私检测、敏感内容检测等规则。

## 规则分类

| 类别 | 目录 | 规则数量 | 说明 |
|------|------|----------|------|
| 注入检测 | `injection/` | ~200 模式 | Prompt Injection、上下文溢出、间接注入 |
| 越狱检测 | `jailbreak/` | ~100 模式 | DAN、角色扮演绕过、特殊字符走私 |
| 隐私检测 | `privacy/` | 14 正则 | API Key、Token、手机号、身份证等 |
| 敏感内容 | `sensitive/` | ~50 模式 | 商业秘密、歧视、暴力、色情等 |

## 规则格式

```json
{
  "rule_id": "RULE-001",
  "rule_name": "提示词注入",
  "category": "injection",
  "level": "high",
  "pattern": "忽略之前的指令",
  "description": "尝试覆盖系统指令",
  "suggestion": "添加输入过滤",
  "tags": ["owasp-llm-01"]
}
```

## 使用方式

### 方式 1：Git Submodule

```bash
git submodule add https://github.com/JasonD2019/ragshield-rules.git rules
```

### 方式 2：直接下载

```bash
# 下载规则库
git clone https://github.com/JasonD2019/ragshield-rules.git

# 复制到项目
cp -r ragshield-rules/rules/* your-project/rules/
```

### 方式 3：pip 安装（规划中）

```bash
pip install ragshield-rules
```

## 项目集成

| 项目 | 集成方式 |
|------|----------|
| [rag-scanner](https://github.com/JasonD2019/rag-scanner) | Git Submodule |
| [raguard-sdk](https://github.com/JasonD2019/raguard-sdk) | 内置打包 |

## 规则贡献

欢迎提交新规则或改进现有规则：

1. Fork 本仓库
2. 在对应目录添加规则文件
3. 提交 Pull Request

## License

MIT License - 可自由使用、修改、分发