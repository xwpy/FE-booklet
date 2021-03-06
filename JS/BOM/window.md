# 理解javascript中的浏览器窗口——窗口基本操作

　　BOM全称brower object model(浏览器对象模型)，用于管理窗口及窗口间的通讯，其核心对象是window。称其为窗口，可能并不准确。因为，有的浏览器窗口可能包含多个标签页，每个标签页都有自己的window对象。本文将详细该内容

&nbsp;

### 窗口位置

【1】获取

　　浏览器(firefox不支持)提供了screenLeft和screenTop属性，分别用于表示窗口相对于屏幕左边和上边的位置

　　在窗口最大化的情况下，运行下列代码时，各个浏览器返回的值并不相同。chrome返回left:0;top:0。而IE则返回left:0;top:56(若有菜单栏，则返回left:0;top:78)，这是因为IE中保存的是从屏幕左边和上边到由window对象表示的页面可见区域的距离。safari则由于自身的bug，返回left:-8;top:-8

<div class="cnblogs_code">
<pre>//移动窗口，会有数值的变化
&lt;div id='myDiv'&gt;&lt;/div&gt;
&lt;script&gt;
var timer = setInterval(function(){
    myDiv.innerHTML = 'left:' + window.screenLeft + ';top:' + window.screenTop;
})
myDiv.onclick = function(){
    clearInterval(timer);
}
&lt;/script&gt;</pre>
</div>

<iframe style="line-height: 1.5; width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w1.html" frameborder="0" width="320" height="240"></iframe>

　　screenX和screenY属性(IE8-)也提供相同的窗口位置信息

　　[注意]screenLeft、screenTop、screenX和screenY都是只读属性，修改他们的值，并不会使得窗口发生移动

　　在窗口最大化的情况下，各个浏览器返回的值依然不相同。firefox返回left:-7;top:-7。chrome依然返回left:0;top:0。而IE9+不论是否显示菜单栏始终返回left:-7;top:-7。safari则由于自身的bug，依然返回left:-8;top:-8

<div class="cnblogs_code">
<pre>&lt;div id='myDiv'&gt;&lt;/div&gt;
&lt;script&gt;
var timer = setInterval(function(){
    myDiv.innerHTML = 'left:' + window.screenX + ';top:' + window.screenY;
})
myDiv.onclick = function(){
    clearInterval(timer);
}
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w2.html" frameborder="0" width="320" height="240"></iframe>

**兼容**

　　获取窗口位置的兼容写法如下

　　[注意]由于各浏览器的实现不同，无法在跨浏览器条件下取得精确坐标值

<div class="cnblogs_code">
<pre>    var leftPos = (typeof window.screenLeft == "number") ? window.screenLeft : window.screenX;
    var topPos = (typeof window.screenTop == "number") ? window.screenTop : window.screenY;
    console.log(leftPos,topPos);   </pre>
</div>

【2】移动

　　使用moveTo()和moveBy()方法可以将窗口精确移动到一个新位置，这两个方法只有IE浏览器支持

　　moveTo()接收两个参数，分别是新位置的x和y坐标值

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
//将窗口移动到(0,0)处
myDiv.onclick = function(){
    window.moveTo(0,100); 
}    
&lt;/script&gt;</pre>
</div>

&nbsp;　　moveBy()接收两个参数，分别是水平和垂直方向上移动像素数

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
//将窗口向下移动100像素
myDiv.onclick = function(){
    window.moveBy(0,100); 
}   
&lt;/script&gt;</pre>
</div>

&nbsp;

### 窗口大小

【1】获取

　　outerWidth和outerHeight属性用于表示浏览器窗口本身的尺寸

　　[注意]IE8-浏览器不支持

<div class="cnblogs_code">
<pre>//chrome返回outerWidth:1920;outerHeight:1030
//IE9+和firefox返回outerWidth:1550;outerHeight:838 
//safari返回outerWidth:1552;outerHeight:840
document.body.innerHTML = 'outerWidth:' + window.outerWidth + ';outerHeight:' + window.outerHeight</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w3.html" frameborder="0" width="320" height="240"></iframe>

　　innerWidth和innerHeight属性用于表示页面大小，实际上等于浏览器窗口尺寸大小减去浏览器自身边框及菜单栏、地址栏、状态栏等的宽度

　　[注意]IE8-浏览器不支持

　　由于&lt;iframe&gt;本身也有window属性，如果页面中存在框架，那么框架中的innerWidth和innerHeight属性指的是框架本身的innerWidth和innerHeight属性

<div class="cnblogs_code">
<pre>//chrome返回innerWidth:1920;innerHeight:971
//IE9+返回innerWidth:1536;innerHeight:768 
//firefox返回innerWidth:1536;innerHeight:755
//safari返回innerWidth:1536;innerHeight:764
document.body.innerHTML = 'innerWidth:' + window.innerWidth + ';innerHeight:' + window.innerHeight</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w4.html" frameborder="0" width="320" height="240"></iframe>

　　DOM中的document.documentElement.clientWidth和document.documentElement.clientHeight也可以表示页面大小(不包含滚动条)，与innerWidth和innerHeight返回相同的值

 　　[注意]类似地，如果访问框架，这两个属性也指向框架的属性

<div class="cnblogs_code">
<pre>//chrome返回innerWidth:1920;innerHeight:971
//IE9+返回innerWidth:1536;innerHeight:768 
//firefox返回innerWidth:1536;innerHeight:755
//safari返回innerWidth:1536;innerHeight:764    
document.body.innerHTML = 'clientWidth:' + document.documentElement.clientWidth + ';clientHeight:' + document.documentElement.clientHeight</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w5.html" frameborder="0" width="320" height="240"></iframe>

