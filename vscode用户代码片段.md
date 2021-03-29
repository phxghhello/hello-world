vscode用户代码片段

```json
{
	// Place your snippets for javascript here. Each snippet is defined under a snippet name and has a prefix, body and 
	// description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
	// same ids are connected.
	// Example:
	// "Print to console": {
	// 	"prefix": "log",
	// 	"body": [
	// 		"console.log('$1');",
	// 		"$2"
	// 	],
	// 	"description": "Log output to console"
	// }
	"Print to console": {
		"prefix": "lg",
		"body": [
			"console.log($0);"
		],
		"description": "Log output to console"
	},
	"alert": {
		"prefix": "al",
		"body": [
			"alert('$0');"
		],
		"description": "alert"
	},
	"document.write": {
		"prefix": "dw",
		"body": [
			"document.write('$0');"
		],
		"description": "document.write"
	},
	"prompt": {
		"prefix": "po",
		"body": [
			"prompt('$0');"
		],
		"description": "prompt"
	},
	"confirm": {
		"prefix": "cf",
		"body": [
			"confirm('$0');"
		],
		"description": "confirm"
	},
	"getElementById": {
		"prefix": "dgi",
		"body": [
			"document.getElementById('$0');"
		],
		"description": "getElementById"
	},
	"getElementsByTagName": {
		"prefix": "dgtn",
		"body": [
			"document.getElementsByTagName('$0');"
		],
		"description": "getElementsByTagName"
	},
	"getElementsByClassName": {
		"prefix": "dgcn",
		"body": [
			"document.getElementsByClassName('$0');"
		],
		"description": "getElementsByClassName"
	},
	"querySelector": {
		"prefix": "dqs",
		"body": [
			"document.querySelector('$0');"
		],
		"description": "querySelector"
	},
	"querySelectorAll": {
		"prefix": "dqsa",
		"body": [
			"document.querySelectorAll('$0');"
		],
		"description": "querySelectorAll"
	},
	"do-while": {
		"prefix": "dow",
		"body": [
			"do {",
			"\t$0",
			"} while();"
		],
		"description": "do-while"
	},
	"for": {
		"prefix": "fr",
		"body": [
			"for($1){",
			"\t$0",
			"}"
		],
		"description": "for"
	},
	"new Array": {
		"prefix": "newa",
		"body": [
			"new Array($0);"
		],
		"description": "new Array"
	},
	"arr3": {
		"prefix": "a3",
		"body": [
			"var arr = [1,2,3];"
		],
		"description": "arr3"
	},
	"arr5": {
		"prefix": "a5",
		"body": [
			"var arr = [1,2,3,4,5];"
		],
		"description": "arr5"
	},
	"arr10": {
		"prefix": "a10",
		"body": [
			"var arr = [1,2,3,4,5,6,7,8,9,10];"
		],
		"description": "arr10"
	},
	"forarr": {
		"prefix": "forarr",
		"body": [
			"for(let i = 0;i < $1.length;i++) {",
			"\t$0",
			"}"
		],
		"description": "arr10"
	},
	"optc": {
		"prefix": "optc",
		"body": [
			"Object.prototype.toString.call($0);"
		],
		"description": "optc"
	},
	"consoledir": {
		"prefix": "dr",
		"body": [
			"console.dir($0);"
		],
		"description": "Log output to console.dir"
	},
	"yulan tupian": {
		"prefix": "ajax_yulan",
		"body": [
			"//1.给file表单元素注册onchange事件",
			"$('file表单').change(function () {",
			"\t//1.2 获取用户选择的图片",
			"\tvar file = this.files[0];",
			"\t//1.3 将文件转为src路径",
			"\tvar url = URL.createObjectURL(file);",
			"\t//1.4 将url路径赋值给img标签的src",
			"\t$('img元素').attr('src', url);",
			"});"
		],
		"description": "图片预览固定四个步骤"
	},
	"comment for function": {
		"prefix": "///",
		"body": [
			"/**",
			"* @description:",
			"* @param {type} ",
			"* @return: ",
			"*/",
		],
		"description": "函数标准注释快捷键"
	},
	"jquery to ajax": {
		"prefix": "ajax",
		"body": [
			"$.ajax({",
			"\turl:'',",
			"\ttype:'get',",
			"\tdataType:'json',",
			"\tdata:'',",
			"\tsuccess: function(backData){",
			"",
			"\t}",
			"});"
		],
		"description": "ajax请求"
	},
	"get for XMLHTTPRequest": {
		"prefix": "ajax1",
		"body": [
			"//(1).实例化ajax对象",
			"var xhr = new XMLHttpRequest();",
			"//(2).设置请求方法和地址",
			"//get请求的数据直接添加在url的后面 格式是 url?key=value",
			"xhr.open('get', '接口url');",
			"//(3).发送请求",
			"xhr.send();",
			"//(4).注册回调函数",
			"xhr.onload = function() {",
			"\tconsole.log(xhr.responseText)",
			"};",
		],
		"description": "get-原生XMLHTTPRequest实现ajax"
	},
	"post for XMLHTTPRequest": {
		"prefix": "ajax2",
		"body": [
			"//(1).实例化ajax对象",
			"var xhr = new XMLHttpRequest();",
			"//(2).设置请求方法和地址",
			"xhr.open('post', '接口url');",
			"//(3).设置请求头（post请求才需要设置）",
			"xhr.setRequestHeader('Content-type','application/x-www-form-urlencoded');",
			"//(4).发送请求 ： 参数格式  'key=value' ",
			"xhr.send('key=value');",
			"//(5).注册回调函数",
			"xhr.onload = function () {",
			"\tconsole.log(xhr.responseText);",
			"};"
		],
		"description": "post-原生XMLHTTPRequest实现ajax"
	},
	"file to ajax": {
		"prefix": "ajax-file",
		"body": [
			"$('提交按钮').on('click',function(e){",
			"\t//禁用表单默认提交事件",
			"\te.preventDefault();",
			"\t//创建FormData对象：参数是表单dom对象",
			"\tvar fd = new FormData('form表单DOM对象')",
			"\t$.ajax({",
			"\t\turl:'',",
			"\t\ttype:'post',",
			"\t\tdataType:'json',",
			"\t\tdata:fd,",
			"\t\tcontentType: false,",
			"\t\tprocessData: false,",
			"\t\tsuccess: function(backData){",
			"\t\t}",
			"\t});",
			"});"
		],
		"description": "表单提交ajax请求"
	},
	"express-server": {
		"prefix": "express",
		"body": [
			"//1.导入模块",
			"const express = require('express');",
			"//2.创建服务器",
			"let app = express();",
			"//3.开启服务器",
			"app.listen(3000,()=>{",
			"console.log('success');",
			"});"
		],
		"description": "快速搭建express服务器"
	},
	"需求分析": {
		"prefix": "silu1",
		"body": [
			"/*",
			"1.分析需求(交互)：",
			"2.思路分析（事件三要素）",
			"\t获取元素：事件源：",
			"\t注册事件：事件类型",
			"\t事件处理：",
			"*/",
		],
		"description": "分析需求"
	},
	"遍历对象": {
		"prefix": "forin1",
		"body": [
			"for(var key in obj){",
			"\tvar value = obj[key]",
			"}",
		],
		"description": "遍历对象快捷语法"
	},
	"axios": {
		"prefix": "axios",
		"body": [
			"axios({",
			"\turl:'请求路径',",
			"\tmethod:'get',",
			"\tdata: { 'post请求参数'},",
			"\tparams: { 'get请求参数'}",
			"}).then(res=>{",
			"\t//成功回调",
			"\tconsole.log(res)",
			"});",
		],
		"description": "axios请求"
	},
	"instance for Vue": {
		"prefix": "newVue",
		"body": [
			"new Vue({",
			"    el:'#app',",
			"    data:{",
			"    },",
			"    methods:{",
			"    },",
			"});",
		],
		"description": "vue基本实例"
	},
	"react_render": {
		"prefix": "readom",
		"body": [
			"ReactDOM.render(<$1 />,document.getElementById(\"root\"));"
		],
		"description": "react render"
	}
}
```

