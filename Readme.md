latte_dom2
===========

#Tag

##文本显示绑定  latte-html 指令 

html:
```html
	<div latte-controller="routeDemo">
		<div latte-route="">
        	<div latte-html="{{a}} {{b}}"></div>
    	</div>
    </div>
```
js:
```js
	var latte_dom = latte.require("latte_dom");
	var data = {
		route: {
			select: ""
		}
	};
	var box = latte_dom.define("routeDemo", data);
```

