# github-cicd-practice

实验一：静态网页自动校验并部署到 GitHub Pages。

## 目录

```
dist/index.html                      # 要发布的静态页面
.github/workflows/deploy-pages.yml   # 校验 + 部署工作流
```

## 发布方式

push 到 `main` 后，工作流先校验 `dist/index.html` 是否存在，再用
`peaceiris/actions-gh-pages` 把 `dist/` 推到 `gh-pages` 分支。

仓库 **Settings → Pages** 的 Source 必须选择：

- Deploy from a branch
- Branch: `gh-pages`，目录 `/ (root)`

## 访问地址

```
https://<你的 GitHub 用户名>.github.io/github-cicd-practice/
```

## 验证这一版是否上线

修改 `dist/index.html` 里的 `v1` 标记（例如改成 `v2`），提交并 push，
等 Actions 变绿后刷新页面，确认标记变化。
