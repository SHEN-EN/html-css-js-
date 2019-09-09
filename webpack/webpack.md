
style-loader css-loader  打包css的插件

file-loader 打包img的插件

webpack.congig.js配置
const path = require('path');
module.exports = {
    entry: '', //文件入口
    output: {
      filename: 'bundle.js',//打包之后的文件名
      path: path.resolve(__dirname, 'demo')//打包之后的文件所在目录
    },
    module：{
    rules:[
        {
            test: ,//正则 example:test:/\.(jpg|png|svg|gif)$/
            use:[]//使用什么模块来匹配 example:use:['file-loader']
        }
        ]
    }
  };

html-webpack-plugin 管理外联的css 和 js 给每个js加入hash值

const path = require('path');
const HtmlWebpackPlugin =require('html-webpack-plugin');
module.exports = {
    entry: '', //文件入口
    output: {
      filename: 'bundle.js',//打包之后的文件名
      path: path.resolve(__dirname, 'demo')//打包之后的文件所在目录
    },
    module：{
    rules:[
        {
            test: ,//正则 example:test:/\.(jpg|png|svg|gif)$/
            use:[]//使用什么模块来匹配 example:use:['file-loader']
        }
        ]
    },
    plugins:[
    new HtmlWebpackPlugin({
            title:''
    })
    ]
  };

const {CleanWebpackPlugin} = require('clean-webpack-plugin')  每次打包清理指定文件夹新版本用法

plugins:[
     new CleanWebpackPlugin()
]

webpack-dev-server  生成一个web服务器
 devServer: {
        contentBase: "./demo",//本地服务器所加载的页面所在的目录
        historyApiFallback: true,//不跳转
        inline: true//实时刷新
    },

package.json:
"scripts":{
     "serve": "webpack-dev-server --open"
}