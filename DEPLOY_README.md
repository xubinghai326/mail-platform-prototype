# 邮件发放平台原型部署说明

这套原型现在已经是纯静态站点结构，可以直接部署到任意静态托管平台。

## 目录说明

- `index.html`
  - 站点根入口。访问域名根路径时会自动跳转到原型首页。
- `prototype-index.html`
  - 原型首页入口。
- `mail-platform-prototype.html`
  - 主控台原型。
- `incident-response-prototype.html`
  - 异常熔断 / 事故处置页。
- `prototype-assets/ui.css`
  - 共享样式文件。
- `.nojekyll`
  - 方便 GitHub Pages 直接按静态文件方式发布。

## 目标效果

部署完成后，别人只需要访问一个网址，例如：

`https://your-domain.example/`

就可以直接打开原型首页，并继续进入两个展示页面。

## 方案一：GitHub Pages

适合：

- 想要一个免费、稳定、公开可访问的网址
- 页面是纯静态文件

步骤：

1. 新建一个 GitHub 仓库
2. 把当前目录中的以下文件上传到仓库根目录
   - `index.html`
   - `prototype-index.html`
   - `mail-platform-prototype.html`
   - `incident-response-prototype.html`
   - `prototype-assets/`
   - `.nojekyll`
3. 进入 GitHub 仓库的 `Settings -> Pages`
4. 在 `Build and deployment` 中选择：
   - `Source: Deploy from a branch`
   - `Branch: main`
   - `Folder: /root`
5. 保存后等待几分钟
6. GitHub 会生成一个网址，通常形如：
   - `https://你的用户名.github.io/仓库名/`

注意：

- 如果仓库名不是个人主页仓库，页面路径里会带仓库名
- 当前页面已使用相对路径，适合直接部署到子目录

## 方案二：Vercel

适合：

- 想要更快的部署体验
- 想绑定自己的域名

步骤：

1. 登录 Vercel
2. 选择 `Add New Project`
3. 导入你的 GitHub 仓库
4. 框架选择保持 `Other`
5. 不需要构建命令
6. 输出目录保持根目录
7. 点击部署

部署完成后，会得到一个 Vercel 域名，例如：

`https://your-project.vercel.app/`

## 方案三：Netlify

适合：

- 希望拖拽上传直接上线

步骤：

1. 登录 Netlify
2. 选择 `Add new site -> Deploy manually`
3. 直接把当前目录拖进去
4. 发布完成后得到一个公开网址

## 当前临时可分享链接

如果本地临时服务仍在运行，你也可以继续使用已经生成的临时公网链接。

但临时链接不是长期稳定方案，进程结束或网络断开后会失效。

## 推荐结论

如果你要发给面试官、同学或团队长期查看，优先推荐：

1. `GitHub Pages`
2. `Vercel`

如果你愿意，我下一步可以继续帮你做：

1. 生成一个适合上传到 GitHub 的最小仓库结构说明
2. 继续把这套页面改成更适合直接部署到 GitHub Pages 的版本
3. 如果你有 GitHub 仓库路径，我可以按仓库路径帮你把链接结构也一起适配好
