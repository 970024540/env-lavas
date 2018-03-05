# pwa-project

> 这是一个 Lavas PWA 项目

## npm 相关命令

``` bash
# 安装工程依赖
npm install

# 在本地启动调试 server
npm run dev

# 构建线上生产环境产物
npm run build

# 启动编译后的代码，注意，需要在 dist 目录中启动，仅 SSR 模式下有效
npm run start

# 检查代码是否符合规范
npm run lint
```
#项目目录说明
```
├── assets                          # 会被 webpack 构建到生成目录的文件中
├── static                          # 原样复制到生成目录中，会以独立的文件形式存在 
├── node_modules                    # node.js模块包文件夹 
├── components                      # 存放 Vue 的组件
  └──UpdateToast.vue                # 在 /core/App.vue 中被引用,用于 Service Worker 更新时提示用户
  └──ProgressBar.vue                # 在 /core/entry-client.js 中被引用，在页面切换时在顶部展示加载的进度条
├── core                            # webpack entry, 全局样式框架，Vue app 启动器等等
├── pages                           # 存放每个页面的 vue 组件,可自动生成路由规则 *:app.vue=>/app
├── lavas.config.js                 # build 构建,errorHandler 错误处理,middleware 中间件,router 路由规则..
├── server.dev.js                   # 本地配置信息
├── server.prod.js                  # 打包配置信息
├── .lavas                          # 自动生成的路由规则，以及处理热加载 (hotreload) 等都放置在这里.
├── babelrc, .editorconfig, .fecsignore, .fecsrc, .gitignore
                                    # 这些文件实际上并不属于 Lavas，而是项目通用文件，分别处理 babel 对 es6/7 的转码规则，IDE 的配置，fecs 代码风格检查的配置和 git 的忽略文件，开发者一般不需要修改。
├── LINCENSE,package.json,README.md # 这些文件也不属于 Lavas
```

Lavas 工程模版基于 [vue-template-vue](https://github.com/lavas-project/lavas-template-vue/) 模版的 `release-*` 分支创建。
如果想要了解具体如何玩转整个 Lavas 创建的 PWA 工程, 请查看[Lavas 官网教程](https://lavas.baidu.com/guide)。

## Changelog

详细的 Changelog 请看 [Release Notes](https://github.com/lavas-project/lavas-template-vue/releases)
