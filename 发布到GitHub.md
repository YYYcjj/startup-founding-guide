# 发布到 GitHub 步骤

本仓库内容已在本机 `git commit` 完成，只差「推送到 GitHub」这一步授权。
三种方式任选，推荐方式一。

---

## 方式一：用 gh CLI（推荐，最省事）

> 前提：本机已装 `gh`（当前环境已有）。需要你本人在浏览器登录一次 GitHub 账号授权。

**步骤 1 — 进入仓库目录（终端）**
```bash
cd /Users/yyy/WorkBuddy/2026-08-24-19-28-16/startup-founding-guide
```

**步骤 2 — 登录授权（会打开浏览器，网址 github.com）**
```bash
gh auth login
```
- 选择 `GitHub.com`
- 认证方式选 `HTTPS` 或 `SSH`（本机已有 SSH key，可选 SSH）
- 按终端提示在浏览器完成授权（授权网址即 github.com 的 OAuth 页面）

**步骤 3 — 建私有仓库并一键推送**
```bash
gh repo create startup-founding-guide --private --source=. --push \
  -d "年轻创业者全攻略：开公司+家庭/健康/关系/资产安全"
```
> 想公开：把 `--private` 改成 `--public`

**完成后仓库地址**
```
https://github.com/YYYcjj/startup-founding-guide
```

---

## 方式二：用 Personal Access Token（PAT）

不想走 `gh auth login` 时可用：
1. 打开网址生成 token：https://github.com/settings/tokens
2. 勾选 `repo` 权限，生成后把 token 交给助手
3. 助手用 API 建仓并推送（**用完即清、不留存**）

---

## 方式三：网页手动建仓 + 本地 push（不推荐）

1. 打开 https://github.com/new ，手动新建仓库 `startup-founding-guide`（选 Private）
2. 本地执行：
```bash
git remote set-url origin https://github.com/YYYcjj/startup-founding-guide.git
git push -u origin main
```
（需本机已登录 GitHub 凭证或配置 SSH key）

---

## 当前本地仓库状态
- 已提交 5 个文件：README.md / 创业必学清单与避坑.md / 家庭健康与关系指南.md / 年轻创业者全攻略.md / 注册清单.md
- 远程地址已配：`git@github.com:YYYcjj/startup-founding-guide.git`
- 卡点：GitHub MCP 应用无建仓权限（403），故需上述任一授权方式。
