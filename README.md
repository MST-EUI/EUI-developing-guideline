
### 初始化

1. 首先本地新建空文件夹，比如 `eui-dialog`，接着依次执行如下命令：

```
$ npm install @mistong/eui-cli -g
$ eui init
```
* 在 [MST-EUI 仓库](https://github.com/MST-EUI) 建立对应组件仓库并关联，组件仓库名称和组件名称保持一致，比如：`eui-dialog`。

> 组件 `package.json` 里的 `name` 都以 `@mistong/eui-` 开头，比如 `@mistong/eui-dialog`。
> `eui-dialog` 这种形式的命名是组件 github 仓库的命名格式，在 github org [MST-EUI](https://github.com/MST-EUI) 下统一管理。
> `@mistong/eui-dialog` 是组件最终发布到 `npm` 的名称，因为所有组件发布的包都放在 `npm` 的 org [@mistong](https://www.npmjs.com/package/@mistong/eui-cli) 下统一管理。


### 开发

1. 单元测试：放置于 `/__test__` 文件夹，代码覆盖率 `>= 90%`。
2. DEMO：放置于 `/demo` 文件夹。
3. `README.md` 要详细给出组件 `api` 说明。
4. `src` 目录由 `index.js` 统一导出模块。
5. 开发分支命名格式为 `develop/版本号` 格式，比如：`delelop/0.1.0`（版本号默认从 `0.1.0` 开始，遵循 `npm` 包版本管理规范）。


### 发布
1. 修改 `HISTORY.md`，记录当前发布的类型及简单描述，比如

```
# History
----

## 0.1.1

* `CHANGED` add loading support

## 0.1.0

* `NEW` first version

```

> `类型` 可选 `[NEW, CHANGED, FIX, FEAT, DEPRECATED]`，其他等。

2. 合并 `master` 分支最新代码到当前开发分支
3. 给当前开发分支打 `tag`，`tag` 格式为 `release/版本号`，比如：当前开发分支 `develop/0.1.2`，那么发布 `tag` 则默认为 `git tag release/0.1.2`
4. `push` 当前 `tag` 到远端仓库，命令为 `git push origin tag名`，比如：`git push origin release/0.1.2`
5. 打包并发布到 `npm` 仓库（切记发布前一定要打包），执行如下命令

```
$ npm run build
$ npm publish
```

> 第一次发布模块的时候，需要先执行 `npm login` 登录自己的 `npm` 账号，接着执行 `npm publish --access=publish`。


## 编码规范

1. Eslint 开启，通过所有检查。
2. 缩进：2 个空格。
3. 换行：`LF`。
4. 注释：尽量一律英文注释（中文易乱码，逼格不够😀）。
5. 命名：变量命名使用小驼峰，组件名称大驼峰，文件夹(普通文件同)一律小写+`.` 的格式，e.g `webpack.config.js`，
6. 样式名：中横线格式，e.g `eui-dialog`