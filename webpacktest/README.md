#webpack
一、管理资源
1.修改index.html的title标签
2.加载css npm install --save-dev style-loader css-loader
3.在webpack.config.js配置加载css文件
const path = require("path"); 
module.exports = { 
	entry:"./src/index.js", 
	output:{ 
		filename:"bundle.js", 
		path:path.resolve(__dirname,"dist") 
	}, 
	module:{ 
		rules:[ {
			 test:/.css$/, 
			 use:[ 
			 	'style-loader', 
			 	'css-loader' 
			] } 
		] 
	} 
} 
4.在src 添加style.css文件
创建一个样式
.hello{ color ： red ;}
5.在./src/index.js中导入style.css文件,并在component()中给元素添加类名hello
import "./style.css";
element.classList.add("hello");
6.执行npm run build 后,浏览网页就能看到hello word变成红色了