---
layout: post
title: 2048小游戏demo
description: "2048小游戏demo"
tags: [css js]
author: DANIEL
---

<style>
p.game_title{
    font-size: 40px;
    font-weight: bold;
    font-family: Arial;
    margin: 0 auto;
    width: 480px;
    padding-top: 10px;
    /*background-color: lightpink;*/
}
#gridPanel{
    width: 480px;
    height: 480px;
    margin: 0 auto;
    background-color: #bbada0;
    border-radius: 20px;
    position:relative;
}
#gameOver{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: none;
    /*background-color: #f00;*/
}
#gameOver>div{
    width: 100%;
    height: 100%;
    background-color: #555;
    opacity: 0.5;
}
#gameOver>p{
    position: absolute;
    width: 300px;
    height: 200px;
    top: 50%;
    left: 50%;
    background-color: #ffffff;
    margin-left: -150px;
    margin-top:-100px ;
    text-align: center;
    line-height: 1.5em;
    border-radius: 30px;
    border: 1px solid #edef72;
}
#gameOver .btn{
    cursor: pointer;
    background-color:#9f8d77;
    color: #ffffff;
    padding: 10px;
    border-radius: 30px;
}
.grid,.cell{
    width: 100px;
    height: 100px;
    border-radius: 10px;
}
.grid{
    background-color: #ccc0b3;
    float: left;
    margin: 16px 0 0 16px;
}
.cell{
    float: left;
    position: absolute;
    font-size: 60px;
    text-align: center;
    line-height: 100px;
    color: #ffffff;
    background-color: #ccc0b3;;
}
[id^="c0"]{top:16px;}
[id^="c1"]{top:132px;}
[id^="c2"]{top:248px;}
[id^="c3"]{top:364px;}
[id^="c4"]{top:480px;}
[id^="c5"]{top:596px;}
[id$="0"]{left: 16px;}
[id$="1"]{left: 132px;}
[id$="2"]{left: 248px;}
[id$="3"]{left: 364px;}
[id$="4"]{left: 480px;}
[id$="5"]{left: 596px;}

