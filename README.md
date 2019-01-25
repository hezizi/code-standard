>团队项目，良好的代码习惯非常重要。**以下为本人开发项目中的代码习惯，或许对你有所帮助**

# WHY?
- **团队项目不是一个人在写代码，自己写代码爽了，也要让别人看着清晰**
- 减少bug处理，方便bug查找解决，提高开发效率，减少不必要的精力消耗
- 方便后期维护

# HOW?
#### 基本准则
- 代码缩进严格统一，要么都是`2`空格，要么都是`4`空格，禁止一切空格交叉使用导致代码不对齐，看着头痛的情况出现
- **禁止代码断层（完整代码块内出现多余的空行）**
- **注释必须写**
- 非工程化项目中`css`禁止在`html`代码中书写
- 注销无用的代码一律删掉
- 便于开发的代码，例如`console.log()`或`alert()`在开发完成后一律删掉


### HTML
- **写注释**
>如果代码量少还看的清楚，但是代码量多了，看大量没有注释的代码就没那么轻松，所以注释要写上
```html
<!-- yes -->
<!-- 下一步 -->
<div class="btn-group df-jcc">
  <button class="next-step cp">下一步</button>
  <button class="submit cp">提交</button>
  <button class="exit cp">退出</button>
</div>

<!-- 提示 -->
<div class="prompt-layer">
  <div class="title df-aic df-jcc">
    <h3>温馨提示</h3>
  </div>
  <div class="prompt-content">
    <img src="xxx.png" alt="xxx">
    <p class="ac"></p>
  </div>
</div>


<!-- no -->
<div class="btn-group df-jcc">
  <button class="next-step cp">下一步</button>
  <button class="submit cp">提交</button>
  <button class="exit cp">退出</button>
</div>
<div class="prompt-layer">
  <div class="title df-aic df-jcc">
    <h3>温馨提示</h3>
  </div>
  <div class="prompt-content">
    <img src="xxx.png" alt="xxx">
    <p class="ac"></p>
  </div>
</div>
```

- **标签合理使用**
```html
<!-- 头部 -->
<header></header>
<!-- 主内容 -->
<main></main>
<!-- 尾部 -->
<footer></footer>
<!-- 按钮 -->
<button></button>
<!-- 导航 -->
<nav></nav>
<!-- 标题 h1-h6 -->
<h3></h3>

......
```
```html
<!-- yes -->
<button class="btn"></button>

<!-- no -->
<div class="btn"></div>
```

- **标签`class`或`id`命名语义化**
> 头部：`class="header"`
>
> 尾部：`footer`
>
> 导航：`nav`
>
> 侧边栏：`sidebar`
>
> 标签页：`tab`
>
> 菜单：`menu`
>
> ......
```html
<!-- yes -->
<div class="sidebar"></div>

<!-- no -->
<div class="left"></div>
```

- **标签属性值使用`""`包裹，不要使用`''`**
```html
<!-- yes -->
<footer class="footer"></footer>

<!-- no -->
<footer class='footer'></footer>
```

- **标签属性书写顺序**
> `class`
>
> `id`  
>
> `data-*` 
>
> `src, type, href, value`
>
> `title, alt`
```html
<!-- yes -->
<a class="" id="" data-val="" href=""></a>

<!-- no -->
<a id="" href="" class="" data-val=""></a>
```

- **禁止代码断层，出现多余的空行造成代码可读性很差**
```html
<!-- yes -->
<div class="point-type df bg-white mb-20 p-20-30 border-e5">
  <div class="text-title">
    <h3></h3>
  </div>
  <nav class="flex-1">
    <ul class="clearfix"></ul>
  </nav>
</div>

<!-- very poor -->
<div class="point-type df bg-white mb-20 p-20-30 border-e5">

  <div class="text-title">
  
    <h3></h3>
  </div>
  
  <nav class="flex-1">
    <ul class="clearfix"></ul>
    
  </nav>
</div>
```

### CSS
 - **项目初始化样式`reset.css`**
```css
*{-webkit-box-sizing: content-box; -moz-box-sizing: content-box; box-sizing: content-box;}
body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,button,textarea,p,blockquote,th,td { margin:0; padding:0;}
body { color:rgba(51,51,51,0.8); font-size:14px; font-family: "Arial","Microsoft YaHei","黑体","宋体",sans-serif; }
td,th,caption { font-size:14px; }
h1, h2, h3, h4, h5, h6 { font-weight:normal; font-size:100%; }
address, caption, cite, code, dfn, em, strong, th, var { font-style:normal; font-weight:normal;}
a { color:#555; text-decoration:none; }
a:hover { text-decoration: none; }
img { border:none; vertical-align: middle}
ol,ul,li { list-style:none; }
i{font-style: normal;}
input, textarea, select, button { font:14px "Arial","Microsoft YaHei","黑体","宋体",sans-serif;}
input,button{border: none; outline: none;}
input[type=checkbox], input[type=radio]{margin: 0;}
table { border-collapse:collapse; }
html {overflow-y: scroll;}
p{margin: 0;}
.clearfix:after {content: "."; display: block; height:0; clear:both; visibility: hidden;}
.clearfix { *zoom:1; }/*公共类*/
```

