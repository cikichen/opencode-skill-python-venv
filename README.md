# OpenCode Skill: Python Virtual Environment

Enforce virtual environment usage before any Python operation to avoid polluting the system Python environment.

[中文说明](#中文说明)

## Features

- ✅ Require virtual environment activation before any Python operation
- ✅ Reuse existing `.venv` directory if present
- ✅ Auto-create if not exists
- ✅ Support `uv` (recommended, faster) and standard `venv`

## Installation

```bash
cd ~/.config/opencode/skills
git clone https://github.com/cikichen/opencode-skill-python-venv.git python-venv
```

## Trigger Conditions

This skill is automatically triggered when:

- Running `.py` files
- Using `pip install` or `uv pip install`
- Executing `python -c` commands
- Any task requiring Python packages

## Core Rule

```
1. Check if .venv exists → If YES, activate and reuse
2. If NOT exists → Create new virtual environment
3. Activate, then run Python commands
```

## Quick Reference

```bash
# Standard pattern: reuse or create
[ -d .venv ] && source .venv/bin/activate || (uv venv && source .venv/bin/activate)

# Install dependencies
uv pip install -r requirements.txt

# Run script
python script.py
```

---

## 中文说明

强制在任何 Python 操作前使用虚拟环境，避免污染系统 Python 环境。

### 功能

- ✅ 任何 Python 操作前必须激活虚拟环境
- ✅ 优先复用现有 `.venv` 目录
- ✅ 不存在时自动创建
- ✅ 支持 `uv`（推荐，更快）和标准 `venv`

### 安装

```bash
cd ~/.config/opencode/skills
git clone https://github.com/cikichen/opencode-skill-python-venv.git python-venv
```

### 触发条件

当你执行以下操作时，此 Skill 会自动触发：

- 运行 `.py` 文件
- 使用 `pip install` 或 `uv pip install`
- 执行 `python -c` 命令
- 任何需要 Python 包的任务

### 核心规则

```
1. 检查 .venv 是否存在 → 存在则直接激活复用
2. 不存在 → 创建新的虚拟环境
3. 激活后再执行 Python 命令
```

## License

MIT
