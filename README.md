# 1. React入门
## 1.1. React的基本认识
	1). Facebook开源的一个js库
	2). 一个用来动态构建用户界面的js库
	3). React的特点
		Declarative(声明式编码)
		Component-Based(组件化编码)
		Learn Once, Write Anywhere(支持客户端与服务器渲染)
		高效
		单向数据流
	4). React高效的原因
    	虚拟(virtual)DOM, 不总是直接操作DOM(批量更新, 减少更新的次数) 
    	高效的DOM Diff算法, 最小化页面重绘(减小页面更新的区域)

## 1.2. React的基本使用
	1). 导入相关js库文件(react.js, react-dom.js, babel.min.js)
	2). 编码:
		<div id="container"></div>
		<script type="text/babel">
			var aa = 123#  #
			var bb = 'test'
			ReactDOM.render(<h1 id={bb}>{aa}</h1>, containerDOM)
		</script>

## 1.3. JSX的理解和使用
	1). 理解
		* 全称: JavaScript XML
		* react定义的一种类似于XML的JS扩展语法: XML+JS
		* 作用: 用来创建react虚拟DOM(元素)对象
	2). 编码相关
		* js中直接可以套标签, 但标签要套js需要放在{}中
		* 在解析显示js数组时, 会自动遍历显示
		* 把数据的数组转换为标签的数组: 
			var liArr = dataArr.map(function(item, index){
				return <li key={index}>{item}</li>
			})
	3). 注意:
	    * 标签必须有结束
	    * 标签的class属性必须改为className属性
	    * 标签的style属性值必须为: {{color:'red', width:12}}

## 1.4. 几个重要概念理解
### 1). 模块与组件
	1. 模块:
	  	理解: 向外提供特定功能的js程序, 一般就是一个js文件
	  	为什么: js代码更多更复杂
	  	作用: 复用js, 简化js的编写, 提高js运行效率
	2. 组件: 
		理解: 用来实现特定界面功能效果的代码集合(html/css/js/image)
	  	为什么: 一个界面的功能太复杂了
	  	作用: 复用编码, 简化项目界面编码, 提高运行效率
### 2). 模块化与组件化
    1. 模块化:
    	当应用的js都以模块来编写的, 这个应用就是一个模块化的应用
    2. 组件化:
    	当应用是以多组件的方式实现功能, 这上应用就是一个组件化的应用


# 2. react组件化开发
## 2.1. 基本理解和使用
	1). 自定义的标签: 组件类(函数)/标签
	2). 创建组件类
		//方式1: 无状态函数(简单组件, 推荐使用)
		function MyComponent1(props) {
			return <h1>自定义组件标题11111</h1>
		}
		//方式2: ES6类语法(复杂组件, 推荐使用)
		class MyComponent3 extends React.Component {
			render () {
			  return <h1>自定义组件标题33333</h1>
			}
		}
	3). 渲染组件标签
		ReactDOM.render(<MyComp />,  cotainerEle)
	4). ReactDOM.render()渲染组件标签的基本流程
		React内部会创建组件实例对象/调用组件函数, 得到虚拟DOM对象
		将虚拟DOM并解析为真实DOM
		插入到指定的页面元素内部