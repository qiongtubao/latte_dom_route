latte_dom_route
===========

#latte-route 指令
##初阶

html:
```html
	<div latte-controller="routeDemo">
		<div latte-route="index"  latte-data="route">
    	</div>
    </div>
```
js:
```js
	var latte_dom = latte.require("latte_dom");
	var data = {
		//latte-data数据
		route: {
			//latte-route设定选择属性index
			index:"a",
    		a: {
    			url: "./a.html",
    			//设置a.html下数据集
    			data: {
    				me: "dong"
    			}
    		},
    		b: {
    			url: "./b.html",
    			data: {

    			}
    		} 
		}
	};
	var box = latte_dom.define("routeDemo", data);
```
a.html
```html
	<div>
		hello a is {{me}}
	</div>
```
b.html:
```html
	<div>
		hello is b
	</div>
```

##进阶
html:
```html
	<div latte-controller="routeDemo">
		<div latte-route="index"  latte-data="route">
    	</div>
    </div>
```
js:
```js
	var latte_dom = latte.require("latte_dom");
	var data = {
		//latte-data数据
		route: {
			//latte-route设定选择属性index
			index:"a",
			end: function(to, next) {
				//只有调用了next 会执行to  route里面如果有start就执行
			},
			start: function(from, next) {
				//只有调用了next 才会dom生命周期结束以及加载新dom
			},
    		a: {
    			url: "./a.html",
    			//设置a.html下数据集
    			data: {
    				me: "dong"
    			}
    		},
    		b: {
    			url: "./b.html",
    			data: {

    			}
    		} 
		}
	};
	var box = latte_dom.define("routeDemo", data);
```
a.html
```html
	<div>
		hello a is {{me}}
	</div>
```
b.html:
```html
	<div>
		hello is b
	</div>
```
