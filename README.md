# Ant Design 项目实践

#### 笔记

文件启动顺序：
npm start => package.json => .roadhogrc (脚手架) => index.js => router.js => IndexPage.js (首页)

数据流向：

<img src="https://camo.githubusercontent.com/c826ff066ed438e2689154e81ff5961ab0b9befe/68747470733a2f2f7a6f732e616c697061796f626a656374732e636f6d2f726d73706f7274616c2f505072657245414b62496f445a59722e706e67" />

### bug

提交错误：
`dva new xxx` 创建的文件夹，提交前删除 `package.json` 中的 `"precommit": "npm run lint"` （通过github创建的文件夹，提交没有这个问题）

`npm start` 样式不显示：
 `package.json` 中的 `extraBabelPlugins` 从 `env` 中分离出来。
 
     "env": {
        "development": {
          "extraBabelPlugins": [
            "dva-hmr",
            "transform-runtime"
          ]
        },
        "production": {
          "extraBabelPlugins": [
            "transform-runtime",
            ["import", { "libraryName": "antd", "style": "css" }]
          ]
        }
      }
 
 改为：
 
      "env": {
          "development": {
            "extraBabelPlugins": [
              "dva-hmr",
              "transform-runtime"
            ]
          }
        },
        "extraBabelPlugins": [
              "transform-runtime",
              ["import", { "libraryName": "antd", "style": "css" }]
        ]
