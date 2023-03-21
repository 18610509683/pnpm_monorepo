### git submodule子模块管理多仓库、pnpm使用步骤
#### 一、从零开始,全局安装： npm i pnpm -g
##### 1、目录下执行命令行 pnpm init
##### 2、复制项目中的 .npmrc .gitignore pnpm-workspace.yaml文件到你的主项目目录（公共依赖目录）
##### 3、添加子项目：git submodule add <git仓库远程地址> <要放置的路径>，如：git submodule add http://47.107.126.107:3000/dingjun.hu/newDA.git ./projects/newDA/
##### 4、进入子项目，添加dev和build脚本
##### 5、在根目录 pnpm i 安装所有依赖、子项目依赖版本不一致需要过滤安装,如：pnpm --filter @packages/utils add dayjs (用于js模块)、pnpm --filter ./projects/web1 add vue@2.7（用于前端项目）
##### 6、pnpm run -r dev(一键启动)、pnpm run -r build(一键打包)，其他命令类推。-r参数必须在dev、build脚本前。
