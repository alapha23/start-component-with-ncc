## 开发手册

### 开发

源码均放在 src 目录下，`src/index.tx` 文件中定义组件类，类中的 public 方法是向用户暴露的方法。

### 构建

在代码开发完成后，需要对项目进行构建并本地测试，该阶段我们可以基于 `tsc` 进行构建，运行 `npm start` 即可生成构建产物 `./dist`。

此时执行如下任意一条指令即可调用目标方法 test：

````bash
npm i && npm run start

cd example

s test

s test --debug

