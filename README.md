
## 组件初始化

```
$ mkdir <eui-demo> && cd <eui-demo>
$ npm install @mistong/eui-cli -g
$ eui init
```

> 这里 `<eui-demo>` 是占位符，执行时替换为要开发的模块名称即可，比如要开发 `eui-dialog` ，则命令为 `mkdir eui-demo && cd eui-demo`


## 开发


### 普通代码提交

```
$ git add .
$ git-cz
$ git push
```

> 使用 `git-cz` 命令提交代码（或者 `npm run commit`），统一 `lint` 检查和提交规范


### 版本变更

```
$ git add .
$ git-cz
$ npm version patch
```

> 使用 [`npm version`](https://docs.npmjs.com/cli/version) 控制版本变更，`npm version patch` 会自动给上个版本打标签并推送到仓库，并自动更新版本号

## 发布

```
$ npm run build
$ npm publish
```

> 第一次发布模块的时候，需要先执行 `npm login` 登录自己的 `npm` 账号，接着执行 `npm publish --access=public`


## 编码

### 项目结构

1. 单元测试：放置于 `/__test__` 文件夹，建议代码覆盖率 `>= 90%`
2. DEMO：放置于 `/demo` 文件夹
3. `README.md` 要详细给出组件 `api` 说明
4. `src` 目录由 `index.js` 统一导出模块
5. 默认在 `master` 分支开发即可，发布版本统一使用 `npm version patch` 命令即可

### 通用

1. Eslint 开启，通过所有检查
2. 缩进：2 个空格
3. 换行：`LF`
4. 注释：尽量一律英文注释（中文易乱码，逼格不够😀）
5. 命名：变量命名使用小驼峰，组件名称大驼峰，文件夹(普通文件同)一律小写+`.` 的格式，e.g `webpack.config.js`
6. 样式名：中横线格式，e.g `eui-dialog`

### 国际化
1. 国际化统一字段为 `locale`，可选值 [`zh-cn`, `en`]，默认值 `zh-cn`

### 主题支持
1. 统一提供 `prefixCls` API，以支持组件样式完全自定义（参考初始化模板示例）
2. 涉及主题的颜色统一管理，依赖 `@mistong/eui-css`，请勿将主题色相关代码硬编码进入组件内