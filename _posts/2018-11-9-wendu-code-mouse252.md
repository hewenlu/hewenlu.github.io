---
layout: post
title: '鼠标点击文字效果'
date: 2018-11-10
author: temperature
color: '#FF8F2A'
cover: '/assets/posts/mouse2.png'
tags: javascript jquery html css 
---

### 文字效果也存一下吧，虽然不太好看，但是252特别，不定哪天心血来潮换上。只需要引入jq库，js加入以下代码或者新建js文件引入,鼠标点击文字效果就出现了！ 


 ```javascript
 
 var getRandomColor = function() {
        return '#' +
            (function(color) {
                return(color += '0123456789abcdef' [Math.floor(Math.random() * 16)]) &&
                    (color.length == 6) ? color : arguments.callee(color);
            })('');
    }
    var a_idx = 0;
    jQuery(document).ready(function($) {
        $("body").click(function(e) {

            var a = new Array("252", "爱生活");
            var $i = $("<span/>").text(a[a_idx]);
            a_idx = (a_idx + 1) % a.length;
            var x = e.pageX,
                y = e.pageY;

            $i.css({
                "z-index": 999,
                "top": y - 20,
                "left": x,
                "position": "absolute",
                "font-weight": "bold",
                "color": getRandomColor,
                "font-family": "Pacifico"
            });
            $("body").append($i);
            $i.animate({
                    "top": y - 180,
                    "opacity": 0
                },
                1500,
                function() {
                    $i.remove();
                });
        });
    });

```        
  
