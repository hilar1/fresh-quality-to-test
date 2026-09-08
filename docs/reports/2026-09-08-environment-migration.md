# Django 5.2 环境迁移记录

## 迁移范围

从 Django 2.0.7 升级到 Django 5.2.17，使用项目内独立 `.venv`，没有修改系统 Python、Anaconda 环境或只读参考目录。

## 兼容修改

- 将 `django.conf.urls.url` 替换为 `django.urls.re_path`。
- 将已移除的 `request.is_ajax()` 替换为请求头判断。
- 将模板中的 `staticfiles` 标签库替换为 `static`。
- 修正 SQLite `OPTIONS` 配置层级。
- 移除已废弃的 `USE_L10N`，显式保留原模型主键类型。
- 更新 django-tinymce 和 TinyMCE 配置。
- 允许通过环境变量覆盖密钥、调试模式和允许主机。

## 验证证据

| 验证项 | 结果 |
|---|---|
| `python manage.py check` | 通过，0 个问题 |
| `python manage.py makemigrations --check --dry-run` | 通过，无模型变化 |
| `python manage.py migrate --noinput` | 通过，全部迁移成功 |
| `python -m pip check` | 通过，无损坏依赖 |
| `/user/login/` | HTTP 200 |
| `/admin/login/` | HTTP 200 |
| `/`（空数据库） | HTTP 500，`df_goods.views.index` 固定访问第 1～6 个分类 |

首页失败被记录为后续商品模块候选缺陷。本迁移不创建往届数据，也不提前改变该业务行为。
