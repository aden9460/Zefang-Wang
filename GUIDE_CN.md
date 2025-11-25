# 📘 al-folio 学术网站使用指南

## 🎯 网站信息

- **本地预览地址**: http://localhost:4000/Zefang-Wang/
- **线上网站地址**: https://aden9460.github.io/Zefang-Wang/
- **项目目录**: `/Users/wangzefang/Downloads/myweb/Zefang-Wang`
- **GitHub 仓库**: https://github.com/aden9460/Zefang-Wang

---

## ✅ 已完成的设置

### 1. 环境安装
- ✅ Ruby 3.4.7 (通过 Homebrew)
- ✅ Bundler 2.7.2
- ✅ Jekyll 4.4.1 及所有依赖包（97个gems）

### 2. 项目配置
- ✅ 克隆 al-folio 模板
- ✅ 配置 `_config.yml`:
  - `url: https://aden9460.github.io`
  - `baseurl: /Zefang-Wang`
- ✅ 禁用外部博客源
- ✅ 删除演示 Jupyter notebook

### 3. 部署设置
- ✅ Git 初始化和远程仓库连接
- ✅ 代码已推送到 GitHub
- ⚠️ **待完成**: 在 GitHub 设置 Actions 权限

---

## 🚀 首次部署（GitHub Pages）

### ⚠️ 必须先完成：设置 GitHub Actions 权限

1. **打开浏览器**访问：
   https://github.com/aden9460/Zefang-Wang/settings/actions

2. **向下滚动**到 "Workflow permissions"

3. **选择**：
   - ✓ "Read and write permissions"
   - ✓ "Allow GitHub Actions to create and approve pull requests"

4. **点击 "Save"**

5. **查看部署状态**：
   https://github.com/aden9460/Zefang-Wang/actions

6. **等待 3-5 分钟**，然后访问：
   https://aden9460.github.io/Zefang-Wang/

---

## 📝 如何修改网站内容

### 1. 修改个人信息

编辑 `_config.yml` 文件：

```yaml
# 基本信息
title: blank  # 留空使用全名
first_name: Zefang
middle_name:
last_name: Wang
email: your-email@example.com

# 个人描述
description: >
  PhD student in Computer Science...

# 社交媒体
twitter_username: your_twitter
github_username: aden9460
linkedin_username: your_linkedin
```

### 2. 更换个人照片

```bash
# 替换照片文件（建议 400x400 像素）
cp /path/to/your/photo.jpg assets/img/prof_pic.jpg
```

### 3. 修改关于页面

编辑文件：`_pages/about.md`

```markdown
---
layout: about
title: about
permalink: /
subtitle: Your Affiliation

profile:
  align: right
  image: prof_pic.jpg

news: true  # 显示最新消息
selected_papers: true  # 显示精选论文
social: true  # 显示社交媒体链接
---

在这里写你的个人简介...
```

### 4. 添加论文/出版物

编辑文件：`_bibliography/papers.bib`

```bibtex
@article{wang2024example,
  title={Your Paper Title},
  author={Wang, Zefang and Others},
  journal={Conference/Journal Name},
  year={2024},
  abbr={NeurIPS},
  pdf={paper.pdf},
  code={https://github.com/your-repo},
  selected={true}  # 标记为精选论文
}
```

### 5. 添加项目

在 `_projects/` 目录创建新文件，例如 `project-name.md`：

```markdown
---
layout: page
title: Project Name
description: Short description of the project
img: assets/img/project-preview.jpg
importance: 1
category: work
---

详细的项目描述...

## Features
- Feature 1
- Feature 2

## Results
...
```

### 6. 写博客文章

在 `_posts/` 目录创建文件，格式：`YYYY-MM-DD-title.md`

```markdown
---
layout: post
title: Your Blog Post Title
date: 2025-11-25
description: Brief description
tags: machine-learning deep-learning
categories: research
---

博客内容...

## Heading 1
内容...

## Heading 2
内容...
```

### 7. 添加 News/最新动态

编辑文件：`_news/announcement_1.md`

```markdown
---
layout: post
date: 2025-11-25
inline: true
related_posts: false
---

简短的新闻更新，比如获奖、接受论文等。
```

---

## 🔄 本地开发和预览

### 启动本地服务器

```bash
# 进入项目目录
cd /Users/wangzefang/Downloads/myweb/Zefang-Wang

# 确保 Ruby 环境正确
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/3.4.0/bin:$PATH"

# 启动 Jekyll 服务器
bundle exec jekyll serve

# 或者使用配置文件
bundle exec jekyll serve --config _config.yml
```

**访问**：http://localhost:4000/Zefang-Wang/

### 停止服务器

按 `Ctrl + C`

---

## 📤 更新和推送到 GitHub

### 标准流程

```bash
# 1. 进入项目目录
cd /Users/wangzefang/Downloads/myweb/Zefang-Wang

# 2. 查看修改的文件
git status

# 3. 添加所有修改
git add .

# 或者添加特定文件
git add _config.yml _pages/about.md

# 4. 提交更改（写清楚改了什么）
git commit -m "Update personal information and add new project"

# 5. 推送到 GitHub
git push origin main
```

### 使用访问令牌推送

```bash
git push https://ghp_YOUR_TOKEN@github.com/aden9460/Zefang-Wang.git main
```

**注意**：替换 `ghp_YOUR_TOKEN` 为你的实际令牌

### 常见提交消息示例

