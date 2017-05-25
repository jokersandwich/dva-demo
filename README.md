# Ant Design 项目实践

<strong>笔记</strong>

文件启动顺序：
npm start => package.json => .roadhogrc (脚手架) => index.js => router.js => IndexPage.js (首页)

直接推送：
`dva new xxx` 创建的文件夹，想推送到 github，先删除 `package.json` 中的 `"precommit": "npm run lint"`

数据流向：

<img src="https://camo.githubusercontent.com/c826ff066ed438e2689154e81ff5961ab0b9befe/68747470733a2f2f7a6f732e616c697061796f626a656374732e636f6d2f726d73706f7274616c2f505072657245414b62496f445a59722e706e67" />
