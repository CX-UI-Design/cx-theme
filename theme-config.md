1、首先安装「主题生成工具」，可以全局安装或者安装在当前项目下，推荐安装在项目里，方便别人 clone 项目时能直接安装依赖并启动，这里以全局安装做演示。

npm i element-theme -g

2、安装白垩主题，可以从 npm 安装或者从 GitHub 拉取最新代码。

# 从 npm
npm i element-theme-chalk -D

# 从 GitHub
npm i https://github.com/ElementUI/theme-chalk -D

3、主题生成工具安装成功后，如果全局安装可以在命令行里通过 et 调用工具，如果安装在当前目录下，需要通过 node_modules/.bi

et -i [可以自定义变量文件]
如：et -i theme-config.scss

4、直接编辑 theme-config.scss 文件内容，配置参数。

5、编译主题，保存文件后，到命令行里执行 et 编译主题，如果你想启用 watch 模式，实时编译主题，增加 -w 参数；如果你在初始化时指定了自定义变量文件，则需要增加 -c 参数，并带上你的变量文件名

et -w -c theme-config.scss -o ./src/element-ui/




注意：2.3.3版本存在样式编译报错问题：

node_modules/element-theme-chalk/src/table.scss
Undefined variable: "$--table-border-color".

$--table-border-color 缺失，自行增加该配置参数到table样式中
$--table-border-color: 1px solid $--border-color-light !default; //表格边框
