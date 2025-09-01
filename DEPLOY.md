# 部署说明

## 🚀 快速部署

### 1. 构建项目
```bash
npm run build
```

### 2. 部署到 GitHub Pages

#### 方法一：手动部署
1. 构建完成后，`dist` 目录包含所有静态文件
2. 将 `dist` 目录中的所有文件复制到你的 GitHub Pages 分支
3. 推送更改到 GitHub

#### 方法二：使用 GitHub Actions 自动部署
创建 `.github/workflows/deploy.yml` 文件：

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout
      uses: actions/checkout@v3
      
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
        
    - name: Install dependencies
      run: npm install
      
    - name: Build
      run: npm run build
      
    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./dist
```

### 3. 配置域名代理

由于你已经配置了域名代理，构建完成后：

1. 确保 `dist` 目录中的文件已部署到你的托管服务
2. 域名代理会自动指向这些静态文件
3. 访问你的域名即可看到网站

## 📁 部署文件说明

构建后的 `dist` 目录包含：

- `index.html` - 主页面文件
- `assets/` - 静态资源目录
  - `index-*.css` - 压缩后的CSS文件
  - `index-*.js` - 压缩后的JavaScript文件

## 🔧 自定义部署

### 修改构建输出目录
在 `vite.config.js` 中修改：

```javascript
export default defineConfig({
  build: {
    outDir: 'your-custom-output-dir', // 自定义输出目录
  }
})
```

### 修改资源路径
如果需要部署到子目录，在 `vite.config.js` 中添加：

```javascript
export default defineConfig({
  base: '/your-subdirectory/', // 部署到子目录时使用
})
```

## 🌐 其他部署平台

### Netlify
1. 拖拽 `dist` 目录到 Netlify
2. 自动部署完成

### Vercel
1. 连接 GitHub 仓库
2. 自动检测并部署

### 阿里云/腾讯云静态网站
1. 上传 `dist` 目录内容
2. 配置域名解析

## 📝 注意事项

1. **文件路径**: 确保所有资源路径都是相对路径
2. **缓存**: 部署后可能需要清除浏览器缓存
3. **HTTPS**: 建议使用HTTPS协议访问
4. **性能**: 构建后的文件已经过压缩优化

## 🆘 常见问题

### Q: 部署后页面显示空白？
A: 检查资源路径是否正确，确保CSS和JS文件能正常加载

### Q: 图片无法显示？
A: 确保图片文件已正确放置在 `dist` 目录中

### Q: 路由问题？
A: 这是单页应用，确保服务器配置了正确的回退路由

---

部署完成后，你的个人网站就可以通过域名访问了！🎉