.n2{background-color:#eee3da ;}
.n4{background-color:#ede0c8 ;}
.n8{background-color:#f2b179 ;}
.n16{background-color:#f59563 ;}
.n32{background-color: #f67c5f;}
.n64{background-color: #f6513b;}
.n128{background-color: #edcf72;
    font-size: 40px;}
.n256{background-color: #edcc61;
    font-size: 40px;}
.n512{background-color: #9c0;
    font-size: 40px;}
.n1024{background-color: #33b5e5;
    font-size: 40px;}
.n2048{background-color:#09c ;
    font-size: 40px;}
.n4096{background-color:#a6c ;
    font-size: 40px;}
.n8192{background-color:#93c ;
    font-size: 40px;}
/*.n16384{background-color: ;}*/
/*.n32768{background-color: ;}*/
.n2,.n4{color: #776e65}

</style>

<p>
	TOP:<span id="top">0</span><br>
</p>
<p>
	SCORE:<span id="score">0</span><br>
</p>
<div id="gridPanel"></div>
<div id="gameOver">
	<div></div>
	<p class="game_title">
		Game Over<br/>
		Score:<span id="fScore"></span>
		<br/>
		<a class="btn" onclick="game.start()">
			Try Again
		</a>
	</p>

</div>

<script type="text/javascript">
/**
 * Created by Administrator on 2016/11/3.
 */

function setCookie(name,value){
    var now = new Date();
    now.setMonth(now.getMonth()+1);
    document.cookie = name+"="+value+";expires="+now.toGMTString();
}
//setCookie("top",999998)
function getCookie(name){
    var cookies = document.cookie.split(";");
//    console.log(cookies);
    for(var i=0;i<cookies.length;i++){
        if(cookies[i].startsWith(name)){
//            console.log(cookies[i].split("=")[1]);
            return cookies[i].split("=")[1];
        }
    }
}



var game = {
    //二维数组 用于保存游戏数据
    data:null,
    //总行数
    RN:4,
    //总列数
    CN:4,
    //历史最高分
    top:0,
    //当前分数
    score:0,
    //每一个小格子的尺寸
    CSIZE:100,
    //每一个小方块的外间距
    MARGINE:16,
    //添加游戏当前状态：0，游戏结束  1，游戏运行
    state:1,
    RUNNING:1,
    GAMEOVER:0,
    HISTORY:[],
    SNUM:0,
    //初始化游戏状态方法
    init:function(){
        for(var r = 0,arr=[];r<this.RN;r++){
            for(var c=0;c<this.CN;c++){
                arr.push(""+r+c);
            }
        }
        //遍历结束
        //将arr按照'" class="grid"></div><div id="g'
        //拼接成字符串 保存到变量html
        var html = arr.join('" class="grid"></div><div id="g');
        html = '<div id="g'+html+'" class="grid"></div>'
//        console.log(html);
        //替换html中所有的/g(\d{2})|grid/g 替换成一个方法
        var htmlc = html.replace(/g(\d{2})|grid/g,function(kword,$1){
//            console.log($1);
            return kword=="grid"?"cell":"c"+$1;
        });
        var panel = document.getElementById("gridPanel");
        console.log(panel);
        panel.innerHTML = html+htmlc;
        var width =this.CN*this.CSIZE+(this.CN+1)*this.MARGINE;
        var height =this.RN*this.CSIZE+(this.RN+1)*this.MARGINE;
        panel.style.width = width+"px";
        panel.style.height = height+"px";
    },
    //声明方法用于游戏开始
    start:function(){
        //清空当前分数 并从浏览器中获取top的值
        this.score = 0;
        this.top = getCookie("top")==undefined?"0":getCookie("top");
        //初始化当前游戏
        this.init();
        //重置游戏状态为running
        this.state = this.RUNNING;
        this.data = [];
        for(var r=0;r<this.RN;r++){
            this.data[r] = [];
            for(var c=0;c<this.CN;c++){
                //[[0,0,0,0],[0,0,0,0],[0,0,0,0],[0,0,0,0]]
                this.data[r][c] = 0;
            }
        }
//        console.log(this.data);
        //调用方法 randomNum()
        this.randomNum();
        this.randomNum();
//        console.log(this.data);

        //显示到id为gridPanel下的子div上upDataView()
        this.upDateView();
        this.HISTORY[this.SNUM] = this.data;

        //响应键盘事件
        document.onkeydown = function(e){
            if(e.keyCode==37){
//                console.log("左");
                this.moveLeft();

            }else if(e.keyCode==38){
//                console.log("上");
                this.moveUp();
            }else if(e.keyCode==39){
//                console.log("右");
                this.moveRight();
            }else if(e.keyCode==40){
//                console.log("下");
                this.moveDown();
            }else if(e.keyCode==90){
                this.back();
            }
        }.bind(this);//绑定到当前game上
        this.upDateView();
    },
    //随机生成一个数字 放到data的二维数组中元素为0的位置上
    randomNum:function(){

        while(true){
            var r = Math.floor(Math.random()*this.RN);
            var c = Math.floor(Math.random()*this.CN);
//            console.log(r,c);
            if(this.data[r][c]==0){
                this.data[r][c] = Math.random()<0.5?2:4;
                break;
            }
        }
    },
    //把data中的数据更新到页面的div中
    upDateView:function(){
        for(var r=0;r<this.RN;r++){
            for(var c=0;c<this.CN;c++){
                var panel1 = document.getElementById("c"+r+c);
                if(this.data[r][c]!=0){
                    panel1.innerHTML = this.data[r][c];
                    panel1.className = "cell n"+this.data[r][c];
                }else{
                    panel1.innerHTML = "";
                    panel1.className = "cell";
                }

            }
        }
        //获取当前对象的属性score 并显示在浏览器中
        document.getElementById("score").innerHTML = this.score;
//        console.log(this.score);
        //把当前对象的属性top 显示在浏览器中
        document.getElementById("top").innerHTML = this.top;
        //判断当前game的状态，如果状态为GAMEOVER 切换显示
        if(this.state==this.GAMEOVER){
            //找到id为gameOver的元素 设置其显示
            document.getElementById("gameOver").style.display = "block";
            document.getElementById("fScore").innerHTML = this.score;
            if(this.score>this.top){
                    setCookie("top",this.score);
                    this.top = getCookie("top")==undefined?"0":getCookie("top")
             }
         }else{
                document.getElementById("gameOver").style.display = "none";
        }
    },
     isGameOver:function(){
        for(var r=0;r<this.RN;r++){
            for(var c=0;c<this.CN;c++){
                if(this.data[r][c]==0){
                    return false
                }
                if(c!=this.CN-1&&this.data[r][c]==this.data[r][c+1]){
                        return false;
                }else
                if(r!=this.RN-1&&this.data[r][c]==this.data[r+1][c]){
                        return false
                }
            }
        }
        return true;
    },
    //向左移动所有的行
    moveLeft:function(){
        //向左移动之前 把data存入before中
        var before = String(this.data);
        //移动每一行
        for(var r=0;r<this.RN;r++){
            this.moveLeftInRow(r);
        }
        //把移动后的data存入after
        var after = String(this.data);
        if(before!=after){
            this.randomNum();
            if(this.isGameOver()){
                this.state = this.GAMEOVER;
            }
        }
        this.upDateView();
    },
    moveLeftInRow:function(r){
        for(var c=0;c<this.CN-1;c++){
            //判断此时此方块后面的每一个小方块是否为0
            var nextc = this.getNextInRow(r,c);
            if(nextc==-1){
                break;
            }else{
                if(this.data[r][c]==0){
                    this.data[r][c] = this.data[r][nextc];
                    this.data[r][nextc] = 0;
                    c--;
                }else if(this.data[r][c]==this.data[r][nextc]){
                    this.score += (this.data[r][c] *= 2);
                    this.data[r][nextc] = 0;
                }
            }
        }
    },
    //查找data中r行c列后下一个不为零的位置
    getNextInRow:function(r,c){
        for(var nextc=c+1;nextc<this.CN;nextc++){
            if (this.data[r][nextc]!=0){
                return nextc;
            }
        }
        return -1;
    },
    moveUp:function(){
        var before = String(this.data);
        for(var c=0;c<this.CN;c++){
            this.moveUpInCol(c);
        }
        var after = String(this.data);
        if(before!=after){
            this.randomNum();
            if(this.isGameOver()){
                this.state = this.GAMEOVER;
            }
        }
        this.upDateView();
    },
    moveUpInCol:function(c){
        for(var r=0;r<this.RN-1;r++){
            var nextr = this.getNextInCol(r,c);
            if(nextr==-1){
                break;
            }else{
                if(this.data[r][c]==0){
                    this.data[r][c] = this.data[nextr][c];
                    this.data[nextr][c] = 0;
                    r--;
                }else
                if(this.data[r][c]==this.data[nextr][c]){
//                    console.log(this.data[r][c]);
//                    console.log(this.data);
                    this.score += (this.data[r][c] *= 2);
                    this.data[nextr][c] = 0;
                }
            }
        }
    },
    getNextInCol:function(r,c){
        for(var nextr=r+1;nextr<this.RN;nextr++){
            if(this.data[nextr][c]!=0){
                return nextr;
            }
        }
        return -1;
    },
    moveRight:function(){
        var before = String(this.data);
        for(var r=0;r<this.RN;r++){
            this.moveRightInRow(r);
        }
        var after = String(this.data);
        if(before!=after){
            this.randomNum();
            if(this.isGameOver()){
                this.state = this.GAMEOVER;
            }
        }
        this.upDateView();
    },
    moveRightInRow:function(r){
        for(var c=this.CN-1;c>=0;c--){
            var nextc = this.getNextInRow1(r,c);
            if(nextc==-1){
                break;
            }else{
                if(this.data[r][c]==0){
                    this.data[r][c] = this.data[r][nextc];
                    this.data[r][nextc] = 0;
                    c++;
                }else
                if(this.data[r][c]==this.data[r][nextc]){
                    this.score += (this.data[r][c] *= 2);
                    this.data[r][nextc] = 0;
                }
            }
        }
    },
    getNextInRow1:function(r,c){
        for(var nextc=c-1;nextc>=0;nextc--){
            if(this.data[r][nextc]!=0){
                return nextc;
            }
        }
        return -1;
    },
    moveDown:function(){
        var before = String(this.data);
        for(var c=0;c<this.CN;c++){
            this.moveDownInCol(c);
        }
        var after = String(this.data);
        if(before!=after){
            this.randomNum();
            if(this.isGameOver()){
                this.state = this.GAMEOVER;
            }
        }
        this.upDateView();
    },
    moveDownInCol:function(c){
        for(var r=this.RN-1;r>=0;r--){
            var nextr = this.getNextInCol1(r,c);
            if(nextr==-1){
                break;
            }else{
                if(this.data[r][c]==0){
                    this.data[r][c] = this.data[nextr][c];
                    this.data[nextr][c] = 0;
                    r++;
                }else
                if(this.data[r][c]==this.data[nextr][c]){
                    this.score += (this.data[r][c] *= 2);
                    this.data[nextr][c] = 0;
                }
            }
        }
    },
    getNextInCol1:function(r,c){
        for(var nextr=r-1;nextr>=0;nextr--){
            if(this.data[nextr][c]!=0){
                return nextr;
            }
        }
        return -1;
    },
    back:function(){
        this.SNUM--;
        this.data = this.HISTORY[this.SNUM];
        console.log(String(this.HISTORY),this.SNUM);

        this.upDateView();
    }
}


game.start();























































/*
function setCookie(name,value){
    var now = new Date();
    now.setDate(now.getMonth()+1);
    document.cookie = name+":"+value+";expires="+now.toGMTString;
}
function getCookie(name){
    var cookies = document.cookie.split(";");
    for(var i=0;i<cookies.length;i++){
        if(cookies[i].startsWith(name)){
            return cookies[i].split("=")[1];
        }
    }
}


var game = {
    //二维数组 用于保存游戏数据
    data:null,
    //总行数
    RN:4,
    //总列数
    CN:4,
    //历史最高分
    top:0,
    //当前分数
    score:0,
    //每一个小格子的尺寸
    CSIZE:100,
    //每一个小方块的外间距
    MARGINE:16,
    //添加游戏当前状态：0，游戏结束  1，游戏运行
    state:1,
    RUNNING:1,
    GAMEOVER:0,
    //初始化游戏状态方法
    init:function(){
        for(var r = 0,arr=[];r<this.RN;r++){
            for(var c=0;c<this.CN;c++){
                arr.push(""+r+c);
            }
        }
        //遍历结束
        //将arr按照'" class="grid"></div><div id="g'
        //拼接成字符串 保存到变量html
        var html = arr.join('" class="grid"></div><div id="g');
        html = '<div id="g'+html+'" class="grid"></div>'
//        console.log(html);
        //替换html中所有的/g(\d{2})|grid/g 替换成一个方法
        var htmlc = html.replace(/g(\d{2})|grid/g,function(kword,$1){
            console.log(typeof (kword));
//            console.log($1);
            return kword=="grid"?"cell":"c"+$1;
        });
        console.log(htmlc);
        var panel = document.getElementById("gridPanel");
        panel.innerHTML = html+htmlc;
        console.log(panel);
        var width =this.RN*this.CSIZE+(this.RN+1)*this.MARGINE;
        var height =this.CN*this.CSIZE+(this.CN+1)*this.MARGINE;
        panel.style.width = width+"px";
        panel.style.height = height+"px";
    },
    //声明方法用于游戏开始
    start:function(){
        //清空当前分数 并从浏览器中获取top的值
        this.score = 0;
        this.top = getCookie("top");
        //初始化当前游戏
        this.init();
        //重置游戏状态为running
        this.state = this.RUNNING;
        this.data = [];
        for(var r=0;r<this.RN;r++){
            this.data[r] = [];
            for(var c=0;c<this.CN;c++){
                //[[0,0,0,0],[0,0,0,0],[0,0,0,0],[0,0,0,0]]
                this.data[r][c] = 0;
            }
        }
        //调用方法 randomNum()
        this.randomNum();
        this.randomNum();
//        console.log(this.data);

        //显示到id为gridPanel下的子div上upDataView()
        this.upDateView();
        //响应键盘事件
        document.onkeydown = function(e){
            if(e.keyCode==37){
                console.log("左");

                this.moveLeft();
            }else if(e.keyCode==38){
                console.log("上");

                this.moveUp();
            }else if(e.keyCode==39){
                console.log("右");

                this.moveRight();
            }else if(e.keyCode==40){
                console.log("下");
                this.moveDown();
            }
        }.bind(this);//绑定到当前game上
    },
    //随机生成一个数字 放到data的二维数组中元素为0的位置上
    randomNum:function(){

        while(true){
            var r = Math.floor(Math.random()*this.RN);
            var c = Math.floor(Math.random()*this.CN);
//            console.log(r,c);
            if(this.data[r][c]==0){
                console.log("aaaa");
                this.data[r][c] = Math.random()<0.5?2:4;
                break;
            }
        }
    },
    //把data中的数据更新到页面的div中
    upDateView:function(){
        for(var r=0;r<this.RN;r++){
            for(var c=0;c<this.CN;c++){
                var panel1 = document.getElementById("c"+r+c);
                if(this.data[r][c]!=0){
                    console.log(panel1);
                    panel1.innerHTML = this.data[r][c];
                    panel1.className = "cell n"+this.data[r][c];
                }else{
                    panel1.innerHTML = "";
                    panel1.className = "cell";
                }

            }
        }
        if(this.state==this.GAMEOVER){
            var over = document.getElementById("gameOver");
            over.style.display = "block";
        }
    },
    isGameOver:function(){
        for(var r=0;r<this.RN;r++){
            for(var c=0;c<this.CN;c++){
                if(this.data[r][c]==0){
                    return false
                }
                if(c!=this.CN&&this.data[r][c]==this.data[r][c+1]){
                    return false;
                }else if(r!=this.RN&&this.data[r][c]==this.data[r+1][c]){
                    return false
                }
            }
        }
        return true;
    },
    //向左移动所有的行
    moveLeft:function(){
        var a=1;
        while(a==1){
            a=0;
            for(var r=0;r<this.RN;r++){
                for(var c=0;c<this.CN;c++){
                    if(r>0&&this.data[r-1][c]==0&&this.data[r][c]!=0){
                        this.data[r-1][c] = this.data[r][c];
                        this.data[r][c] = 0;
                        console.log("左移");
                        a=1;
                    }
                    if(r>0&&this.data[r-1][c]==this.data[r][c]&&this.data[r][c]!=0){
                        this.data[r-1][c] = this.data[r-1][c]*2;
                        this.data[r][c]=0;
                        a=1;
                    }
                }
            }
        }
        this.randomNum();
        this.upDateView();
    },

    moveUp:function(){},
    moveRight:function(){},
    moveDown:function(){}

}
window.onload = function(){
    game.start();
}
*/
</script>