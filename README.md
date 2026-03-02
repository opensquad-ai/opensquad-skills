# opensquad-skills

OpenSquad 技能商店仓库，包含可一键安装的技能卡（Skill Cards）。

## 目录结构

```
opensquad-skills/
├── index.json               # 技能索引，商店从此读取列表
├── likes.json               # 点赞数据（由系统自动维护）

```

## index.json 字段说明

| 字段 | 说明 |
|---|---|
| `id` | 技能唯一标识符（与目录名一致） |
| `name` | 技能显示名称 |
| `description` | 简短描述 |
| `category` | 分类（dev / search / file / data / ai / system） |
| `tags` | 标签列表 |
| `author` | 作者 |
| `version` | 版本号 |
| `download_url` | zip 文件的 raw.githubusercontent.com 下载地址 |

## 安装行为

商店安装时会将 zip 内容（`SKILL.md` + `tools.py`）解压至项目根目录的 `skills/{id}/` 下。

## 贡献技能

1. 新建 `{skill_id}/` 目录，创建 `SKILL.md` 和 `tools.py`
2. 在 `index.json` 中追加条目
3. 运行 `python ../build_zips.py` 生成 zip
4. 提交 PR
