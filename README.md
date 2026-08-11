# 浮光笔记

基于 Hugo 与 Blowfish 的中文个人博客。

## 本地预览

```bash
./bin/hugo server -D
```

打开终端显示的本地地址即可预览。

## 新建文章

```bash
./bin/hugo new content posts/my-new-post/index.md
```

编辑生成的 `index.md`，并将 `draft` 改为 `false` 后发布。

## 生产构建

```bash
./bin/hugo --minify
```

生成结果位于 `public/`。

## 个性化

- 站点标题、作者信息：`config/_default/languages.zh-cn.toml`
- 菜单：`config/_default/menus.zh-cn.toml`
- 首页和文章显示选项：`config/_default/params.toml`
- 正式域名：`config/_default/hugo.toml` 中的 `baseURL`

项目已附带 Hugo 0.164.0 Extended（Apple Silicon），因此不依赖系统中较旧的 Hugo。若要升级全局 Homebrew 版本，请先修复 `/opt/homebrew/Cellar` 的目录所有权，再执行 `brew upgrade hugo`。

## 使用 Obsidian 写作

在 Obsidian 中将本项目根目录作为仓库打开。项目已配置标准 Markdown 链接、文章目录内附件和模板目录，并隐藏主题、构建结果等无需编辑的文件。

最便捷的使用方式是直接双击项目根目录中的三个文件：

- `新建文章.command`：输入标题，自动创建 `content/posts/时间戳/index.md` 并用 Obsidian 打开。
- `预览博客.command`：启动 Hugo 并打开 `http://localhost:1313/`。
- `生成发布文件.command`：执行生产构建，结果写入 `public/`。

文章默认是草稿。写完后将文章属性中的 `draft` 改为 `false`，再生成发布文件。

图片可以直接拖到文章中；文件会和该文章的 `index.md` 放在同一目录，并使用 Hugo 可识别的相对路径。

如果手动创建笔记，可在 Obsidian 命令面板中选择“模板：插入模板”，然后使用 `博客文章` 模板。
