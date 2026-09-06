# 发布到 GitHub 步骤

> ✅ **状态：已发布（2026-09-06）**
> 仓库已成功推送至 GitHub，且已设为 **私有（Private）**。
> 地址：https://github.com/YYYcjj/startup-founding-guide
> 含 6 个文档 + .gitignore，全部已推送。

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

## 方式三：网页手动建仓 + 本地 push

> ⚠️ 实测：本机 SSH key（id_ed25519）未注册到 GitHub（`Permission denied (publickey)`），
> 故无法从本环境直接 SSH 推送。请在**你自己的 Mac 终端**完成下面步骤（用你已登录的 GitHub 凭证）。

1. 打开 https://github.com/new ，手动新建仓库 `startup-founding-guide`：
   - 设为 **Private**
   - **不要**勾选 "Add a README file" / .gitignore / license（保持空仓库，因为本地已有内容）
   - 点 **Create repository**
2. 在你自己的 Mac 终端进入仓库目录并推送：
```bash
cd /Users/yyy/WorkBuddy/2026-08-24-19-28-16/startup-founding-guide
git remote set-url origin https://github.com/YYYcjj/startup-founding-guide.git
git push -u origin main
```
3. 若 push 要求输入账号密码：GitHub 已停用密码登录，**密码处填 PAT**（在 https://github.com/settings/tokens 生成、勾 repo 权限）；或用 `gh auth login` 登录后直接 push。

> 最省事替代：把 PAT 交给助手，助手用 HTTPS 从本环境直接推送（无需你跑命令）。

---

## 当前本地仓库状态
- 已提交 6 个文件（含 .gitignore）：README.md / 创业必学清单与避坑.md / 家庭健康与关系指南.md / 年轻创业者全攻略.md / 注册清单.md / 发布到GitHub.md
- 远程：`https://github.com/YYYcjj/startup-founding-guide.git`（私有，已推送）
- 推送已通过方式二（classic PAT，带 `repo` 权限）完成，凭据用完即清。
