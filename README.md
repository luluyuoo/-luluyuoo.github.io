# Yuyan Liu — Academic Homepage

这是已确认最终版本的 GitHub Pages 发布文件。页面使用英文；这份操作说明使用中文。

## 文件说明

- `index.html`：完整网页与个人信息，以后更新成绩、论文、竞赛、证书和项目主要编辑这个文件。
- `styles.css`：最终版本编译后的完整样式，包含响应式布局和动画。
- `profile.jpg`：头像。
- `favicon.svg`：浏览器标签页图标。
- `.nojekyll`：告诉 GitHub Pages 直接发布静态文件。
- `README.md`：本说明；不会作为首页显示，因为已有 `index.html`。

这些就是发布所需的全部文件。不需要安装 Node.js、不需要运行 npm/pnpm，也不需要添加 GitHub Actions 工作流。原 Sites 工程和私有预览保持不变。

## 一、创建仓库

1. 登录 https://github.com ，确认账号为 `luluyuoo`。
2. 点击右上角 `+` → `New repository`。
3. Owner 选择 `luluyuoo`。
4. Repository name 填写 `luluyuoo.github.io`，不要加 `https://`。
5. 选择 `Public`。这个网站上线后，网页里的姓名、成绩、邮箱等信息会公开展示。
6. 可以勾选 `Add a README file`，这样创建后会直接出现 `Add file` 按钮。
7. 点击 `Create repository`。

如果该仓库已存在，请直接使用它；先备份原有网站文件，避免误覆盖。

## 二、上传网站（网页操作，无需命令行）

1. 将 `luluyuoo-github-pages-final.zip` 解压。
2. 打开解压后的文件夹，找到 `index.html`、`styles.css`、`profile.jpg`、`favicon.svg` 和 `README.md`。
3. 在 GitHub 仓库的 `Code` 页点击 `Add file` → `Upload files`。
4. 把上述文件拖入上传区域。上传的是这些文件本身，**不要上传 ZIP，也不要将外层文件夹作为一个子文件夹上传**。
5. 在下方提交说明中填写 `Publish academic homepage`。
6. 选择直接提交到 `main`，点击 `Commit changes`。
7. 确认仓库根目录直接能看到 `index.html`，而不是需要再点击一层文件夹才能看到。

### 补上 .nojekyll

Windows 资源管理器或网页上传有时不会显示/带上这个点开头的文件。若仓库没有它：

1. 在仓库点击 `Add file` → `Create new file`。
2. 文件名输入 `.nojekyll`（前面有一个英文句点）。
3. 文件内容可以留空；如果界面不允许，输入一个空格即可。
4. 点击 `Commit changes`，提交到 `main`。

## 三、开启 GitHub Pages

1. 在这个仓库顶部点击 `Settings`。
2. 左侧点击 `Pages`。
3. 在 `Build and deployment` 中，将 `Source` 设为 `Deploy from a branch`。
4. Branch 选择 `main`；旁边的目录选择 `/(root)`。
5. 点击 `Save`。
6. 等待 GitHub 完成部署。通常几分钟，官方说明最多可能需要约 10 分钟。
7. 再回到 `Settings` → `Pages`，点击 `Visit site`。

最终网址：

https://luluyuoo.github.io/

这里不需要选择 `GitHub Actions` 作为 Source，因为发布包已经是生成完毕的静态网页。你仍可能在 `Actions` 页看到 GitHub 自动执行的 Pages 部署任务，这是正常的。

## 四、以后如何更新

### 改文字和成绩

1. 在 GitHub 仓库打开 `index.html`。
2. 点击铅笔图标编辑。
3. 使用搜索定位 `Freshman Year`、`4.75`、`Publications`、`Competitions &amp; Certificates` 或 `Things I Have Built`。
4. 修改现有文字；添加新学年或新成果时，可以复制相应完整 HTML 卡片块后再修改内容。不要删除配对的标签。
5. 点击 `Commit changes`。GitHub Pages 会自动更新。

也可以在本地用 VS Code 编辑，然后通过 `Add file` → `Upload files` 上传修改后的同名文件。

### 换头像

将新头像命名为 `profile.jpg` 后替换同名文件；请确保它确实是 JPG 图片。若换为 PNG，需要一起修改 `index.html` 中的图片路径。

### 本地看效果

直接双击 `index.html`，浏览器即可预览。CSS 动画是否生效取决于浏览器支持情况，与当前预览网站一致。

### 可选：以后用 Git 命令更新

如果希望使用 Git，先安装 Git 并完成 GitHub 登录授权，然后在一个新的目录克隆仓库：

```powershell
git clone https://github.com/luluyuoo/luluyuoo.github.io.git
cd luluyuoo.github.io
```

将发布包里的文件复制进这个克隆目录（保留 `.git` 文件夹），修改后执行：

```powershell
git add .
git commit -m "Update academic homepage"
git push
```

请使用这个单独的 GitHub 仓库目录；无需修改原 Sites 工程的远程仓库配置。

## 五、常见问题

- **404**：检查仓库名是否恰好为 `luluyuoo.github.io`，Pages 是否选择 `main` 和 `/(root)`，根目录是否有 `index.html`。
- **有文字但没有样式/头像**：检查 `styles.css`、`profile.jpg` 是否与 `index.html` 在同一层，文件名大小写是否一致。
- **看到 README 而不是网站**：通常是 `index.html` 不在发布根目录，或文件名不正确。
- **改完没更新**：先等部署任务完成，再用 `Ctrl + F5` 强制刷新。
- **部署失败**：打开仓库的 `Actions` 页，查看最近的 `pages build and deployment` 任务及其报错。
- **Git 推送登录**：不要使用 GitHub 账户密码作为 Git 密码；使用 Git Credential Manager 的浏览器登录、SSH，或按 GitHub 提示配置令牌。不要把令牌写进网页文件。

## 官方参考

- 创建 Pages：https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- 配置发布来源：https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