　　如果没有滚动条，这两类属性在电脑端表示同样的值，在移动端却有不同的用途。innerWidth和innerHeight表示的是视觉视口，即用户正在看到的网站的区域；而document.documentElement.clientWidth和clientHeight表示的是布局视口，指CSS布局的尺寸。[详细情况移步至此](http://www.cnblogs.com/xiaohuochai/p/5496995.html)

【2】调整

　　使用resizeTo()和resizeBy()这两个方法可以用来调整浏览器窗口的大小&nbsp;

　　[注意]只有IE和safari浏览器支持

　　resizeTo()接收两个参数：浏览器窗口的新宽度和新高度

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
myDiv.onclick = function(){
    //将浏览器窗口大小调整到200,200
    window.resizeTo(200,200);
}
&lt;/script&gt;    </pre>
</div>

　　resizeBy()接收两个参数：浏览器新窗口与原窗口的宽度和高度之差

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
myDiv.onclick = function(){
    //将浏览器窗口宽度减小100
    window.resizeBy(-100,0);
}
&lt;/script&gt;    </pre>
</div>

&nbsp;

### 打开窗口

　　window.open()方法可以导航到一个特定的URL，也可以打开一个新的浏览器窗口。这个方法接收4个参数：要加载的URL、窗口目标、一个特性字符串以及一个表示新页面是否取代浏览器历史记录中当前加载页面的布尔值

**参数**

　　【1】通常只需要传递第一个参数，默认在新窗口打开

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
myDiv.onclick = function(){
    window.open("http://baidu.com");
}
&lt;/script&gt;    </pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w6.html" frameborder="0" width="320" height="240"></iframe>

　　【2】第二个参数表示已有窗口或者框架的名称，或者是_self、_parent、_top、_blank等窗口打开方式

　　[注意]关于窗口打开方式详细情况[移步至此](http://www.cnblogs.com/xiaohuochai/p/5007282.html#anchor2)

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
//在当前窗口打开
myDiv.onclick = function(){
    window.open("http://baidu.com",'_self');
}
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w7.html" frameborder="0" width="320" height="240"></iframe>

　　【3】第三个参数是一个逗号分隔的设置字符串，表示在新窗口中都显示哪些特性

![open](https://pic.xiaohuochai.site/blog/JS_BOM_open.jpg)
<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
myDiv.onclick = function(){
    //在新窗口中打开高度为500，宽度为500，纵坐标为0，横坐标为200的qq网页
    window.open("http://qq.com","_blank","height=500,width=500,top=0,left=200")
} 
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w8.html" frameborder="0" width="320" height="240"></iframe>

　　【4】第四个参数只在第二个参数命名的是一个存在的窗口时才有用。它是一个布尔值，声明了由第一个参数指定的URL是应用替换掉窗口浏览历史的当前条目(true)，还是应该在窗口浏览历史中创建一个新的条目(false)，后者是默认的设置

**返回值**

　　open()方法的返回值是新窗口的Window对象

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
myDiv.onclick = function(){
    var w = window.open();
    w.document.body.innerHTML = '测试文字';
}
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w9.html" frameborder="0" width="320" height="240"></iframe>

　　新创建的window对象有一个opener属性，其中保存着打开它的原始窗口对象

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
myDiv.onclick = function(){
    var w = window.open();
    console.log(w.opener === window);//true
}
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w10.html" frameborder="0" width="320" height="240"></iframe>

**过滤**

　　大部分浏览器都有弹出窗口过滤系统。通常，open()方法只有当用户手动单击按钮或者链接的时候才会调用。javascript代码尝试在浏览器初始载入时开启一个弹出窗口时，通常会失败。如果被拦截，则返回值是undefined

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
var w = window.open();
console.log(w);//undefined
&lt;/script&gt;</pre>
</div>

&nbsp;

### 窗口关闭

　　就像方法open()打开一个新窗口一样，方法close()将关闭一个窗口。如果已经创建了 Window对象w，可以使用如下的代码将它关掉

<div class="cnblogs_code">
<pre>&lt;div&gt;
    &lt;span id="span1"&gt;打开窗口&lt;/span&gt;
    &lt;span id="span2"&gt;关闭窗口&lt;/span&gt;    
&lt;/div&gt;
&lt;script&gt;
var w;
span1.onclick = function(){
    w = window.open();
}
span2.onclick = function(){
    if(w){
        w.close();
    }
}
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w11.html" frameborder="0" width="320" height="240"></iframe>

　　新窗口的对象w还有一个closed属性，用于检测是否被关闭

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;点击此处&lt;/div&gt;
&lt;script&gt;
//先显示false，1s后显示true
myDiv.onclick = function(){
    var w = window.open();
    console.log(w.closed);>//>false
    setTimeout(function(){
        w.close();
        console.log(w.closed);>//>true
    },1000);

}
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w12.html" frameborder="0" width="320" height="240"></iframe>

**小应用**

　　通过window.open()返回的对象可以操作新打开窗口的开闭

<div class="cnblogs_code">
<pre>&lt;div id="myDiv"&gt;打开窗口&lt;/div&gt;
&lt;script&gt;
    var w = null;
    myDiv.onclick = function(){
        //如果w不存在，即没有打开新窗口，或新窗口被关闭
        if(!w){
            w = window.open("http://baidu.com","_blank","height=400,width=400,top=10,left=10");
            myDiv.innerHTML = '关闭窗口';
        //如果w存在，说明新窗口被打开
        }else{
            w.close();
            w = null;
            myDiv.innerHTML = '打开窗口';
        }
    }
&lt;/script&gt;</pre>
</div>

<iframe style="width: 100%; height: 40px;" src="https://demo.xiaohuochai.site/js/window/w13.html" frameborder="0" width="320" height="240"></iframe>