- **项目自定义公用样式统一放在某一指定`css`中**（**根据自身习惯决定，以下是我编写`css`习惯**）
1. 将一些经常使用到的样式统一放到`public.css`文件中，避免重复书写

```css
/* 
 * public.css
 */
 
.fl {
    float: left;
}
.fr {
    float: right;
}
.ac {
    text-align: center;
}
.ar {
    text-align: right;
}
.df {
    display: -webkit-flex;
    display: flex;
}
.df-aic {
    display: -webkit-flex;
    display: flex;
    align-items: center;
}
.df-jcc {
    display: -webkit-flex;
    display: flex;
    justify-content: center;
}
.flex-1 {
    flex: 1;
}
.bs {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
.cp {
    cursor: pointer;
}
.bg-white {
    background-color: #fff;
}
.w100 {
    width: 100%;
}
.h100 {
    height: 100%;
}
.mb-20 {
    margin-bottom: 20px;
}

......
```
2. 其他公用样式统一放到`base.css`中
```css
/* 
 * base.css
 * 凡是多个页面会同时使用到的样式全部放入该文件中 
 */
 
body {
    background-color: #f9f9fb;
}
.container {
    width: 1280px;
    margin: auto;
    padding: 0 15px;
}

/* 头部 */
header {}

/* 主内容 */
main {}

/* 尾部 */
footer {}

/* 搜索 */
.search {}

/* checkbox */
input[type="checkbox"] {
    width: 20px;
    height: 20px;
    -webkit-appearance:none;
    background: url("xxx.png") no-repeat center;
}
input[type="checkbox"]:checked {
    background: url("xxx.png") no-repeat center;
}

......
```

- **写注释**
> 某一区块代码的样式写好注释，比如`header`，`footer`，`列表`，`搜索`，`返回顶部` ...
```css
/* yes */
/* header */
header {}

/* footer */
footer {}

/* 返回顶部 */
.go-top {}

/* no */
header {}
footer {}
.go-top {}
```
 - **`css`书写顺序**
1. 文本位置样式
`float，position，left，top，display，z-index...`
2. 文本宽高，边距
`width，height，padding，margin...`
3. 文本内容颜色，大小
`color，line-height，font-size，text-align...`
4. 文本背景，边框
`background，border...`
5. 其他
`border-radius，transform，transiton...`
```css
/* yes */
nav ul li {
    float: left;
    width: 90px;
    height: 32px;
    margin: 10px;
    padding: 0 20px 0 10px;
    font-size: 18px;
    text-align: right;
    border: 1px solid #eee;
    border-radius: 4px;
}

/* no */
nav ul li {
    margin: 10px;
    text-align: right;
    border: 1px solid #eee;
    width: 90px;
    height: 32px;
    padding: 0 20px 0 10px;
    float: left;
    font-size: 18px;
    border-radius: 4px;
}
```

- **`padding margin`写法**
```css
/* 只有一个值的情况 */
.title {
    margin-left: 10px;
}

/* 多值情况 */
/* yes */
.title {
    margin: 0 20px 10px;
}

/* no */
.title {
    margin-top: 0;
    margin-right: 20px;
    margin-left: 20px;
    margin-bottom: 10px;
}
```

- **`css`选择器两边各保留一个空格**
```css
/* yes */
label + input {
    margin-left: 10px;
}
nav > ul > li {
    margin-left: 10px;
}

/* no */
label+input {
    margin-left: 10px;
}
nav>ul>li {
    margin-left: 10px;
}
```

### JavaScript
- **写注释**
1. 整功能模块注释

	```javascript
	/**
	 *   列表筛选
	 *   @param {Array} xxxxx              保存所选省份
	 *   @param {String} xxxxxxxxxx        保存所选年代
	 *   @method xxxx                      保存所选部分，用于筛选
	 *   @method xxxx                      删除筛选中所选条件
	 * 	 ......
	 */
	```
2. 整功能模块内部小功能代码注释也需要写

	```javascript
	// 列表分页
	xxxx
	
	// 重置筛选条件
	xxxx
	```

- **驼峰命名**
```javascript
/* yes */
let searchVal = '';
function getUserInfo() {}

/* no */
let searchval = '';
function getuserinfo() {}
......
```

- **加空格让代码更优雅**
1.  `=` `==` `===` `>` `<` `%` `+` `*` `/` `,` ...

	```javascript
	/* yes */
	const name = 'yuci';
	const userArr = ['a', 'b', 'c'];
	if (i === 0) {
	    // do
	}
	for (let i = 0, len = arr.length; i < len; i++) {
	    // do
	}
	
	/* no */
	const name='yuci';
	const userArr=['a','b','c'];
	if(i===0){
	    // do
	}
	for(let i=0,len=arr.length;i<len;i++){
	    // do
	}
	......
	```

