# RAGShield Rules

[中文文档](README_CN.md)

Security detection rules library for RAG systems, including injection detection, jailbreak detection, privacy detection, and sensitive content detection.

## Rule Categories

| Category | Directory | Rules | Description |
|----------|-----------|-------|-------------|
| Injection | `injection/` | ~200 patterns | Prompt Injection, Context Overflow, Indirect Injection |
| Jailbreak | `jailbreak/` | ~100 patterns | DAN, Role-play Bypass, Character Smuggling |
| Privacy | `privacy/` | 14 regex | API Key, Token, Phone, ID Card, etc. |
| Sensitive | `sensitive/` | ~50 patterns | Business Secrets, Discrimination, Violence, Pornography |

## Rule Format

```json
{
  "rule_id": "RULE-001",
  "rule_name": "Prompt Injection",
  "category": "injection",
  "level": "high",
  "pattern": "ignore previous instructions",
  "description": "Attempt to override system instructions",
  "suggestion": "Add input filtering",
  "tags": ["owasp-llm-01"]
}
```

## Usage

### Option 1: Git Submodule

```bash
git submodule add https://github.com/JasonD2019/ragshield-rules.git rules
```

### Option 2: Direct Download

```bash
# Clone the repository
git clone https://github.com/JasonD2019/ragshield-rules.git

# Copy to your project
cp -r ragshield-rules/rules/* your-project/rules/
```

### Option 3: pip Install (Planned)

```bash
pip install ragshield-rules
```

## Project Integration

| Project | Integration Method |
|---------|---------------------|
| [rag-scanner](https://github.com/JasonD2019/rag-scanner) | Git Submodule |
| [raguard-sdk](https://github.com/JasonD2019/raguard-sdk) | Built-in Package |

## Contributing

Welcome to submit new rules or improve existing ones:

1. Fork this repository
2. Add rule files in the corresponding directory
3. Submit a Pull Request

## License

MIT License - Free to use, modify, and distribute