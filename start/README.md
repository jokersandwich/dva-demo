# start

#### 安装dva-cli

    $ npm install dva-cli -g

    $ dva -v

    0.7.0

#### 创建新应用

    $ dva new dva-quickstart

    $ cd dva-quickstart

#### 安装antd

    $ npm install antd babel-plugin-import --save

#### 配置antd

    //.roadhogrc
    {
      "entry": "src/index.js",
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
    }

#### 生成新文件

    $ dva g route products

    $ dva g model products

    $ dva g component ProductList

#### 编写文件

见<a src="https://ant.design/docs/react/practical-projects-cn">官网</a> 
`components/ProductList.js`, `models/products.js`, `routes/Products.js`

#### 数据写入

    //index.js
    const app = dva({
      initialState: {
        products: [
          { name: 'dva', id: 1 },
          { name: 'antd', id: 2 },
        ],
      },
    });

