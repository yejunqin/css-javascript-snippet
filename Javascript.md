# Javascript

---

**window.onload**
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

