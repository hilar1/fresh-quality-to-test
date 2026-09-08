# 校园鲜达质量改进项目基线设计

## 目标

从往届 DailyFresh 商城中提取必要的被测系统源码，建立一个全新的三人课程项目仓库。原商城代码只作为被测基线；需求分析、人工测试设计、自动化测试实现、缺陷发现、修复验证、AI 实践和汇报材料由本组重新完成。

`E:\project\soft_test` 是只读参考源。不得修改、删除、重命名或格式化其中任何文件；所有新文件与后续变更只写入 `E:\project\softtest project`。

## 新仓库

- 暂定名称：`campus-fresh-quality-lab`
- 默认可见性：私有
- 项目名称：校园鲜达
- 定位：校园生鲜自提系统的测试与质量改进
- 基线标签：`baseline-v0.1`

## 基线保留内容

- `apps/` 中的业务实现、模型、路由和迁移
- `daily_fresh_demo/` 中的 Django 项目配置
- `templates/` 页面模板
- `static/` 前端静态资源
- 必要的示例图片资源
- `manage.py`

## 基线排除内容

- 四个模块中往届编写的 `tests.py`
- 往届需求、用例、缺陷、报告、PPT 和视频
- `.venv/`、`.idea/`、缓存文件和临时 Office 文件
- `db.sqlite3` 及其中可能包含的历史数据
- 旧的运行说明和互相矛盾的依赖锁定
- 将 JavaScript、CSS 和 HTML 错标为 Python 的 `.gitattributes`

## 初始仓库结构

```text
campus-fresh-quality-lab/
  apps/
  daily_fresh_demo/
  docs/
    provenance/
    requirements/
    defects/
    reports/
    ai-records/
  static/
  templates/
  manage.py
  requirements.txt
  README.md
  NOTICE.md
  .gitignore
```

`NOTICE.md` 记录原始项目地址及本组改造边界。`README.md` 只说明当前可验证的环境、目录和运行命令，不复用往届报告文字。

## 三人所有权

- 成员 A：用户、登录和地址；兼顾环境与 README
- 成员 B：商品、搜索和浏览历史；兼顾测试数据与度量
- 成员 C：购物车、订单和库存；兼顾集成执行入口与演示

每名成员都要在自己的业务域完成需求、人工用例、自动化实现、至少一个缺陷闭环和对应文档，并用个人 GitHub 账号提交。贡献比例由最终提交和交付物事实计算。

## 演进方式

1. 创建只含设计说明的新 Git 仓库。
2. 导入清理后的商城源码，形成独立的基线提交。
3. 建立可复现环境并完成兼容性迁移。
4. 三名成员分别提交需求分析和后续测试工作。
5. 在 `baseline-v0.1` 上开展人工测试，保留失败证据。
6. 缺陷修复后执行回归并形成 `module1-final`。
7. 模块二从 `module1-final` 开始开展 AI 辅助测试对照实验。

## 完成标准

- 新仓库不包含往届测试成果和个人数据。
- 全新环境可按 README 一键安装和启动。
- Git 历史能追溯三个人的真实工作。
- 测试用例、测试代码和缺陷报告相互对应。
- 模块一不使用 AI 生成测试用例或自动化测试。
