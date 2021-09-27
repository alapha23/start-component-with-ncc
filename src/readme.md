## 开发手册

### 开发

````
在功能调试完成后，需要进行发布前的编译，与之前编译不同的是，此时编译是基于 ncc 进行的，而 ncc 编译过程耗时比较久，而且不支持 watch 模式，因此在之前测试时先基于 `tsc` 进行编译。


1. build 完成后会将 node_modules 删除，详情可以参考 package.json 中的 postbuild 内容
2. package.json 中包含 "autoInstall": false，表明在该组件被加载时不会安装依赖
```

### 平台发布

#### 注册 serverless devs 平台账号

```
s cli platform register
```

#### 已有账号可以直接登录

```
s cli platform login
```
#### 进行发布
在 <projectName> 根目录执行
```
npm run publish
```

### 内部开发者发布

对于内部同学，是基于 github actions 进行发布的，action 相关的 yaml 内容可以参考 [registry-publish.yml](./.github/workflows/registry-publish.yml)。

开发完成后将所有内容上传至 [devsapp](https://github.com/devsapp) 中，然后在相应的 repo 中发布 Release 即可触发对应的发布流程。
若有一些开发态的内容不想发布，可以将其放在 .signore 中，这个文件的作用是在打包发布产物时排除指定文件或目录。目前该文件不支持正则表达式写法。

