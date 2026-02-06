# OpenCode Skill: Python Virtual Environment

强制在任何 Python 操作前使用虚拟环境，避免污染系统 Python 环境。

## 功能

- ✅ 任何 Python 操作前必须激活虚拟环境
- ✅ 优先复用现有 `.venv` 目录
- ✅ 不存在时自动创建
- ✅ 支持 `uv`（推荐，更快）和标准 `venv`

## 安装

```bash
cd ~/.config/opencode/skills
git clone https://github.com/cikichen/opencode-skill-python-venv.git python-venv
```

## 触发条件

当你执行以下操作时，此 Skill 会自动触发：

- 运行 `.py` 文件
- 使用 `pip install` 或 `uv pip install`
- 执行 `python -c` 命令
- 任何需要 Python 包的任务

## 核心规则

```
1. 检查 .venv 是否存在 → 存在则直接激活复用
2. 不存在 → 创建新的虚拟环境
3. 激活后再执行 Python 命令
```

## 快速参考

```bash
# 标准模式：复用或创建
[ -d .venv ] && source .venv/bin/activate || (uv venv && source .venv/bin/activate)

# 安装依赖
uv pip install -r requirements.txt

# 运行脚本
python script.py
```

## License

MIT
