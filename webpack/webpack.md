
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