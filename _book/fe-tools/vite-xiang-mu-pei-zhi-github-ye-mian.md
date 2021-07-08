# vite项目 配置GitHub页面

## vite 创建Vue3项目

\([https://segmentfault.com/a/1190000039261260](https://segmentfault.com/a/1190000039261260)\)

## 配置 GitHub

1. 修改 `vite.config.js`

   ```javascript
   import { defineConfig } from 'vite'
   import vue from '@vitejs/plugin-vue'
   // https://vitejs.dev/config/
   export default defineConfig({
     plugins: [vue()],
     base:'/viteProject/'   // 对应GitHub项目名称
   })
   ```

2. 添加`deploy.sh`文件

   ```text
   # 发生任何错误时终止
   set -e

   # 构建
   npm run build

   # 进入输出产物文件夹
   cd dist

   # 如果你要部署到自定义域名
   # echo 'www.example.com' > CNAME

   git init
   git add -A
   git commit -m 'deploy'

   # 如果你要部署在 https://<USERNAME>.github.io
   # git push -f git@github.com:<USERNAME>/<USERNAME>.github.io.git master

   # 如果你要部署在 https://<USERNAME>.github.io/<REPO>
   git push -f git@github.com:Wang9977/viteProject.git master:gh-pages

   cd -
   ```

3. 执行`deploy.sh`
   * 切换到git bash 命令行
   * 执行 `./deploy.sh`
4. github部署
   * 打开GitHub对应项目 setting页面
   * 在左边菜单栏选择Pages
   * Source 选择gh-pages分支
   * 

[demo](https://wang9977.github.io/viteProject/)

