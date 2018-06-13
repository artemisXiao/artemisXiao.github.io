### js
```
/***
 * ================================================公告滚动
 */
//document.getElementById()的最简化应用
function get_ele(element) {
    if (arguments.length > 1) {
        for (var i = 0, length = arguments.length, elements = []; i < length; i++) {
            elements.push($(arguments[i]));
        }
        return elements;
    }
    if (typeof element == "string") {
        return document.getElementById(element);
    } else {
        return element;
    }
}
//类创建函数
var Class = {
    create: function () {
        return function () {
            this.initialize.apply(this, arguments);
        }
    }
}
//对象属性方法扩展
Function.prototype.bind = function (object) {
    var method = this;
    return function () {
        method.apply(object, arguments);
    }
}
var Scroll = Class.create();
Scroll.prototype = {
    //第一个参数定义要滚动的区域,第二个参数定义每次滚动的高度
    initialize: function (element, height, delay) {
        this.element = get_ele(element);
        this.element.innerHTML += this.element.innerHTML;
        this.height = height;
        this.delay = delay * 1000;
        this.maxHeight = this.element.scrollHeight / 2;
        this.counter = 0;
        this.scroll();
        this.timer = "";
        this.element.onmouseover = this.stop.bind(this);
        this.element.onmouseout = function () {
            this.timer = setTimeout(this.scroll.bind(this), 1000);
        }.bind(this);
    },
    scroll: function () {
        if (this.element.scrollTop < this.maxHeight) {
            this.element.scrollTop++;
            this.counter++;
        } else {
            this.element.scrollTop = 0;
            this.counter = 0;
        }

        if (this.counter < this.height) {
            this.timer = setTimeout(this.scroll.bind(this), 5);
        } else {
            this.counter = 0;
            this.timer = setTimeout(this.scroll.bind(this), this.delay);
        }
    },
    stop: function () {
        clearTimeout(this.timer);
    }
}
/***
 * ================================================公告滚动
 */


//启动轮播 new Scroll(ElementId, height(px) ,delay(s))
new Scroll('gonggao_board', 22, 5);
```