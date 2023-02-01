# 集群性能仿真平台
# 项目简介

平台提供了模拟模型负载在集群下进行分布式训练，对集群性能分析和展示的功能。
## 功能特性

- 集群硬件配置调整
- 拓扑算法选择
- 模型负载选择
- 模拟平台抖动
- 集群拓扑图可视化
- 集群性能分析及可视化
- 数据并行训练
### 环境依赖
node.js，typescript语言，react-ui，d3.js框架
### 使用安装

- 安装所需依赖
  
  在已有node.js、typescript环境下

  在终端进入ef-topo-core目录后`npm install`

  在终端进入ef-topo-web目录后`npm install`
- 编译构建代码
  
  在终端进入ef-topo-core目录后`npm run build`

  在终端进入ef-topo-web目录后`npm run build`
- 在浏览器启动
  
  在终端进入ef-topo-web目录后`npm run serve`

- 在浏览器调试
  
  在终端进入ef-topo-web目录后`npm run watch`

  打开另一个终端`npm run serve`
- 进行单元测试
  在终端进入ef-topo-core目录后`npm run test`
### 目录结构描述
```
 │─ef-topo-core  拓扑后端逻辑代码
    │  │─dist 编译构建后的文件存放目录
    │  │─node_modules 依赖存储目录
    │  │─src\core
    │  │  │─opt       
    │  │  ├─sim
    │  │  │  │  ccl.ts  添加通信任务broadcast、reduce、scatter等
    │  │  │  │  cfg.ts  硬件、模型、拓扑、平台等配置
    │  │  │  │  overload.ts 定义模型负载及操作
    │  │  │  │  task.ts  计算任务、通信任务、规约任务等执行操作
    │  │  │  │  training.ts 模型训练、计算性能
    │  │  │  │  
    │  │  │  └─data
    │  │  │          cfg.leo.rn50.hvd.pod160.json 全部配置参数
    │  │  │          
    │  │  ├─topo
    │  │  │      device.ts 定义连接
    │  │  │      topo.ts 定义拓扑算法
    │  │  │      
    │  │  └─utils  通用功能，定义array类操作、产生随机数、序列化
    │  │          array_util.ts 
    │  │          common_util.ts
    │  │          random_util.ts
    │  │          serialize.ts
```
```
 │─ef-topo-web  拓扑前端页面代码
    │  │─dist 编译构建后的文件存放目录
    │  │─node_modules 依赖存储目录
    │  │─src
    │  │  │  app.ts   主程序入口    
    │  │  │  chart.ts   全局fps图构建
    │  │  │  layout.ts  拓扑图布局构建
    │  │  │  perf.ts    性能变量动态变化
    │  │  │  player.ts  拓扑启动暂停
    │  │  │  util.ts    通用功能
    │  │  │  view.ts    画拓扑图
    │  │─index.html    静态页面
```
### 截图
![图](https://i.hd-r.cn/1301a143f366e9137e53e53fea1c5940.png)

  