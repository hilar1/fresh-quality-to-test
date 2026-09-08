# 校园鲜达 Django 5.2 环境迁移设计

## 目标

把 `baseline-v0.1` 从 Django 2.0.7 迁移到可在当前电脑 Python 3.13 上复现的 Django 5.2 LTS 环境，并保留商城现有业务行为，为模块一人工测试提供稳定被测版本。

## 范围

- 使用 Python 3.13、Django 5.2、django-tinymce 5.0 和 Pillow 12.3。
- 替换 Django 已移除的路由、AJAX 判断和模板静态标签 API。
- 修正 SQLite `OPTIONS` 配置层级。
- 将密钥、调试开关和允许主机改为环境变量可覆盖的本地配置。
- 补充安装、迁移和启动说明。

本阶段不修复用户、商品、购物车和订单中的业务缺陷，也不生成模块一测试用例或自动化测试。

## 验收标准

- 新建虚拟环境后可从 `requirements.txt` 完成安装。
- `python manage.py check` 无错误。
- 现有迁移能应用到全新的 SQLite 数据库，且 `makemigrations --check --dry-run` 不产生模型变更。
- 开发服务器可启动，首页请求进入应用；缺少初始商品数据导致的业务页面错误单独记录，不在环境迁移中伪装修复。
