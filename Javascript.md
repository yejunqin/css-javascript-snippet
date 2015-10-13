# Javascript

---

### window.onload
```javascript
function windowOnload (fn){
	var oldload;
	if(window.onload){
		oldload = window.onload;
		window.onload = function(){
			oldload();
			fn();
		}
	}
	else{
		window.onload = fn;
	}
}
```

### 获取url参数
``` javascript
$.getUrlParam = function(name) {
	var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)");
	var r = window.location.search.substr(1).match(reg);
	if (r != null) return unescape(r[2]); return null;
}
```

### 判断手机号
``` javascript
function isMobile(str) {
	var reg = /^(1)[0-9]{10}$/;
	return reg.test(str);
}
```

### 本地存储
``` javascript
var storage = {
	set: function(key, value) {					//保存数据至本地
		if(typeof(localStorage)=="undefined") {	
			return;
		}
		else {
			try {
				localStorage.setItem(key, value);
			}
			catch (e) {
				alert("Error:"+e);
			}
		}
	},
	get: function(key) {						//从本地获取保存数据
		if(typeof(localStorage)=="undefined") {
			return false;
		}
		else {
			try {
				return localStorage.getItem(key);
			}
			catch (e) {
				return false;
			}
		}
	}
};
```
### 判断数组
``` javascript
var isArray = function(value){
	return Object.prototype.toString.apply(value) === '[object Array]';
}
```