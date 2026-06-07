# 个人博客 - WSPN Blog

## 技术方案

- **静态站点生成器**: Hugo
- **主题**: hugo-theme-stack
- **托管**: GitHub Pages
- **自动部署**: GitHub Actions
- **评论**: Giscus (GitHub Discussions)
- **搜索**: 主题内置 Fuse.js

## 项目结构

```
blog_infra/
├── content/posts/          # 博客文章
│   ├── java/               # Java 学习
│   ├── llm/                # 大语言模型/AI
│   ├── vr/                 # VR 开发
│   ├── infra/              # 基础设施(Kafka/Docker等)
│   └── misc/               # 杂项
├── themes/hugo-theme-stack/ # 主题
├── static/images/           # 图片资源
├── hugo.toml                # 站点配置
├── .github/workflows/deploy.yml  # 自动部署
└── archetypes/default.md    # 文章模板
```

## 本地开发

```bash
# 安装 Hugo (Windows)
winget install Hugo.Hugo.Extended

# 初始化子模块（拉取主题）
git submodule update --init --recursive

# 本地预览
hugo server -D

# 创建新文章
hugo new posts/java/my-new-post.md
```

## 部署流程

1. 编写 Markdown 文章
2. `git add . && git commit -m "new post: xxx"`
3. `git push origin main`
4. GitHub Actions 自动构建并部署到 GitHub Pages

## 站点地址

https://<username>.github.io/blog_infra/
