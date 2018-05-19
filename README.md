# vue todo

这个项目是为了学习webpack而创建的项目，课程源于：[Vue+Webpack打造todo应用](https://www.imooc.com/learn/935)

项目使用方式：

``` bash
# 启动本地服务器
npm run dev

# 构建打包项目
npm run build
```

----

课程中 webpack 一些关键的知识点笔记：

1. `cross-env`跨平台坏境变量
2. `host`设置为0.0.0.0 的好处是，我们可以通过localhost，127.0.0.1来进行访问。同时还可以通过内网IP来进行访问(也就是说我们可以通过我们的手机进行访问)

**关于babel:**

- babel-loader
- babel-core (babel编译核心)
- 同时需要在根目录下新建`.babelrc`
- 如果这是我们需要让项目分成生产模式和开发模式的话，还需要安装：
  ○ [babel-preset-env](https://babeljs.cn/docs/plugins/preset-env/) 根据你支持的环境自动决定适合你的 Babel 插件的 Babel preset
- 如果是 vue 项目并且想用`jsx`文件的话，我们还需要安装以下依赖
  ○ babel-plugin-transform-vue-jsx 扩展合并帮助程序作为模块导入以避免重复, 专门处理vue 的jsx文件
  ○ babel-plugin-syntax-jsx
  ○ babel-helper-vue-jsx-merge-props

**配置css环境:**

- autoprefix
- postcss-loader
- 同时需要新建配置`postcss.config.js`
- extract-text-webpack-plugin 可以将 css 抽出来

> chunkhash 和 hash 的区别

在 webpack 里，`chunk`就是一个模块，chunkhash也就是根据这个模块生成的`hash`，这个`chunkhash`是单独的，不会和其他文件有相同的`hash`。

我们当我们使用`[name]-[hash].css`和[name]-[hash].js时，这个`hash`是相同的，指向的是本次打包的应用的`hash`，是共有的。