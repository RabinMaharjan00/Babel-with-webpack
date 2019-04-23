# To install and use server using babel so that we dont have to reload everytime:

1. npm install --save-dev webpack webpack-dev-server babel-core babel-loader @babel-preset-env babel-cli

2. make webpack.config.js
const path = require('path');

module.exports={
    entry:{
        app:'./src/app.js'
    },
    output:{
        path:path.resolve(__dirname,'dist'),
        filename:'app.bundle.js'
    },
    module:{
        rules:[{
            test:/\.js?$/,
            exclude:/node_modules/,
            loader:'babel-loader',
            query:{
                presets:["@babel/preset-env"]
            }
        }]
    }
}
3.npm run build
4. To automatic compile
"build": "webpack --mode production ",
"start": "webpack-dev-server --output-public-path=/dist/"
in package.json

5. npm start to compile it

[Note]No .babelrc needed
