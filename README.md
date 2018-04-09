# webpackExample
A Webpack example
Webpack：模块打包器，分析项目结构。找到js模块转换一些不能直接运行的语言（TypeScript，Scss，ES6等），供浏览器使用。
1. Webpack的功能：
    1. 生成sourceMap：对应编译文件和源文件
2. webpack构建本地服务器
3. Loaders：webpack调用外部的脚本或工具，实现对不同格式的文件的处理，（Scss/less =》 css，ES6/ES7 =〉js，jsx =》js）
    * test：一个用以匹配loaders所处理文件的拓展名的正则表达式（必须）
    * loader：loader的名称（必须）
    * include/exclude:手动添加必须处理的文件（文件夹）或屏蔽不需要处理的文件（文件夹）（可选）；
    * query：为loaders提供额外的设置选项（可选）
    1. Babel：ES6/ES7/JSX ==》JS
    2. CSS:通过使用css模块，css中有很多全局的类名、动画名默认值只作用于当前模块。在cssloader中，对类名进行格式的转变。可以避免，相同类名对不同组件之间的污染。
        * css-loader:可以使用类似@import /url(…)的方法实现require()功能
        * style-loader：将所有计算后的样式加入页面中
4. Plugins
    1. html-webpack-plugin:根据一个index.html模版。生成一个引用JS文件的新的index.html。（因为有的时候生成的bundle.js名字添加了hash会不同）
    2. Hot Module Replacement
        * webpack配置文件中添加HMR插件
        * webpack dev server中添加了hot参数
    3. 优化插件
        * OccurenceOrderPlugin：为组件分配ID，可以分析优先考虑使用最多的模块，并为他们分配最小的ID
        * UglifyJsPlugin:压缩JS代码
        * ExtractTextPlugin：分离CSS JS代码
    4. 缓存：内容改变，文件名称相应改变。（为静态资源提供hash值）

