Works in Firefox

```html
<script type="text/javascript" src="html2canvas.js"></script>
<script type="text/javascript" src="jquery-1.9.1.min.js"></script>
<script type="text/javascript" src="base64.js"></script>
<script type="text/javascript" src="canvas2image.js"></script>
```

```js

// jQuery injection

var sc=document.createElement('script');
sc.src="http://code.jquery.com/jquery-1.9.1.js";
document.getElementsByTagName('head')[0].appendChild(sc);

// Facebook scroll down

var interval = setInterval(function () { 
  document.getElementById('group_mall_222256717910544').lastChild.scrollIntoView(); 
}, 2000);

// proper function

var saveImage = function (div) {
	html2canvas($(div)[0], {
		onrendered: function(canvas) {
			$(div).html(canvas);
			//Canvas2Image.saveAsPNG($(div).find("canvas").first()[0]);
		}
	
	});
};
```


Example:

```js
$("#group_mall_230539737076122 > div").each(function(index) {
  //console.log($(this).attr("id"))
  saveImage($(this));
});
```
