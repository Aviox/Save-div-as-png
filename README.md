Works in Firefox

```html
<script type="text/javascript" src="html2canvas.js"></script>
<script type="text/javascript" src="jquery-1.9.1.min.js"></script>
<script type="text/javascript" src="base64.js"></script>
<script type="text/javascript" src="canvas2image.js"></script>
```

```js

// scripts injection

var sc=document.createElement('script');
sc.src="http://code.jquery.com/jquery-1.9.1.js";
document.getElementsByTagName('head')[0].appendChild(sc);

sc=document.createElement('script');
sc.src="https://raw.github.com/Aviox/Save-div-as-png/master/base64.js";
document.getElementsByTagName('head')[0].appendChild(sc);

sc=document.createElement('script');
sc.src="https://raw.github.com/Aviox/Save-div-as-png/master/canvas2image.js";
document.getElementsByTagName('head')[0].appendChild(sc);

sc=document.createElement('script');
sc.src="https://raw.github.com/Aviox/Save-div-as-png/master/html2canvas.js";
document.getElementsByTagName('head')[0].appendChild(sc);

$().jquery;

// Facebook posts scroll down

var interval = setInterval(function () { 
  //document.getElementById('group_mall_222256717910544').lastChild.scrollIntoView(); 
  document.getElementById('pagelet_group_mall').firstChild.firstChild.lastChild.scrollIntoView();
}, 2000);

// expand Facebook comments

$("#pagelet_group_mall span").filter(function () { 
  return /Zobacz więcej komentarzy/.test($(this).text())
}).click();

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

// struktura:  div z id pagelet_group_mall > zaglebiony div (nieistotny) > div z postami > divy "dzieci" - posty

$("#pagelet_group_mall > div > div > div").each(function(index) {
  //console.log($(this).attr("id"))
  saveImage($(this));
});
```