2. `if` `else` `for` `while` `switch` `try` `catch` `function` ...

	```javascript
	/* yes */
	if (i === 0) {
        // do
	} else {
	    // do
	}
	try {
	    // do
	} catch {
	    // do
	}
	switch (dataSort) {
	    // do
	}
	for (let i = 0, len = arr.length; i < len; i++) {
	    // do
	}
	const fn = username => {
	    // do
	}
	function fn() {
        // do
	}
	
	/* no */
	if(i===0){
	    // do
	}else{
        // do
	}
	for(let i=0,len=arr.length;i<len;i++){
	    // do
	}
	switch(dataSort){
	    // do
	}
	const fn=username=>{
	    // do
	}
	function fn(){
	    // do
	}
	......
	```

3. 对象 `:` 右边加上一个空格

	```javascript
	/* yes */
	const user = {
        name: 'xxx',
        age: 'xxx'
	}
	this.state = {
  	    username: ''
	}
	this.setState({
  	    username: 'yucihent'
	})
	
	/* no */
	const user = {
        name:'xxx',
        age:'xxx'
	}
	......
	```
- **禁止代码断层（可读性非常差）**
```javascript
/* yes */
/**
 * fetch请求封装
 */
let fetchData = async (url, method, data) => {
    let options;
    let dataStr = '';
    const headers = {
      'Accept': 'application/json',
      'Content-Type': 'application/x-www-form-urlencoded'
    };
    // get 请求
    if (method === 'get') {
        if (typeof data === 'object') {
            Object.keys(data).forEach(key => {
                dataStr += `${key}=${data[key]}&`
            });
            if (dataStr) {
                dataStr = dataStr.substring(0, dataStr.length - 1)
            };
            url = `${url}?${dataStr}`;
        }
        options = {
            method: 'GET',
            headers,
        }
    } else {
        let formData = new FormData();
        for (let key in data) {
            formData.append(key, data[key])
        }
        options = {
            method: 'POST',
            body: formData
        }
    }
    let response = await fetch(url, options);
    let res = await response.json();
    return res;
}

/* very poor very poor very poor */
let fetchData = async (url, method, data) => {
    let options;
    let dataStr = '';
    const headers = {
      'Accept': 'application/json',
      'Content-Type': 'application/x-www-form-urlencoded'
    };
    // get 请求
    if (method === 'get') {
        if (typeof data === 'object') {
            Object.keys(data).forEach(key => {
                dataStr += `${key}=${data[key]}&`
            });
            
            if (dataStr) {
                dataStr = dataStr.substring(0, dataStr.length - 1)
                
            };
            url = `${url}?${dataStr}`;

        }
        options = {
            method: 'GET',
            headers,
        }
    } else {
        let formData = new FormData();
        
        for (let key in data) {
            formData.append(key, data[key])
            
        }
        options = {
            method: 'POST',
            body: formData
        }


    }
    
    let response = await fetch(url, options);
    let res = await response.json();
    return res;


}
```

- **一行代码不要过多**
```javascript
/* yes */
import {
    List,
    InputItem,
    WingBlank,
    WhiteSpace,
    Button,
    Radio,
    Toast
} from 'antd-mobile'

/* no */
import { List, InputItem, WingBlank, WhiteSpace, Button, Radio, Toast } from 'antd-mobile'
```

- **使用`''`，而非`""`**
```javascript
/* yes */
import HelloWorld from './components/HelloWorld'
methods: {
    delItem(index) {
    	this.$emit('delItem', index)
    }
}

/* no */
import HelloWorld from "./components/HelloWorld"
methods: {
    delItem(index) {
    	this.$emit("delItem", index)
    }
}
```

- **简洁清晰**
1. 模板字符串替代 `++` 字符串拼接
2. 解构赋值

	```javascript
	/* yes */
	this.state = {
        name: 'xxx',
        age: 'xxx'
	}
	const { name, age } = this.state;
	
	/* no */
	const name = this.state.name;
	const age = this.state.age;
	```
3. 属性名属性值相同简写

	```javascript
	/* yes */
	components: {
        Header,
        Footer
	}
	
	/* no */
	components: {
        Header: Header,
        Footer: Footer
	}
	```
4. 函数
	
	```javascript
	/* yes */
	methods: {
        delItem(index) {
        	this.$emit('delItem', index)
        }
	}
	
	/* no */
	methods: {
        delItem: function(index) {
        	this.$emit('delItem', index)
        }
	}
	```

	......

#### 结束语
> **上述内容为我在项目中遇到过的代码规范问题以及本人编码习惯的部分总结，不可能适用每位开发者，但大部分编码风格应该是合大众口味，希望能帮助到大家**

#### 唠叨一句
> 团队合作的一个黄金定则：**你看别人的代码就像看自己代码一样**，良好的代码习惯 **非常重要 非常重要 非常重要**
