# Python 项目示例

本示例展示如何在 Python 项目中配置和使用 Claude Code 中文开发套件。

## 🎯 项目结构

这是一个典型的 Python Web API 项目结构：

```
python-project/
├── CLAUDE.md                    # Python 项目 AI 上下文
├── src/
│   ├── __init__.py
│   ├── main.py                  # FastAPI 应用入口
│   ├── core/                    # 核心业务逻辑
│   │   ├── __init__.py
│   │   ├── config.py            # 配置管理
│   │   └── database.py          # 数据库连接
│   ├── api/                     # API 路由
│   │   ├── __init__.py
│   │   └── routes/
│   │       ├── __init__.py
│   │       ├── users.py         # 用户相关接口
│   │       └── health.py        # 健康检查
│   └── models/                  # 数据模型
│       ├── __init__.py
│       └── user.py              # 用户模型
├── tests/                       # 测试文件
├── requirements.txt             # 依赖列表
├── .env.example                 # 环境变量示例
└── docs/                        # 项目文档
    └── ai-context/
        └── project-structure.md # 项目结构说明
```

## ⚙️ 技术栈

- **Python 3.11+** with **Poetry** - 依赖管理和打包
- **FastAPI 0.104+** - 现代异步Web框架，支持类型提示
- **Pydantic v2** - 数据验证和序列化
- **SQLAlchemy 2.0** - 现代Python ORM
- **Uvicorn** - ASGI服务器
- **Pytest** - 测试框架

## 🚀 快速开始

### 1. 复制项目模板
```bash
cp -r examples/python-project my-api-project
cd my-api-project
```

### 2. 安装依赖
```bash
pip install -r requirements.txt
# 或使用Poetry
poetry install
```

### 3. 配置环境
```bash
cp .env.example .env
# 编辑 .env 文件设置数据库等配置
```

### 4. 启动开发
```bash
claude
# 现在可以使用中文化的Claude Code功能开发
```

## 💡 AI开发最佳实践

### Python特有的AI指令

在 `CLAUDE.md` 中已配置：

- **类型提示强制要求** - 所有函数必须有类型提示
- **Pydantic模型优先** - 数据结构使用Pydantic定义
- **异步编程模式** - FastAPI路由使用async/await
- **错误处理标准** - 使用HTTPException和自定义异常

### 常用开发工作流

1. **创建新API端点**：
   ```bash
   # 使用Claude创建新的API路由
   /create-docs api/routes/products.py
   ```

2. **生成数据模型**：
   ```bash
   # 基于业务需求生成Pydantic模型
   /refactor models/product.py
   ```

3. **代码审查**：
   ```bash
   # AI辅助代码审查
   /code-review src/api/routes/
   ```

## 📚 项目特定命令

### 数据库迁移
```bash
# 生成数据库迁移脚本
alembic revision --autogenerate -m "Add product model"
alembic upgrade head
```

### 测试执行
```bash
# 运行测试套件
pytest tests/ -v
# 生成覆盖率报告
pytest --cov=src tests/
```

### 代码质量检查
```bash
# 代码格式化
black src/ tests/
# 导入排序
isort src/ tests/
# 类型检查
mypy src/
```

## 🔧 开发环境配置

### VSCode 配置
项目包含 `.vscode/settings.json` 配置：
- Python解释器设置
- 自动格式化配置
- 调试配置

### Pre-commit Hook
配置代码提交前检查：
```bash
pre-commit install
```

## 🎯 项目定制

### 修改AI上下文
编辑 `CLAUDE.md` 文件，添加项目特定指令：
```markdown
### 项目特定规则
- API响应必须包含request_id字段
- 所有时间字段使用UTC时区
- 密码字段使用bcrypt加密
```

### 更新项目结构文档
编辑 `docs/ai-context/project-structure.md`，描述你的具体技术选型。

---

*这个示例为Python开发者提供了完整的Claude Code中文开发套件配置，帮助快速构建高质量的Python Web应用。*