```bash
# 修改个人信息
git commit -m "Update personal information and bio"

# 添加新论文
git commit -m "Add NeurIPS 2024 paper to publications"

# 添加新项目
git commit -m "Add deep learning project showcase"

# 修改样式
git commit -m "Update website theme colors"

# 写博客
git commit -m "Add blog post about research experience"
```

---

## 🔍 常见问题

### Q1: 修改了 `_config.yml` 但网站没更新？

**A**: 配置文件修改后需要重启 Jekyll 服务器：
```bash
# 停止服务器（Ctrl + C）
# 重新启动
bundle exec jekyll serve
```

### Q2: 推送后网站没更新？

**A**:
1. 检查 GitHub Actions 是否成功：https://github.com/aden9460/Zefang-Wang/actions
2. 等待 3-5 分钟
3. 强制刷新浏览器（Cmd + Shift + R）

### Q3: 图片不显示？

**A**: 检查图片路径：
- 本地开发：`/assets/img/photo.jpg`
- 线上需要：`/Zefang-Wang/assets/img/photo.jpg`（自动处理）

### Q4: 如何临时禁用某个部分？

**A**: 在 `_config.yml` 中设置：
```yaml
news: false  # 禁用 news
blog_nav: false  # 禁用博客导航
```

### Q5: 遇到 "convert: command not found" 警告？

**A**: 这是 ImageMagick 的警告，不影响网站运行。如果想解决：
```bash
brew install imagemagick
```

---

## 📁 重要文件和目录结构

```
Zefang-Wang/
├── _config.yml           # 主配置文件 ⚠️ 修改需重启
├── _pages/              # 页面（about, publications, etc.）
│   ├── about.md
│   ├── publications.md
│   └── projects.md
├── _posts/              # 博客文章
├── _projects/           # 项目展示
├── _news/               # 最新动态
├── _bibliography/       # 论文引用（BibTeX）
│   └── papers.bib
├── assets/
│   ├── img/            # 图片
│   │   └── prof_pic.jpg  # 个人照片
│   ├── pdf/            # PDF 文件（论文等）
│   └── json/           # 数据文件
├── _sass/              # 自定义样式
└── _site/              # ⚠️ 生成的网站，不要编辑！
```

---

## 🎨 自定义主题

### 修改颜色

编辑 `_sass/_themes.scss`：

```scss
// 定义你的主题颜色
$theme-color: #0066cc;
$hover-color: #004499;
```

### 修改字体

编辑 `_sass/_variables.scss`：

```scss
$font-family: 'Roboto', sans-serif;
```

---

## 🔐 安全提示

### 保护访问令牌

```bash
# ❌ 不要这样（令牌会暴露在历史记录中）
git push https://ghp_TOKEN@github.com/...

# ✅ 使用 SSH 或 配置 credential helper
git config --global credential.helper osxkeychain
```

### 设置 Git 用户信息

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

---

## 🛠️ 常用维护命令

### 更新依赖包

```bash
bundle update
```

### 清理生成的文件

```bash
bundle exec jekyll clean
```

### 查看详细构建信息

```bash
bundle exec jekyll serve --verbose
```

### 构建生产版本

```bash
JEKYLL_ENV=production bundle exec jekyll build
```

---

## 📞 获取帮助

- **al-folio 官方文档**: https://github.com/alshedivat/al-folio
- **al-folio 自定义指南**: [CUSTOMIZE.md](CUSTOMIZE.md)
- **Jekyll 文档**: https://jekyllrb.com/docs/
- **Markdown 语法**: https://www.markdownguide.org/
- **GitHub Pages 文档**: https://docs.github.com/pages

---

## 🎯 快速参考命令

```bash
# 启动本地预览
bundle exec jekyll serve

# 更新和推送
git add .
git commit -m "Your message"
git push origin main

# 查看文件状态
git status

# 查看提交历史
git log --oneline

# 撤销未提交的修改
git checkout -- filename.md

# 撤销最后一次提交（但保留修改）
git reset --soft HEAD~1

# 查看远程仓库
git remote -v
```

---

## 📋 快速检查清单

部署前检查：
- [ ] 设置了 GitHub Actions 权限
- [ ] 更新了个人信息（姓名、邮箱等）
- [ ] 替换了个人照片
- [ ] 修改了关于页面
- [ ] 添加了至少一篇论文/项目
- [ ] 测试了本地预览
- [ ] 提交信息清晰明了

---

## 🔄 版本历史

- **v1.0** (2025-11-25): 初始版本
  - 完成基础配置
  - 设置 GitHub Pages 部署
  - 创建使用指南

---

**最后更新**: 2025-11-25
**文档作者**: Created with Claude Code
**al-folio 版本**: Latest (from template)

---

## 💡 提示和技巧

1. **定期备份**：重要修改前先创建 git 分支
   ```bash
   git checkout -b backup-20251125
   ```

2. **使用草稿**：在 `_drafts/` 目录创建草稿文章，不会被发布
   ```bash
   bundle exec jekyll serve --drafts  # 预览草稿
   ```

3. **查看构建错误**：如果网站没更新，查看 Actions 日志找错误

4. **测试部署配置**：修改 `_config.yml` 后先本地测试

5. **保持依赖更新**：定期运行 `bundle update` 更新 gems

---

**祝你使用愉快！🎉**

如有问题，请参考 al-folio 官方文档或在 GitHub 仓库提 Issue。
